## Overview

Tokenizer is a Rust project that provides a basic implementation of the Byte Pair Encoding (BPE) algorithm. BPE is a widely used technique in natural language processing that iteratively merges the most frequent pair of symbols in a corpus to learn subword units useful for NLP tasks. The project serves as both a learning tool for Rust developers interested in AI and a foundation for further exploration in tokenization.

## Features

- **BPE Implementation**: Provides a basic implementation of the Byte Pair Encoding algorithm in Rust
- **Extensible Design**: Built with modularity in mind, allowing for easy expansion with additional tokenization techniques such as GPT-2 tokenization
- **MIT License**: Open-source under the MIT License, enabling free use, modification, and distribution

## Usage

```bash
git clone https://github.com/usama3627/tokenizer.git
cd tokenizer
cargo build
cargo run
```

To train the tokenizer, download a training dataset (e.g., from Hugging Face), rename it to `myresponse.json`, and place it in the project directory.

## Dependencies

- `serde` (version 1.0.104 with derive feature)
- `serde_json` (version 1.0.48)

## Planned Enhancements

- Modularization to separate BPE implementation from other tokenization techniques
- Performance optimizations for the tokenization process
- Enhanced documentation with detailed algorithm explanations
- Integration of additional tokenization techniques for a comprehensive NLP toolkit

## License

MIT License.