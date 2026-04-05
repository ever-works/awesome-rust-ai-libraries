## Overview

vLLM is a high-throughput and memory-efficient inference and serving engine for large language models. It is designed to address the memory bottleneck of attention computation during autoregressive decoding.

## Key Features

- **PagedAttention**: Efficiently manages attention key and value memory via paging, analogous to virtual memory in operating systems
- **Continuous batching**: Dynamically batches incoming requests to maximize throughput
- **High throughput**: Achieves up to 24x higher throughput than HuggingFace Transformers without architectural changes
- **Optimized CUDA kernels**: Uses optimized CUDA kernels for attention and other operations
- **Distributed serving**: Supports tensor parallelism and pipeline parallelism for serving large models across multiple GPUs
- **Streaming outputs**: Supports streaming generation and various sampling parameters
- **OpenAI-compatible API**: Provides an OpenAI-compatible server API for easy integration
- **Multi-platform support**: Works with various hardware backends including NVIDIA GPUs, AMD GPUs, and Intel CPUs/XPUs

## Supported Models

Supports a wide range of LLM architectures including LLaMA, Mistral, Mixtral, Qwen, DeepSeek, Gemma, Yi, Phi, Falcon, Baichuan, and many more.

## Pricing

Free and open-source under the Apache 2.0 license.