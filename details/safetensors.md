## Overview

SafeTensors is the Rust implementation of the safetensors format, a safe, zero-copy serialization format for storing model weights. It was created as a replacement for PyTorch's pickle-based weight storage, eliminating security risks associated with arbitrary code execution during deserialization.

## Features

- Safe, zero-copy format for storing model weights
- Replaces PyTorch pickle-based serialization
- Eliminates deserialization security vulnerabilities
- Supported by Hugging Face and widely adopted
- Fast reading with memory mapping support

## Status

Active development.