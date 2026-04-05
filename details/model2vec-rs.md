## Overview

model2vec-rs is a Rust crate providing an efficient implementation for inference with Model2Vec static embedding models. Model2Vec is a technique for creating compact and fast static embedding models from sentence transformers, achieving significant reductions in model size and inference speed. The Rust implementation is optimized for performance, running approximately 1.7× faster than the Python version (8000 samples/second vs 4650 samples/second in single-threaded CPU benchmarks).

## Usage

The crate can be used in two ways:

- **As a library**: Integrate into Rust applications via `cargo add model2vec-rs` and use the `StaticModel::from_pretrained` API to load models and generate embeddings.
- **As a CLI tool**: Install via `cargo install model2vec-rs` for quick terminal-based encoding of single sentences or files of text.

## Features

- **Fast Inference**: Optimized Rust implementation achieving 8000 samples/second throughput on CPU (vs 4650 for Python).
- **Hugging Face Hub Integration**: Load pre-trained Model2Vec models directly from the Hugging Face Hub using model IDs, or from local file paths.
- **Multiple Model Formats**: Supports models with f32, f16, and i8 weight types stored in safetensors files.
- **Batch Processing**: Encodes multiple sentences in batches with configurable batch sizes.
- **Configurable Encoding**: Customization of maximum sequence length and batch size during encoding.
- **Normalization Control**: Optional override of model's default normalization behavior.

## Available Models

Pre-trained potion models available on the Hugging Face Hub:

| Model | Language | Distilled From | Params | Task |
|-------|----------|----------------|--------|------|
| potion-base-32M | English | bge-base-en-v1.5 | 32.3M | General |
| potion-multilingual-128M | Multilingual | bge-m3 | 128M | General |
| potion-retrieval-32M | English | bge-base-en-v1.5 | 32.3M | Retrieval |
| potion-base-8M | English | bge-base-en-v1.5 | 7.5M | General |
| potion-base-4M | English | bge-base-en-v1.5 | 3.7M | General |
| potion-base-2M | English | bge-base-en-v1.5 | 1.8M | General |

## Licensing

MIT license.