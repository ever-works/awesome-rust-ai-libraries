## Overview

sif-embedding is a Rust library implementing the Smooth Inverse Frequency (SIF) and unsupervised Random Walk SIF (uSIF) algorithms for producing sentence embeddings. Based on work from Arora et al. (ICLR 2017) and Ethayarajh (RepL4NLP 2018), it provides a lightweight, CPU-only alternative to DNN-based embedding models.

## Features

- **No GPU required**: Runs entirely on CPU.
- **Fast embeddings**: Processes ~80K sentences per second on a single core of Apple M2.
- **Reasonable evaluation scores**: While not matching SOTA models like SimCSE, performance is competitive for a simple baseline.
- **Multi-language support**: Evaluated on both English (STS-Benchmark, SICK) and Japanese (JSTS, JSICK) similarity tasks.
- **Integration examples**: Includes example code for use with Qdrant vector database via rust-client.

## Benchmarks

On an English Wikipedia dataset using one core of Apple M2 (24 GB RAM):
- ~80K sentences per second throughput.

## Evaluation Results (Spearman's Correlation)

### STS-Benchmark (English)

| Model | Train | Dev | Test | Avg |
|---|---|---|---|---|
| sif_embedding::Sif | 65.2 | 75.3 | 63.6 | 68.0 |
| sif_embedding::USif | 68.0 | 78.2 | 66.3 | 70.8 |
| princeton-nlp/unsup-simcse-bert-base-uncased | 76.9 | 81.7 | 76.5 | 78.4 |
| princeton-nlp/sup-simcse-bert-base-uncased | 83.3 | 86.2 | 84.3 | 84.6 |

### JSTS/JSICK (Japanese)

| Model | JSICK (test) | JSTS (train) | JSTS (val) | Avg |
|---|---|---|---|---|
| sif_embedding::Sif | 79.7 | 67.6 | 74.6 | 74.0 |
| sif_embedding::USif | 79.7 | 69.3 | 76.0 | 75.0 |
| cl-nagoya/unsup-simcse-ja-base | 79.0 | 74.5 | 79.0 | 77.5 |
| cl-nagoya/sup-simcse-ja-base | 82.8 | 77.9 | 80.9 | 80.5 |

## Use Cases

- Applications where DNN-based sentence embeddings are too slow
- Environments without GPU access
- Quick baseline sentence embeddings for development and prototyping

## Licensing

Dual-licensed under either:
- Apache License, Version 2.0
- MIT license