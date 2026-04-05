## Overview

diffusion-rs is a high-performance Rust library designed for blazingly fast inference of diffusion models. It supports quantization, DDUF format, and model offloading for efficient AI image generation workloads.

## Features

- High-speed diffusion model inference
- Quantization support for reduced memory and compute requirements
- DDUF (Diffusion Unified Format) model format support
- Model offloading for handling large models
- Multi-backend hardware acceleration

## Backend Support

- CPU: Host-side computation
- CUDA: NVIDIA GPU acceleration via cudarc
- Metal: Apple GPU acceleration
- Additional backends supported

## Dependencies

- cudarc: CUDA bindings
- intel-mkl-src: Intel MKL for CPU optimization
- accelerate-sr: Apple Accelerate framework
- metal: Metal GPU framework
- gemm: General matrix multiplication

## Pricing

Free and open-source.