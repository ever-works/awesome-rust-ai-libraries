## Overview

zyx is a tensor library for machine learning in Rust that focuses on efficient tensor operations with lazy execution and automatic differentiation, supporting multiple GPU backends.

## Features

- Tensor operations for machine learning workloads
- Lazy execution model for computation optimization
- Automatic differentiation (AutoDiff) for gradient-based training
- Multi-backend GPU support: CUDA, OpenCL, WGPU

## Backend Support

- CUDA: NVIDIA GPU acceleration via manual CUDA bindings
- OpenCL: Cross-platform GPU acceleration via manual OpenCL bindings
- WGPU: WebGPU-based acceleration via wgpu and vulkano

## Dependencies

- wgpu: WebGPU implementation
- vulkano: Vulkan bindings
- Manual bindings to CUDA, OpenCL, and HSA

## Pricing

Free and open-source.