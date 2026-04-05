## Overview

operators is a multi-hardware operator library providing neural network computation primitives that work across diverse hardware platforms, serving as a backend for projects like InfiniLM.

## Features

- Neural network computation operators
- Multi-hardware unified interface
- Support for diverse accelerator architectures
- Hardware abstraction layer

## Backend Support

- CPU: Host-side computation
- CUDA: NVIDIA GPU acceleration via cuda-driver
- OpenCL: Cross-platform GPU acceleration via clrt
- Ascend: Huawei Ascend NPU support via infinirt
- Cambricon: Cambricon MLU support

## Dependencies

- clrt: OpenCL runtime bindings
- infinirt: Ascend runtime bindings
- cuda-driver: CUDA driver interface

## Pricing

Free and open-source.