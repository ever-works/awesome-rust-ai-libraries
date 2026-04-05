## Overview

WONNX is a fully native Rust implementation of an ONNX inference runtime based on wgpu (WebGPU). Unlike wrapper bindings to C++ libraries, it implements ONNX operators entirely in Rust, enabling model execution both in native applications and via WebAssembly in web browsers.

## Features

- 100% Rust ONNX inference runtime with no C++ FFI
- Built on wgpu (WebGPU) for GPU-accelerated inference
- Runs natively and in WebAssembly/browser environments
- Supports a growing set of ONNX operators
- Zero external runtime dependencies beyond wgpu

## Status

Active development.