## Overview

OxiRAG is a four-layer RAG pipeline built entirely in Rust, combining semantic search, speculative draft verification, formal logic verification via SMT solving, and knowledge graph-based retrieval. It supports both native (Tokio) and WASM runtimes.

## Architecture

The pipeline consists of four specialized layers:

- **Layer 1 (Echo)**: Semantic search using vector embeddings with support for Cosine, Euclidean, and Dot Product similarity metrics. Includes an in-memory vector store with configurable capacity and pluggable embedding providers (Candle BERT, mock for testing).
- **Layer 2 (Speculator)**: Draft verification with a rule-based speculator for quick checks or optional Candle-based SLM for advanced verification. Supports Accept/Revise/Reject decision pipeline.
- **Layer 3 (Judge)**: SMT-based logic verification with claim extraction from natural language, SMT-LIB encoding of logical claims, and OxiZ SMT solver integration for formal verification of temporal, causal, and modal claim structures.
- **Layer 4 (Graph)**: Knowledge graph-based retrieval (GraphRAG) with entity and relationship extraction from documents, in-memory graph store supporting BFS traversal, shortest path, and N-hop queries, and hybrid search combining vector and graph results.

## Key Innovations

- **Speculative RAG**: Uses cache as drafts, not answers — verified with SLM before finalizing
- **Context-Aware Prefix Caching**: Efficient KV cache management with context fingerprinting, LRU eviction with TTL, and prefix matching for partial cache hits
- **On-the-fly Distillation**: Automatic generation of specialized lightweight models for frequent queries, with query pattern frequency tracking, Q&A pair collection, and training example export for LoRA fine-tuning
- **Hidden States Manipulation**: Direct manipulation of transformer hidden states for verification

## Feature Flags

- `native` — Enable native runtime with Tokio (default)
- `wasm` — Enable WASM bindings
- `echo` — Enable Layer 1 (semantic search) (default)
- `speculator` — Enable Layer 2 with Candle SLM
- `judge` — Enable Layer 3 with OxiZ SMT solver
- `graphrag` — Enable Layer 4 (knowledge graph)
- `prefix-cache` — Enable prefix caching for KV cache management
- `distillation` — Enable distillation tracking and Q&A collection
- `full` — Enable all features (native only)
- `cuda` — Enable CUDA acceleration for Candle
- `metal` — Enable Metal acceleration for Candle

## Distillation Support

Includes training example export for LoRA fine-tuning with feature-based distillation (FitNet, attention transfer), teacher-student architecture with progressive learning, and distillation loss functions (KL, MSE, cosine).

## Cross-Platform Support

- Full async/await support with Tokio for native runtime
- WASM bindings for browser/edge deployment via `wasm-pack`

## Project Statistics

| Metric | Value |
|--------|-------|
| Source Files | 91 Rust files |
| Lines of Code | 48,463 |
| Tests | 1,500 |
| Clippy Warnings | 0 |
| Rustdoc Warnings | 0 |

## Roadmap Progress

| Feature | Progress |
|---------|----------|
| Speculative RAG | 99% |
| Context-Aware Prefix Caching | 95% |
| Hidden States Manipulation | 90% |
| On-the-fly Distillation | 85% |

## Ecosystem

Part of the COOLJAPAN Pure Rust ecosystem alongside OxiZ (SMT solver), SciRS2 (scientific computing), NumRS2 (numerical computing), and OxiBLAS (BLAS implementation).

## Pricing

Free and open-source under the Apache License, Version 2.0.