## Overview

fast-hnsw is a pure-Rust, dependency-free implementation of Hierarchical Navigable Small World (HNSW) approximate nearest-neighbour (ANN) search, based on Malkov & Yashunin's 2018 IEEE TPAMI paper. The crate requires zero C/C++ dependencies and provides full algorithmic fidelity with comprehensive testing.

## Features

### Core Capabilities
- **Pure Rust** — zero C/C++ dependencies (including `memmap2`, also pure Rust)
- **Full algorithmic fidelity** — heuristic (Algorithm 4) and simple (Algorithm 3) neighbour selection; `extendCandidates`; `keepPrunedConnections`
- **Five built-in distance metrics** — Euclidean, Squared Euclidean, Cosine, Dot-product, Manhattan; custom metrics via the `Distance` trait
- **Five index types**:
  - `Hnsw<D>` — plain ANN search
  - `LabeledIndex<D, L>` — with typed payload (class label, text tag, secondary embedding)
  - `PairedIndex<A, B>` — two independent HNSW graphs over the same items (text+image, query+doc)
  - Custom payload types via the `Payload` trait (encode/decode)

### Pruning Strategies
- **PruneStrategy::Simple** (default) — sort by stored distance and truncate; ~25 ns per prune; beats hnsw_rs at every workload
- **PruneStrategy::Heuristic** (opt-in) — full Algorithm 4 diversity check; ~1–11 µs per prune; recovers the quality gap vs Simple on high-dimensional data

### Persistence
- Binary file format with save / load / `load_mmap` support
- Vector section at fixed byte 256 offset for zero-copy memory-mapping
- Fixed-stride types use a flat layout; variable-width types get an offset table

### Internal Optimizations
- **Visited-node set**: generation counter instead of HashSet (105 ns vs 1,703 ns per call)
- **Flat vector store**: id × dim indexing in a single `Vec<f32>` — guaranteed single cache line, no pointer chase
- **Reusable heaps**: candidate and result heaps cleared rather than reallocated
- **(u32, f32) connection pairs**: storing distance at edge-add time enables zero-computation pruning

## API

### Builder Configuration

| Method | Default | Description |
|---|---|---|
| `.m(usize)` | 16 | Max bidirectional links per node per non-zero layer. Must be ≥ 2. |
| `.m0(usize)` | 2 × M | Max links at layer 0 specifically. |
| `.ef_construction(usize)` | 200 | Beam width during index build. Higher = better quality, slower inserts. |
| `.heuristic(bool)` | true | Use heuristic neighbour selection (Algorithm 4). |
| `.extend_candidates(bool)` | false | Expand candidates with their neighbours during selection. |
| `.keep_pruned(bool)` | true | Pad with pruned candidates when heuristic selects fewer than M. |
| `.prune_strategy(PruneStrategy)` | Simple | How to shrink an existing neighbour's list when it overflows. |
| `.capacity(usize)` | 0 | Expected number of vectors. Pre-allocates internal buffers. |
| `.seed(u64)` | entropy | Fix RNG seed for reproducible index layouts. |

### Hnsw Methods
- `insert(Vec<f32>) -> usize` — Add a vector; returns its assigned id (0-based)
- `search(&[f32], k, ef) -> Vec<SearchResult>` — Return the k approximate nearest neighbours
- `get_vector(id) -> &[f32]` — Retrieve a stored vector by id
- `len() / is_empty() / dim() / max_level()` — Index introspection
- `stats() -> IndexStats` — Layer-by-layer node and edge counts

## Benchmarks

Compared against hnsw_rs v0.3.3 and hnsw v0.11 (rust-cv):

### Insert Throughput (vectors/sec, PruneStrategy::Simple)
- n=1k, dim=32: 18,451 (1.80× vs hnsw_rs)
- n=50k, dim=128: 2,241 (2.14× vs hnsw_rs)

### Search Throughput (queries/sec at ef=200)
- n=1k, dim=32: 15,194 (1.87× vs hnsw_rs)
- n=50k, dim=128: 1,836 (2.12× vs hnsw_rs)

### Recall@10 at ef=200
- n=1k, dim=32: 100.0% (+1.4 pp vs hnsw_rs)
- n=10k, dim=128: 95.6% (+2.0 pp vs hnsw_rs)

### Persistence Benchmarks
- **Save throughput**: 530–1130 MB/s for fixed-payload types; 350–680 MB/s for variable-width
- **mmap-load speedup**: 76–91× for bare Hnsw; 68–88× for PairedIndex (at n=50k/dim=128)
- **At n=50k/dim=128**: owned load 865 ms vs mmap load 11 ms

## Distance Metrics

| Type | Formula |
|---|---|
| Euclidean | ‖a − b‖₂ |
| SquaredEuclidean | ‖a − b‖₂² (no sqrt, preserves NN order) |
| Cosine | 1 − cos(a, b) |
| DotProduct | 1 − a·b |
| Manhattan | ‖a − b‖₁ |

## Tuning Guide

| Goal | Lever |
|---|---|
| Higher recall | Increase `ef` at query time and/or `ef_construction` at build time |
| Faster search | Reduce `ef` |
| Lower memory | Reduce M |
| Maximum insert speed | PruneStrategy::Simple (default) |
| Maximum recall quality | PruneStrategy::Heuristic |

## Built-in Payloads

`()`, `u32`, `u64`, `i32`, `i64`, `f32`, `f64`, `String`, `Vec<u8>`, `Vec<f32>`, and `(A, B)` for any two payload types.

## Quick Start

```toml
[dependencies]
hnsw = { version = "*" }
```

## License

MIT