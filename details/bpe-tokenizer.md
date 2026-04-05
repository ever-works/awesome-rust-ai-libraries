## Overview

bpe-tokenizer is a Rust crate that provides Byte Pair Encoding (BPE) tokenization functionality. It allows users to tokenize text into subword units using pre-trained vocabularies. BPE is a widely-used technique in natural language processing (NLP) that breaks down words into subword tokens based on the most frequent token pairs.

The crate supports Unicode-aware text segmentation for sentence and word splitting, making it suitable for processing a variety of languages and scripts. Pre-trained multilingual vocabularies are sourced from the BPEmb project, supporting tokenization in 275 languages.

## Features

- **Custom BPE vocabularies**: Bring your own BPE token vocabularies or use built-in ones.
- **Pre-trained multilingual vocabularies**: Sourced from the BPEmb project with support for 275 languages, pre-trained on Wikipedia data.
- **Three vocabulary sizes** available as optional Cargo features:
  - `default-small` (100,000 tokens): Suitable for memory-constrained environments.
  - `default-medium` (320,000 tokens): Balances token coverage and memory efficiency.
  - `default-large` (1,000,000 tokens): Provides the most detailed token representations for high-granularity tasks.
- **Unicode-aware segmentation**: Leverages the `unicode-segmentation` crate for proper text splitting across languages.
- **Multiple tokenization modes**:
  - `tokenize`: Splits and flattens text into a flat `Vec<String>`.
  - `tokenize_sentences`: Tokenizes into nested sentence vectors `Vec<Vec<String>>`, useful for processing multiple sentences separately.
  - `tokenize_iter` / `tokenize_sentences_iter`: Provides an iterator over generated tokens for better memory efficiency in large-scale text processing.
- **Load vocabularies from string or file**: Create encoders via `new_from_str` or `new_from_file`.

## Usage

Install via Cargo:
```bash
cargo add bpe-tokenizer
```

Basic example:
```rust
use bpe_tokenizer::BytePairEncoder;

let vocab = BytePairEncoder::new_from_str("hello\t1\nworld\t2").unwrap();
let tokenized = vocab.tokenize("Hello, world!");
// Output: ["<s>", "▁hello", "▁world", "</s>"]
```

With default medium vocabulary:
```rust
use bpe_tokenizer::BytePairEncoder;

let encoder = BytePairEncoder::new_default_medium().unwrap();
let tokenized = encoder.tokenize("This is a test sentence.");
// Output: ["<s>", "▁this", "▁is", "▁a", "▁test", "▁sentence", "</s>"]
```

## Licensing

This crate is licensed under the MIT License. The pre-trained vocabularies from BPEmb are also MIT-licensed.