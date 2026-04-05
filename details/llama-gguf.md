## Overview

llama-gguf is a Rust-based LLM inference engine compatible with llama.cpp's GGUF format and ONNX exports. It supports CPU inference with SIMD optimization (AVX2, AVX-512, NEON) and GPU-resident inference on CUDA, Metal (Apple Silicon), DirectX 12, and Vulkan. The project includes a full CLI, an HTTP server with OpenAI-compatible API, RAG integration with PostgreSQL/pgvector, and distributed inference via gRPC.

## Supported Model Architectures

- LLaMA/LLaMA2/LLaMA3
- Mistral
- Qwen2/Qwen2.5
- Qwen3 (dense with QK norm, partial RoPE)
- Qwen3Moe (MoE with top-k expert routing)
- Qwen3Next (hybrid attention + DeltaNet recurrent layers)
- Mixtral (MoE with top-2 expert routing)
- TinyLlama (GQA support)
- DeepSeek-Coder (linear RoPE scaling)
- CodeLlama
- Yi

## Key Features

- **GGUF Support** — Load any GGUF model file compatible with llama.cpp
- **ONNX Support** — Load HuggingFace Optimum ONNX exports (F32, F16, BF16 with auto-conversion)
- **Quantization** — All K-quant formats (Q2_K through Q8_0) plus F16/F32
- **HuggingFace Integration** — Download models directly from HuggingFace Hub
- **GPU Inference** — Full GPU-resident inference; CUDA, Metal, DX12, Vulkan via Backend trait
- **Mixture of Experts** — MoE support with top-k routing
- **DeltaNet/SSM** — Gated DeltaNet recurrent layers for hybrid attention/SSM models
- **Distributed Inference** — Pipeline-parallel inference across multiple nodes via gRPC
- **RAG** — Retrieval-Augmented Generation with PostgreSQL/pgvector vector store
- **OpenAI-compatible API** — HTTP server with streaming support
- **Grouped Query Attention** — Efficient KV cache for GQA models
- **Streaming Output** — Token-by-token generation
- **CLI** — Commands for inference, chat, serving, quantization, benchmarking, embeddings, downloads, and RAG

## Quantization Formats

| Format | Bits | Quality | Size (7B) |
|--------|------|---------|------------|
| Q2_K | 2 | Low | ~2.5 GB |
| Q3_K | 3 | Fair | ~3.0 GB |
| Q4_K_M | 4 | Good | ~4.0 GB |
| Q5_K_M | 5 | Better | ~5.0 GB |
| Q6_K | 6 | High | ~5.5 GB |
| Q8_0 | 8 | Excellent | ~7.0 GB |
| F16 | 16 | Full | ~14 GB |

## Feature Flags

| Flag | Default | Description |
|------|---------|-------------|
| cpu | Yes | CPU backend with SIMD (AVX2, AVX-512, NEON) |
| huggingface | Yes | HuggingFace Hub model downloading |
| cli | Yes | Command-line interface |
| client | Yes | HTTP client for remote inference |
| onnx | Yes | ONNX model loading via HuggingFace Optimum |
| cuda | No | NVIDIA GPU acceleration via CUDA |
| metal | No | Apple Silicon GPU acceleration via Metal |
| dx12 | No | Windows GPU acceleration via DirectX 12 |
| vulkan | No | Cross-platform GPU acceleration via Vulkan |
| server | No | HTTP server with OpenAI-compatible API |
| rag | No | RAG with PostgreSQL/pgvector vector store |
| distributed | No | Pipeline-parallel inference via gRPC |

## GPU Acceleration Details

All GPU backends support: element-wise ops (add, mul, scale), activations (SiLU, GELU), RMS norm, softmax, RoPE positional embeddings, and vector-matrix multiplication (f32).

CUDA-exclusive operations: quantized dequantization on GPU, fused RMS norm kernels, DeltaNet recurrent layer kernels, MoE expert routing and dispatch, KV cache management on GPU.

## RAG Features

- Search modes: semantic (vector), keyword (tsvector), and hybrid with Reciprocal Rank Fusion
- Distance metrics: cosine similarity, L2 distance, inner product
- Indexing: HNSW and IVFFlat with configurable parameters
- Metadata filtering: Eq, In, Range, Contains, compound AND/OR/NOT filters
- KnowledgeBase API: high-level API for document ingestion, chunking, and retrieve-and-generate
- Configuration via TOML files with environment variable overrides

## Performance

Benchmarked on Intel i9-13900K (24 cores, AVX2) with 64GB RAM:

| Model | Quantization | Tokens/sec |
|-------|-------------|------------|
| Qwen2.5-0.5B | Q4_K_M | ~1.2 t/s |
| TinyLlama-1.1B | Q4_K_M | ~1.5 t/s |
| Mistral-7B | Q4_K_M | ~0.3 t/s |

Current implementation prioritizes correctness over speed. Performance optimizations are planned.

## Installation

```bash
# From crates.io
cargo install llama-gguf

# From source
git clone https://github.com/Lexmata/llama-gguf.git
cargo build --release

# As a library
[dependencies]
llama-gguf = "0.10"
```

## License

Dual-licensed under either:

- Apache License, Version 2.0
- MIT License