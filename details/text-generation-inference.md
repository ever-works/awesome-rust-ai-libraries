## Overview

Text Generation Inference (TGI) is a high-performance, production-ready text generation server built in Rust by Hugging Face. It powers the Hugging Face Inference API and is a widely used solution for serving transformer-based language models.

## Features

- High-performance text generation serving
- Native Rust implementation for safety and speed
- gRPC and HTTP API support
- Optimized for hosting transformer models (LLaMA, BLOOM, StarCoder, etc.)
- Tensor parallelism for multi-GPU inference
- Optimized inference with continuous batching
- Production-ready deployment architecture