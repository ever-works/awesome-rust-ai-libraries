## Overview

qwen3_tts_rs is a Rust implementation of the Qwen3 Text-to-Speech (TTS) model inference engine. It provides three cross-platform CLI tools suitable for agentic skills for AI agents and bots: `tts` for speech generation with named speaker voices, `voice_clone` for cloning voices from reference audio, and `api_server` for an OpenAI-compatible HTTP API server.

## Backends

- **libtorch** — via the `tch` crate, cross-platform with optional CUDA support
- **MLX** — Apple Silicon native via Metal GPU

## CLI Tools

### tts — Text-to-Speech

Generates speech from text using named speaker voices (CustomVoice model).

- Supports English, Chinese, Japanese, and Korean
- Output: 24 kHz, 16-bit PCM WAV
- Available speakers: Vivian, Serena, Ryan, Aiden, Uncle_fu, Ono_anna, Sohee, Eric, Dylan
- Voice style instructions available for 1.7B models (e.g., "Speak in an urgent and excited voice")

### voice_clone — Voice Cloning

Clones a voice from reference audio using the Base model in ICL (In-Context Learning) mode.

- Reference audio must be mono 24 kHz 16-bit WAV
- Optional transcript of reference audio enables ICL mode for higher quality
- Output: 24 kHz, 16-bit PCM WAV

### api_server — OpenAI-Compatible API

HTTP API server compatible with OpenAI's `/v1/audio/speech` endpoint.

- **Endpoints**: `POST /v1/audio/speech`, `GET /v1/models`, `GET /health`
- Supports multiple response formats: wav, pcm, mp3, flac, ogg, opus
- Speed multiplier: 0.25–4.0x
- SSE streaming support with base64-encoded PCM chunks
- Voice cloning via API with `audio_sample` and `audio_sample_text` fields
- Voice name mapping: alloy→serena, echo→ryan, fable→vivian, onyx→eric, nova→ono_anna, shimmer→sohee

## Architecture

Text → Tokenizer → Dual-stream Embeddings → TalkerModel (28-layer Transformer) → codec_head → Code 0 → CodePredictor (5-layer Transformer) → Codes 1-15 → Vocoder → 24kHz Waveform

## Performance

Tested on Apple M4 Mac with MLX backend. Real-Time Factor (RTF) values:

- **0.6B CustomVoice**: ~1.57x–1.85x RTF (API non-streaming), ~1.70x–2.38x (CLI)
- **1.7B CustomVoice**: ~2.74x–3.05x RTF (API non-streaming), ~2.93x–3.41x (CLI)
- Lower RTF means faster than real-time; the 0.6B model achieves faster-than-real-time synthesis

## Library Usage

Available as a Rust crate on crates.io:

```toml
[dependencies]
qwen3-tts-rs = "0.2"
# Or for MLX backend:
# qwen3-tts-rs = { version = "0.2", default-features = false, features = ["mlx"] }
```

## Pricing

Free and open-source under the Apache-2.0 license.

## Credits

Based on the original Python implementation by the Alibaba Qwen team.