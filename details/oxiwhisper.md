## Overview

OxiWhisper is a pure Rust implementation of OpenAI's Whisper speech-to-text model. It has zero C/C++ dependencies and provides complete inference engine capabilities including GGML model loading, quantized inference, SIMD-accelerated computation, streaming API, and subtitle export.

## Features

### Inference

- GGML model loading (ggml-tiny.bin, ggml-base.bin, etc.) and ONNX model loading
- Q4_0, Q5_0, and Q8_0 quantized inference with dequantize-on-the-fly GEMV
- SIMD-accelerated dot products: AVX2+FMA (x86_64), NEON (aarch64), simd128 (WASM)
- matrixmultiply::sgemm for attention QK^T and scores@V with stride-based transpose
- Arc copy-on-write KV cache for beam search
- Zero-copy tensor reshape, in-place activations (GELU, softmax, layer norm)
- Pre-allocated inference buffers for latency-sensitive applications

### Decoding

- Greedy decoding, beam search (configurable width), temperature sampling
- Top-k and nucleus (top-p) filtering
- Automatic language detection (99 languages)
- Timestamp segments with start/end times and per-segment confidence
- Token-level log-probabilities
- Initial prompt conditioning for domain-specific vocabulary
- Suppress tokens to block specific token IDs
- No-repeat-ngram penalty to prevent hallucination loops
- Compression ratio filtering for hallucination detection
- Previous context conditioning for cross-chunk coherence

### Audio & Analysis

- Pure Rust WAV loader (PCM 8/16/24/32-bit, IEEE float, multi-channel)
- Automatic resampling to 16 kHz mono
- Voice Activity Detection with adaptive noise floor thresholding
- VAD-aware chunking for long audio at silence boundaries
- Word-level timestamps via DTW cross-attention alignment
- Log-mel spectrogram computation using OxiFFT

### API

- `transcribe()`, `transcribe_segmented()`, `transcribe_timed()`
- `transcribe_long()`, `transcribe_long_segmented()`, `transcribe_long_with_vad()`
- `transcribe_batch()` for multiple audio clips
- `transcribe_to_srt()`, `transcribe_to_vtt()` subtitle export
- `stream()` returning StreamTranscriber for real-time processing
- `encoder_output()` for embedding extraction
- `mel_spectrogram()` for audio analysis
- `model_stats()` for memory/parameter statistics
- Optional serde feature for JSON serialization via `to_json()`

## Supported Models

| Model  | Parameters | Size (f32) | Size (Q4_0) | Size (Q5_0) |
|--------|-----------|------------|-------------|-------------|
| tiny   | 39M       | ~150 MB    | ~40 MB      | ~48 MB      |
| base   | 74M       | ~290 MB    | ~80 MB      | ~95 MB      |
| small  | 244M      | ~950 MB    | ~250 MB     | ~300 MB     |
| medium | 769M      | ~3.0 GB    | ~800 MB     | ~950 MB     |
| large  | 1.5B      | ~6.0 GB    | ~1.5 GB     | ~1.8 GB     |

## Feature Flags

| Feature | Description | Default |
|---------|-------------|--------|
| timing  | Print per-phase timing diagnostics to stderr | off |
| onnx    | Enable ONNX model loading via oxionnx | off |
| serde   | JSON serialization for TranscribeResult, etc. | off |

## Examples

- `transcribe` — Simple CLI transcription
- `streaming` — Real-time streaming with StreamTranscriber
- `batch_transcribe` — Multi-file batch transcription
- `bench` — Performance benchmarking with RTF reporting
- `profile_attention` — Attention kernel profiling (sgemm vs tiled)

## License

Apache-2.0