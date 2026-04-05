## Overview

The `llm` crate is a Rust library that enables running inference on large language models directly on local hardware. It provides a unified interface for loading GGML-format model files and executing inference using quantized models, making it possible to run LLMs on consumer-grade machines without GPU requirements.

## Features

- Supports GGML-format model files for memory-efficient model loading
- Unified inference API across supported model architectures
- Local inference without cloud dependencies or API keys
- Quantized model support for reduced memory footprint
- Streaming token generation for interactive applications
- Compatible with popular open-source LLM architectures
- Multi-backend support including CPU inference

## Supported Model Architectures

- LLaMA
- GPT-NeoX
- GPT-J
- Bloom
- MPT

## Use Cases

- Local LLM inference in Rust applications
- Building AI-powered CLI tools and desktop applications
- Edge deployment of language models
- Research and experimentation with LLM architectures
- Building RAG pipelines with local inference

## Pricing

Free and open-source under the Apache 2.0 license.