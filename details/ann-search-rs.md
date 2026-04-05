## Overview

ann-search-rs is a Rust library providing various approximate nearest neighbour (ANN) and vector search algorithms. Originally extracted from bixverse (a R/Rust package for computational biology), it exposes ANN APIs for use across the Rust ecosystem. The library features optimized implementations with SIMD, multi-threading, and optimized memory access structures.

## ANN Algorithms

- **Annoy** (Approximate Nearest Neighbours Oh Yeah)
- **BallTree**
- **HNSW** (Hierarchical Navigable Small World)
- **NNDescent** (Nearest Neighbour Descent, inspired by PyNNDescent)
- **LSH** (Locality Sensitive Hashing)
- **IVF** (Inverted File index)
- **Exhaustive Flat Index**
- **Vamana** (the graph powering DiskANN)

## Distance Metrics

- Euclidean
- Cosine

## Quantised Indices (optional `quantised` feature)

- **BF16**: Brain floating point 16 quantisation for exhaustive and IVF indices
- **SQ8**: Scalar int8 quantisation for exhaustive and IVF indices
- **PQ**: Product quantisation for IVF indices (ideal for dimensions ≥ 128)
- **OPQ**: Optimised product quantisation for IVF indices

## GPU-Accelerated Indices (optional `gpu` feature)

- Exhaustive flat index with GPU acceleration
- IVF (Inverted File index) with GPU acceleration
- CAGRA style index

Uses cubecl with wgpu backend for system-agnostic GPU support.

## Binarised Indices (optional `binary` feature)

- **Binary**: Different types of binary quantisations for exhaustive and IVF indices (SimHash random projection or ITQ via PCA)
- **RaBitQ**: RaBitQ quantisation for exhaustive and IVF indices with additional data for approximate distance calculations

Binary indices support on-disk storage of original vectors for subsequent re-ranking to improve recall.

## Installation

```toml
# Basic
[dependencies]
ann-search-rs = "*"

# With quantization
ann-search-rs = { version = "*", features = ["quantised"] }

# With GPU support
ann-search-rs = { version = "*", features = ["gpu"] }

# With binary indices
ann-search-rs = { version = "*", features = ["binary"] }
```

## Roadmap

- GPU support (implemented in v0.2.1)
- Binary indices (implemented in v0.2.1)
- Proper SIMD (implemented in v0.2.2 via the wide crate)
- On-disk index storage and querying
- Expanded GPU support for additional indices

## Licensing

MIT License.