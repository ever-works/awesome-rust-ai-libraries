## Overview

The half crate provides an f16 (half-precision float) type for Rust. It is useful in machine learning contexts for 16-bit model weights, quantization, and GPU inference where reduced precision can significantly reduce memory usage and improve throughput.

## Features

- IEEE 754-2008 compliant f16 (half-precision float) type
- Conversions between f16, f32, and f64
- Useful for 16-bit model weights and quantization
- Standard numeric trait implementations