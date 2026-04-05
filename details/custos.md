## Overview

custos is a minimal OpenCL, CUDA, Vulkan, and host CPU array manipulation engine/framework for Rust. It provides a unified interface for hardware-accelerated array operations with support for automatic differentiation and lazy execution.

## Features

- Array manipulation engine across multiple hardware backends
- Automatic differentiation (AutoDiff) for gradient computation
- Lazy execution model for optimized computation graphs
- Multi-device support: CPU, OpenCL, CUDA, Vulkan, NNAPI

## Backend Support

- CPU: Host-side computation with libm
- OpenCL: OpenCL acceleration via min-cl
- CUDA: NVIDIA GPU acceleration via ash/vulkan bindings
- Vulkan: Cross-platform GPU acceleration via naga
- NNAPI: Android Neural Networks API support

## Dependencies

- min-cl: Minimal OpenCL bindings
- libm: Math library
- ash: Vulkan bindings
- naga: Shader translation library
- nnapi: Android NNAPI bindings

## Pricing

Free and open-source.