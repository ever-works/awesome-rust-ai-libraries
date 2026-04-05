## Overview

SemanticSimilarity-rs is a small Rust library designed to compute similarity and dissimilarity metrics between embeddings using vector distance. It allows developers to bring their own embedding models and compute similarity/distance scores on the resulting vectors.

## Distance Measures

The library implements the following distance and similarity measures:

- **Cosine** — handles both normalized and non-normalized vectors
- **Euclidean** — straight-line distance between vectors
- **Manhattan** — sum of absolute differences along each dimension
- **Chebyshev** — maximum absolute difference along any single dimension
- **Angular** — angular distance between vectors
- **Jaccard Index** — similarity measure for sets
- **Levenshtein** — edit distance for sequences
- **Minkowski** — generalized distance metric parameterized by p
- **Dot product** — inner product of two vectors

## Features

- **Parallel Computation** — Utilizes `rayon` for parallel processing of distance computations
- **Bring your own embedding** — Works with any embedding model; the library is decoupled from embedding generation
- **Simple API** — Direct function calls like `cosine_similarity()` and `euclidean_distance()`

## Installation

Add to your `Cargo.toml`:

```toml
[dependencies]
semanticsimilarity_rs = "0.1.0"
```

Or via cargo add:

```bash
cargo add semanticsimilarity_rs
```

## Usage

```rust
use semanticsimilarity_rs::{cosine_similarity, euclidean_distance};

fn main() {
    let vec1: [f64; 3] = [1.0, 2.0, 3.0];
    let vec2: [f64; 3] = [4.0, 5.0, 6.0];

    let similarity = cosine_similarity(&vec1, &vec2, false);

    println!("Cosine similarity between vec1 and vec2: {}", similarity);
}
```

## Pricing

Free and open-source.