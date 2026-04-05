## Overview

RAKE-rs is a Rust implementation of the Rapid Automatic Keyword Extraction algorithm, originally proposed by Stuart Rose et al. The algorithm identifies key phrases in a corpus by analyzing the frequency and co-occurrence of words.

## Features

- Multilingual support for keyword extraction
- Based on the original RAKE algorithm
- Fast implementation leveraging Rust's performance
- No external dependencies required for text processing

## How It Works

- Splits text into candidate key phrases using delimiters and stop words
- Scores each candidate based on word frequency and degree of co-occurrence
- Returns ranked key phrases by relevance score

## Use Cases

- Document summarization pipelines
- Tag generation for content
- Search engine optimization
- Information retrieval and filtering
- Preprocessing for NLP/ML workflows