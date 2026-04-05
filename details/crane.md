## Overview

Crane (Crane - Candle-based Rust Accelerated Neural Engine) is a high-performance inference framework leveraging Rust's Candle for maximum speed on CPU/GPU. It bridges the gap between PyTorch's suboptimal inference performance and llama.cpp's complex C++ codebase by combining Candle's efficiency with Rust's reliability and Python-like ergonomics.

## Supported Models

- **LLMs:** Qwen3 (0.6B–30B+), Qwen 2.5 (0.5B–72B), Hunyuan Dense
- **Vision-Language Models:** Qwen3 VL (2B, 4B), PaddleOCR VL 0.9B / 1.5
- **Speech:** Moonshine ASR, Silero VAD, Qwen3-TTS (12Hz, 24kHz, 16-codebook RVQGAN + native Candle decoder, voice cloning), Spark-TTS, Orpheus-TTS (WIP)

## Key Features

- **Blazing-Fast Inference:** Outperforms native PyTorch with Candle's optimized kernels; up to 6x faster on Apple Silicon (M1/M2/M3) compared to vanilla Transformers
- **Rust-Powered:** Eliminates C++ complexity while maintaining native performance
- **Apple Silicon Optimized:** GPU acceleration via Metal on macOS devices (3–5x speedup over CPU-only)
- **Hardware Agnostic:** Unified codebase for CPU, CUDA, and Metal execution
- **OpenAI & SGLang Compatible API:** Full API server in crane-oai with continuous batching
- **Out-of-Box AI Abilities:** Basic LLM chat, VLM chat, OCR with VLM, TTS, ASR, VAD, and more
- **Simplified Model Addition:** Add new models with <100 LOC in most cases

## Inference Optimizations

- Pre-allocated KV cache
- GQA 4D matmul
- Fused RoPE with cache pre-growth
- GGUF quantization support
- Batched decode
- Smart sampling fallback for large vocabularies
- Configurable environment variables for GPU top-k, top-p fallback, CPU sampling, and sampling trace

## OpenAI-Style API Endpoints

The crane-oai server supports:

| Family | Endpoint | Description |
|---|---|---|
| OpenAI | POST /v1/chat/completions | Chat completions (streaming & non-streaming) |
| OpenAI | POST /v1/completions | Text completions |
| OpenAI | POST /v1/audio/speech | Text-to-speech (Qwen3-TTS) |
| OpenAI | GET /v1/models | List models |
| OpenAI | POST /v1/tokenize | Tokenize text |
| OpenAI | POST /v1/detokenize | Detokenize tokens |
| SGLang | POST /generate | Native text generation |
| SGLang | GET /model_info | Model metadata |
| SGLang | GET /server_info | Server stats |
| SGLang | GET /health_generate | Deep health check |
| Mgmt | GET /health | Health check |
| Mgmt | GET /v1/stats | Engine statistics |

## Project Structure

- **crane-core:** Core library with model implementations, tokenizer, and generation logic
- **crane:** High-level SDK with chat, vision, audio, and multimodal clients (demonstration binaries)
- **crane-oai:** OpenAI & SGLang compatible API server with continuous batching inference engine
- **example:** Example binaries for chat, ASR, vision, OCR, and TTS

## Speed Benchmarks (f16)

| Model/Platform | Mac M1 Metal | Mac M1 Metal 16 | PyTorch |
|---|---|---|---|
| Qwen2.5-500M | 17.5 t/s | 35 t/s | 6.9 t/s |

## Build Options

```bash
# CPU
cargo build --release

# CUDA (GPU)
cargo build --release --features cuda
```

## TTS Capabilities

- **CustomVoice:** Predefined speakers for Chinese, English, Japanese
- **Voice Clone (Base model):** Clone speech from reference audio using ICL
- **Output formats:** wav, pcm

## Pricing

Free and open-source under the Apache 2.0 license.