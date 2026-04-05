## Overview

diffusers-rs is a Rust implementation equivalent to HuggingFace's diffusers Python library. It is built on top of the tch crate (Rust bindings for LibTorch) and enables running Stable Diffusion models natively in Rust.

## Supported Models

- Stable Diffusion v1.5
- Stable Diffusion v2.1

## Pipelines

### Text-to-Image
Generate images from text prompts using the Denoising Diffusion Implicit Model (DDIM) scheduler. The default scheduler produces images based on textual descriptions.

### Image-to-Image
Generate a new image based on an existing input image and a text prompt. This pipeline modifies the source image guided by the provided prompt.

### Inpainting
Modify specific regions of an existing image based on a text prompt and a mask image. Requires dedicated inpainting UNet weights.

### ControlNet
Control image generation using an input image as a structural guide. Uses Canny edge detection to extract edges from the input image, which then guides the Stable Diffusion generation process. Compatible with Stable Diffusion v1.5 weights.

## Weight Management

Weights are retrieved from HuggingFace model repositories and stored locally in the `data/` directory:

- **SD v2.1**: `bpe_simple_vocab_16e6.txt`, `clip_v2.1.safetensors`, `unet_v2.1.safetensors`, `vae_v2.1.safetensors`
- **SD v1.5**: `bpe_simple_vocab_16e6.txt`, `pytorch_model.safetensors`, `unet.safetensors`, `vae.safetensors`
- **ControlNet**: `controlnet.safetensors`
- **Inpainting**: `unet-inpaint.safetensors`

A Python script (`scripts/get_weights.py`) is provided to automate weight retrieval.

## Hardware Requirements

- **GPU**: Requires more than 8GB of VRAM for full GPU inference
- **CPU fallback**: Available but slower, can be enabled via `--cpu all` flag
- **Mixed mode (8GB GPU)**: Use FP16 UNet weights and place only the UNet on GPU, keeping VAE and CLIP on CPU

## Features

- DDIM (Denoising Diffusion Implicit Model) scheduler
- Multiple pipeline modes: text-to-image, image-to-image, inpainting, ControlNet
- Safetensors format for model weights
- CPU and GPU inference support
- Configurable via command-line flags using clap
- Edge-detection guided generation via ControlNet

## Pricing

Free and open-source under the Apache 2.0 license.