## Overview

hnsw-rust is a pure Rust implementation of the Hierarchical Navigable Small World (HNSW) algorithm, a state-of-the-art approach to Approximate Nearest Neighbor (ANN) search in high-dimensional spaces.

## Algorithm Details

The HNSW algorithm constructs a layered graph structure with the following properties:

- **Higher layers** (less dense): Used for rapid global navigation across the search space
- **Lower layers** (more dense): Facilitate fine-grained local search to refine nearest neighbor results
- **Greedy heuristic**: Search commences from a high layer and iteratively moves to the closest node to the target, transitioning down to denser layers
- **Probabilistic insertion**: New nodes start at the lowest layer, with inclusion in higher layers governed by a probabilistic threshold that decreases exponentially

This structure mirrors the 'small world' phenomenon observed in social networks, where short path lengths exist between any two nodes, enabling efficient navigation in sparse, high-dimensional spaces.

## Key Features

- Pure Rust implementation with no external dependencies for the core algorithm
- Layered graph structure enabling logarithmic search complexity
- Greedy nearest neighbor traversal across multiple layers
- Probabilistic node placement for balanced graph construction
- Suitable for high-dimensional vector similarity search

## References

The implementation is based on the following works:

- Malkov, Yu. A., & Yashunin, D. A. (2016). Efficient and robust approximate nearest neighbor search using Hierarchical Navigable Small World graphs. arXiv preprint arXiv:1603.09320.
- Watts, D. J., & Strogatz, S. H. (1998). Collective dynamics of 'small-world' networks. Nature, 393(6684), 440-442.
- Kleinberg, J. M. (2000). The small-world phenomenon: An algorithmic perspective. Proceedings of the 32nd annual ACM symposium on Theory of computing.

## Pricing

Free and open-source.