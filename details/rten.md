## Overview

RTen (the Rust Tensor engine) is a machine learning runtime that supports models in ONNX format. It enables taking ML models trained in Python using frameworks such as PyTorch and running them in Rust applications. In addition to ML inference, the project provides supporting libraries for common pre-processing and post-processing tasks across various domains.

## Goals

- Provide a small and efficient neural network runtime for running PyTorch-created models in Rust
- Be easy to compile and run on a variety of platforms, including WebAssembly
- End-to-end Rust: the project and all required dependencies are written in Rust, simplifying build and deployment

## Supported Devices

- CPU inference only (no GPU)
- SIMD acceleration via AVX2, AVX-512, Arm Neon, and WebAssembly SIMD
- Multi-threaded inference by default (defaults to the number of physical/performance cores), customizable

## Supported Models and Operators

- Supports most standard ONNX operators
- Float32 weights supported
- Quantized models with int8 or uint8 weights supported
- Quantized models can leverage CPU features such as VNNI (x86) and UDOT / i8mm (Arm) for better performance

## Model Formats

- **ONNX**: Load models in ONNX format directly (supported since v0.23)
- **RTen (.rten)**: Custom format offering faster load times and support for arbitrarily large models in a single file. Conversion available via rten-convert.

## WebAssembly Support

- Build the WebAssembly library via `make wasm` (requires WebAssembly SIMD, available since Chrome 91, Firefox 89, Safari 16.4)
- Non-SIMD builds available via `make wasm-nosimd` or both via `make wasm-all`
- Two approaches for JavaScript usage:
  1. Prepare model inputs in JavaScript, use RTen's built-in WebAssembly API to run the model and post-process in JS
  2. Create a Rust library with RTen that handles pre/post-processing on the Rust side, exposing a domain-specific WebAssembly API
- At runtime, `binaryName()` function can determine which build is supported

## Getting Started

- Clone the repository and run examples from the `rten-examples/` directory
- Many examples use Hugging Face's Optimum or Python tools to export ONNX models
- Quick-start example: export a ResNet-50 model and run image classification with a single `cargo run` command

## Licensing

Open-source project (see repository for license details).