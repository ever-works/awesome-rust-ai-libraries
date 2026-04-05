## Overview

rust-sentence-transformers is a Rust port of the popular [UKPLab/sentence-transformers](https://github.com/UKPLab/sentence-transformers) library, allowing users to generate sentence embeddings in Rust. The library is built on top of [rust-bert](https://github.com/guillaume-be/rust-bert).

## Features

- Supports loading BERT models fine-tuned with the original sentence-transformers Python library
- Compatible model and pooling directory structure with the original library
- Inference-only support (no training)
- Supports both CPU and CUDA (GPU) devices via torch-sys (tch-rs)
- Generates sentence embeddings from input text arrays
- Configurable batch size for encoding

## Usage

Models must be provided in a directory structure compatible with the original sentence-transformers library, with both model weights and pooling configurations.

```rust
use std::path::Path;
use tch::{Device};
use rust_sentence_transformers::model::SentenceTransformer;

let device = Device::Cpu;
let sentences = [
    "Bushnell is located at 40°33′6″N 90°30′29″W.",
    "According to the 2010 census, Bushnell has a total area of 2.138 square miles.",
];

let embedder = SentenceTransformer::new(
    Path::new("/path/to/sentence-tranformers-model/bert-base-nli-stsb-mean-tokens"),
    device)?;

let embeddings = &embedder.encode(sentences.to_vec(), 8);
```

## Dependencies

- rust-bert — Rust bindings for HuggingFace's transformers library
- tch-rs — Rust bindings for PyTorch/libtorch (provides tensor operations and device support)

## Licensing

Open-source. Refer to the repository for specific license details.