## Overview

`diskann-rs` is a Rust implementation of DiskANN based on the DiskANN paper by Microsoft Research. It uses the Vamana graph algorithm for index construction and beam search for queries, storing all index data in a single memory-mapped file to keep RAM usage well below full index size.

## Key Algorithm

- **Vamana graph construction**: Builds an approximate nearest-neighbor graph with robust α-pruning and multi-pass refinement (default: two passes, first at α = 1.0, second at user-specified α defaulting to 1.2)
- **Memory-mapped storage**: Uses `memmap2` for efficient disk-based access without loading the full index into RAM
- **Beam search query**: Uses medoid entry points and beam search over the graph, typically visiting less than 1% of indexed vectors
- **Parallel processing**: Uses `rayon` for parallel batched graph refinement during build and concurrent query processing

## Features

- **Single-file storage**: All index data (metadata, vectors, adjacency lists) stored in one memory-mapped file
- **Generic over vector element type and distance**: Works with any `T` and any `anndists::Distance`, supporting use cases beyond standard floating-point ANN
- **Distance metrics**: Support for Euclidean, Cosine, and Hamming similarity via `anndists`; generic distance trait extensible to other distances
- **Build-optimized data layout**: Uses flat contiguous storage instead of `Vec<Vec>` during construction to improve cache locality and reduce allocation overhead
- **Medoid-based entry points**: Uses an approximate medoid as the default search entry point
- **Extensive benchmarks**: Speed, accuracy, and memory consumption benchmarks against HNSW (both in-memory and on-disk)
- **Vamana graph visualization**: 2D visualization of graph build and search paths via `diskann-vamana-viz` crate

## Space and Time Complexity

- **Index Build Time**: O(n × max_degree × beam_width)
- **Disk Space**: n × (dimension × 4 + max_degree × 4) bytes
- **Search Time**: O(beam_width × log n) — typically visits < 1% of dataset
- **Memory Usage**: O(beam_width) during search
- **Query Throughput**: Scales linearly with CPU cores

## Parameter Tuning

- `max_degree`: 32–64 for most datasets
- `build_beam_width`: 128–256 for good graph quality
- `alpha`: 1.2–2.0 (higher = more diverse neighbors)
- `beam_width` (search): 128 or larger (trade-off between speed and recall)

## Index Memory-Mapping

When host RAM cannot map the entire database file, the database can be built in several smaller pieces (random split). Queries are run against each piece and results merged (ranked by distance). This shard approach can improve recall by allowing larger M and build beam width per piece.

## Performance Benchmarks

On SIFT 1M dataset (128-dim, M4 Max):
- **DiskANN**: Build time ~3907s CPU, recall 0.9997, ~24,379 req/s (k=10, beam=512)
- **HNSW (hnsw_rs)**: Build time ~3014s CPU, recall 0.9874, ~63,968 req/s (k=10, ef=64)

## Examples

- `demo.rs`: Demo with 100K vectors
- `perf_test.rs`: Performance benchmarking with 1M vectors
- `diskann_mnist.rs`: Benchmarking with MNIST fashion dataset (60K)
- `diskann_sift.rs`: Benchmarking with SIFT 1M dataset
- `bigann.rs`: Benchmarking with SIFT 10M dataset
- `hnsw_sift.rs`: Comparison with in-memory HNSW

## License

MIT License

## References

- Jayaram Subramanya, S. et al., 2019. "DiskANN: Fast Accurate Billion-Point Nearest Neighbor Search on a Single Node." NeurIPS 32.
- Based on the official Microsoft implementation of DiskANN.