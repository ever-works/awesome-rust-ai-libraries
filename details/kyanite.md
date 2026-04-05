## Overview

Kyanite is a neural network inference library written in Rust. It provides ONNX model support and includes a custom Graph IR for representing and optimizing computation graphs during inference.

## Features

- Neural network inference execution
- ONNX model loading and execution
- Custom Graph IR for computation graph representation
- CPU and CUDA backend support

## Backend Support

- CPU: Host-side inference computation
- CUDA: NVIDIA GPU acceleration via manual CUDA bindings

## Dependencies

- Manual bindings to CUDA

## Pricing

Free and open-source.al**: The CUDA executor and planner.
- **kn-runtime**: A wrapper around the other crates to allow selecting between CPU and GPU execution at runtime.
- **kn-python**: An experimental Python wrapper around the runtime crate, using PyO3.

## Graph IR

The Graph IR is an SSA-style directed acyclic graph where nodes are values with a shape, data type, and the operation that computes it. Operations include convolution, matmul, reshape, broadcast, slice, unary, binary, reduce, softmax, and more. The graph can be constructed directly in code using the graph builder API, or loaded from ONNX files via the ONNX loader.

## Optimizer

The optimizer applies the following transformations:

- Constant folding
- Fusing consecutive affine operations (bias, scale, batchnorm) into a single bias+scale operation
- Fusing consecutive clamping operations (relu, min, max) into a single min+max operation
- Strength reduction: replacing division by a constant with multiplication by the inverse
- Recognizing the layernorm template (reduce, subtract, power, reduce, divide) and replacing it with the layernorm operator

## CPU Executor

A simple CPU executor that directly runs each operation, using BLAS routines for matmuls and im2col for convolutions. Serves as the baseline for unit tests verifying GPU executor correctness.

## CUDA Executor

The CUDA executor processes graphs through a CUDA Planner that:

- Determines memory layout of tensors (strides and memory offsets), handling reshape, broadcast, and stride operations implicitly
- Reuses buffers where possible to minimize total memory usage
- Decides which cuDNN/cuBLAS operations to run for convolutions and matmuls, fusing operations where possible (e.g., "convolution + residual + bias + relu" into a single cuDNN operation)
- Compiles custom kernels for remaining operations using an autokernel framework based on NVRTC (Runtime Compilation), handling scalar operations, reduce, softmax, layernorm, and gather

The planner step is separated from execution so the expensive planning step only needs to be carried out once per network architecture.

## System Requirements

The project has been tested with CUDA v12.2 and cuDNN version v8.9.5. CUDA libraries (CUDA, cuBLAS, NVRTC) and cuDNN must be installed manually.

## Licensing

Open-source under the Apache 2.0 license.