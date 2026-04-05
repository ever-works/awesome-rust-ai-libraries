## Overview

candle2 is a minimalist ML framework for Rust with a syntax that closely mirrors PyTorch. It is designed to reduce binary size, enabling serverless (CPU) and small, fast deployments without the overhead of Python or the large runtime of PyTorch.

## Structure

- **candle-core**: Core ops, devices, and Tensor struct definition.
- **candle-nn**: Facilities to build real models (neural network layers, optimizers, etc.).
- **candle-examples**: Real-world examples demonstrating practical usage.
- **candle-kernels**: Custom CUDA kernels.

## Features

- **PyTorch-like syntax**: Familiar API for users coming from PyTorch, covering tensor creation, indexing, reshaping, matmul, arithmetic, device/dtype conversion, and model loading/saving.
- **CPU and CUDA backends**: Supports f16, bf16, and m16 precision formats.
- **WASM support**: Models can run directly in the browser via WebAssembly. Includes WASM examples for Whisper and llama2.c.
- **Model training**: Full training capabilities built in.
- **Distributed computing**: Supports NCCL for multi-GPU/multi-node workloads.
- **Pre-built model examples**: Llama, Llama-v2, Falcon, Bert, StarCoder, and Whisper.
- **Custom ops/kernels**: Embed user-defined operations such as flash-attention v2.
- **Safetensors integration**: Native support for loading and saving models in the safetensors format.
- **MKL support**: Optional Intel MKL integration for optimized CPU performance.

## Examples

The framework ships with runnable examples for popular models:

```
cargo run --example whisper --release
cargo run --example llama --release
cargo run --example falcon --release
cargo run --example bert --release
cargo run --example bigcode --release
```

To enable CUDA, add `--features cuda` to the command line.

## WASM Examples

Browser-based WASM examples are available for Whisper and llama2.c. They can be built with `trunk` or tried online.

## PyTorch Comparison

| PyTorch | Candle |
|---|---|
| `torch.Tensor([[1, 2], [3, 4]])` | `Tensor::new(&[[1f32, 2.], [3., 4.]], &Device::Cpu)?` |
| `torch.zeros((2, 2))` | `Tensor::zeros((2, 2), DType::F32, &Device::Cpu)?` |
| `tensor[:, :4]` | `tensor.i((.., ..4))?` |
| `tensor.view((2, 2))` | `tensor.reshape((2, 2))?` |
| `a.matmul(b)` | `a.matmul(&b)?` |
| `tensor.to(device="cuda")` | `tensor.to_device(&Device::Cuda(0))?` |
| `tensor.to(dtype=torch.float16)` | `tensor.to_dtype(&DType::F16)?` |

## Design Motivation

- Reduces binary size compared to PyTorch, enabling faster runtime creation on clusters.
- Removes Python from production workloads, avoiding GIL-related overhead.
- Integrates with the Hugging Face Rust ecosystem (safetensors, tokenizers).

## Pricing

Free and open-source.