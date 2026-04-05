## Overview

GraphRAG-rs is a high-performance, modular Rust implementation of Graph-based Retrieval Augmented Generation. It supports three deployment architectures: Server-Only (traditional production), WASM-Only (100% client-side browser execution), and Hybrid (WASM client with optional server). The project implements cutting-edge research papers from 2019-2025 for superior retrieval quality, achieving +20% accuracy with 99% cost savings compared to traditional approaches.

## Deployment Options

### Server-Only (Production Ready)
- Qdrant vector database integration
- Real embeddings via Ollama with GPU acceleration
- Hash-based fallback embeddings (no external dependencies)
- REST API with semantic search
- Docker Compose setup for easy deployment
- 5.2MB release binary (optimized)
- Best for: Multi-tenant SaaS, mobile apps, GPU workloads, >1M documents

### WASM-Only (100% Client-Side, Production Ready)
- Complete GraphRAG pipeline running in browser
- ONNX Runtime Web with GPU-accelerated embeddings (3-8ms inference)
- WebLLM integration (Phi-3-mini for LLM synthesis, 40-62 tok/s with WebGPU)
- Pure Rust vector search with cosine similarity
- Full Leptos UI with document upload and query interface
- Entity extraction with relationships
- Natural language answer synthesis
- IndexedDB and Cache API for browser storage
- Best for: Privacy-first apps, offline tools, zero infrastructure cost, edge deployment

### Hybrid (Planned)
- WASM client for real-time UI with optional server for heavy processing
- Best for: Enterprise apps, multi-device sync, combined UX with scalability

## Features

### Research-Based Retrieval Features
- **LightRAG Dual-Level Retrieval**: 6000x token reduction (EMNLP 2025)
- **Leiden Community Detection**: +15% modularity vs Louvain (Sci Reports 2019)
- **Cross-Encoder Reranking**: +20% accuracy improvement (EMNLP 2019)
- **HippoRAG Personalized PageRank**: 10-30x cheaper retrieval (NeurIPS 2024)
- **Semantic Chunking**: Better chunk boundaries (LangChain 2024)

### Advanced Reasoning & Optimization (Phases 2-3)
- **Symbolic Anchoring** (CatRAG-style): Grounds abstract concepts to concrete entities for better conceptual query handling
- **Dynamic Edge Weighting**: Adjusts relationship importance based on query context using semantic, temporal, and causal signals
- **Causal Chain Analysis**: Discovers multi-step causal chains with temporal consistency validation
- **Hierarchical Relationship Clustering**: Organizes relationships into multi-level hierarchies using Leiden algorithm with LLM-generated summaries
- **Graph Weight Optimization** (DW-GRPO): Learns optimal relationship weights through heuristic optimization

### Complete 7-Stage Pipeline

**Indexing (build_graph):**
1. Chunking — configurable chunk_size and chunk_overlap
2. Entity Extraction — hybrid approach with optional gleaning
3. Relationship Extraction — with gleaning support
4. Graph Construction — PageRank integration, max connections

**Query (ask):**
5. Embedding — multiple backends with configurable dimensions
6. Retrieval — hybrid strategy (semantic, keyword, BM25, graph-based)
7. Answer Generation — configurable chat model and temperature

### Chunking Strategies
- **HierarchicalChunkingStrategy**: LangChain-style with paragraph/sentence boundary preservation
- **Tree-sitter AST Chunking (cAST)**: Context-aware splitting preserving syntactic boundaries for code
- **Trait-Based Architecture**: Minimal extensible interface (ChunkingStrategy trait) with zero-cost abstractions

### Storage Options
- **Native Production**: Qdrant, LanceDB (embedded), pgvector, Neo4j (for >100k entities)
- **WASM Browser**: Voy (75KB pure Rust vector search with k-d tree), IndexedDB, Cache API

### ML Inference Backends

**Embeddings:**
- ONNX Runtime Web (GPU): 25-40x speedup, 3-8ms inference, WebGPU + CPU fallback
- Burn + wgpu (GPU): 20-40x speedup, 100% Rust
- Candle (CPU): 100% Rust, BERT/MiniLM models, 50-100ms
- Ollama: Server-side embeddings with GPU acceleration

**LLM Chatbot:**
- WebLLM: 40-62 tok/s with WebGPU, production-ready
- Candle: 2-5 tok/s CPU-only, 100% Rust
- Ollama: Server-side LLM with unlimited GPU power (CUDA, ROCm, Metal)

### Embedding Providers (8 supported)
- HuggingFace (Free, offline, 100+ models)
- OpenAI ($0.13/1M tokens, best quality)
- Voyage AI (domain-specific for code, finance, law)
- Cohere ($0.10/1M, multilingual 100+ languages)
- Jina AI ($0.02/1M, best price/performance)
- Mistral ($0.10/1M, RAG-optimized)
- Together AI ($0.008/1M, cheapest)
- Ollama (Free, local GPU)

### Ollama Integration
- Streaming responses with tokio channels
- Custom parameters (temperature, top_p, top_k, stop sequences, repeat penalty)
- Automatic DashMap-based response caching with 80%+ hit rate
- Thread-safe metrics tracking with atomic operations
- Type-safe dependency injection for all Ollama services
- Full async/await support for embeddings and language models

## Architecture

The project uses a modular workspace design with 4 publishable crates:
- **graphrag-core**: Portable core library (native + WASM), 50,000+ lines, LightRAG, PageRank, caching, incremental updates
- **graphrag-wasm**: WASM bindings, ONNX Runtime Web, WebLLM, IndexedDB + Cache API
- **graphrag-leptos**: Leptos UI components (chat, search, visualization)
- **graphrag-server**: Production REST API server with Qdrant integration, Ollama embeddings, Docker Compose

### Feature Flags
- Storage: memory-storage, persistent-storage (LanceDB), redis-storage
- Processing: parallel-processing, caching, incremental, pagerank, lightrag, rograg
- LLM/integrations: ollama, dashmap, neural-embeddings, function-calling
- GPU: cuda, metal, webgpu
- Chunking: code-chunking (tree-sitter)
- API/CLI: web-api

## Developer Experience
- Progressive API: 4 complexity levels (Simple → Easy → Builder → Advanced)
- TypedBuilder for compile-time safety
- Auto-detection of LLM/backend
- TOML configuration-driven processing with hot reload
- Interactive CLI setup wizard with domain templates
- Actionable error messages with solutions
- 220+ test cases with 100% pass rate
- Structured tracing logging throughout core library
- Zero compilation warnings with clippy

## Examples

**Simple API (one line):**
```rust
let answer = simple::answer("Your document text", "Your question")?;
```

**Stateful API (multiple queries):**
```rust
let mut graph = SimpleGraphRAG::from_text("Your document text")?;
let answer1 = graph.ask("What is this about?")?;
let answer2 = graph.ask("Who are the main characters?")?;
```

**Batch Processing:**
```rust
for file in ["doc1.txt", "doc2.txt", "doc3.txt"] {
    graphrag.add_text(&fs::read_to_string(file)?)?;
}
let answer = graphrag.ask("What connects these documents?")?;
```

**CLI Usage:**
```bash
cargo run --bin simple_cli config.toml "What are the main themes?"
```

## Performance
- ONNX Runtime Web: 25-40x speedup for embeddings, 3-8ms inference
- WebLLM: 40-62 tok/s LLM inference with WebGPU
- LightRAG Integration: 6000x token reduction vs traditional GraphRAG
- PageRank Retrieval: Fast-GraphRAG with 27x performance boost, 6x cost reduction
- Parallel async/await processing with concurrent document handling
- Intelligent LLM response caching with 80%+ hit rates
- Cache hit: <1ms vs 100-1000ms for API calls