## Overview

A Rust port of the Python sentence-transformers library, powered by the Candle ML framework. It provides an API for generating sentence and text embeddings using various pre-trained transformer models.

## Supported Models

The library includes built-in support for the following models:

- sentence-transformers/all-MiniLM-L6-v2
- sentence-transformers/all-mpnet-base-v2
- sentence-transformers/paraphrase-multilingual-MiniLM-L12-v2
- sentence-transformers/paraphrase-MiniLM-L6-v2
- sentence-transformers/all-MiniLM-L12-v2
- sentence-transformers/paraphrase-multilingual-mpnet-base-v2
- sentence-transformers/distiluse-base-multilingual-cased-v2
- sentence-transformers/paraphrase-mpnet-base-v2
- sentence-transformers/LaBSE
- BAAI/bge-small-en-v1.5
- intfloat/multilingual-e5-large
- intfloat/multilingual-e5-base
- intfloat/multilingual-e5-small

Additionally, any model based on BertModel, XLMRobertaModel, DistilBertModel, or MPNetModel architectures can be used with additional boilerplate configuration.

## Features

- **Pre-built model loading**: Use `with_sentence_transformer` to load any supported model with minimal configuration
- **Custom model support**: Load models not in the supported list using `SentenceTransformerBuilder::new()` with configuration for safetensors or PyTorch checkpoints, normalization (e.g., L2), pooling layers, and dense layers
- **GPU acceleration**: Support for CUDA devices alongside CPU inference
- **Batch processing**: Configurable batch size in tokens for efficient embedding generation
- **Cosine similarity utility**: Built-in `cosine_similarity` function for comparing embeddings
- **Hugging Face Hub integration**: Models are loaded directly from Hugging Face repositories

## Planned Architecture Support

The project aims to add support for additional architectures:

- T5EncoderModel
- RobertaModel and RobertaForMaskedLM
- Gemma3TextModel
- ModernBert
- NomicBertModel
- AlbertModel

## Pricing

Free and open-source.