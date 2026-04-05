## Overview

Vox is a local-first voice AI framework written in Rust. It provides speech-to-text, text-to-speech, and voice chat pipelines that run entirely on-device — no API keys, no cloud, and no data leaving the machine. The framework uses a pluggable architecture with trait-based backends for VAD (Voice Activity Detection), STT (Speech-to-Text), and TTS (Text-to-Speech).

## Pipeline

```
Mic → VAD (Silero) → STT (Whisper/Sherpa/Streaming) → Your Code → TTS (Kokoro/Piper/Chatterbox) → Speaker
```

Audio is captured via cpal, resampled to 16kHz mono, and fed frame-by-frame to VAD. On speech end, the utterance goes to STT. A callback receives the text and a VoxContext for optional TTS reply.

## Features

- **Speech-to-Text** — Whisper (tiny to medium), Sherpa-ONNX (SenseVoice, Zipformer, Paraformer), or streaming Sherpa for real-time partial transcription
- **Text-to-Speech** — Kokoro (50+ voices), Piper (multilingual), Pocket (pure Rust, edge-ready), or Chatterbox (voice cloning)
- **Voice Chat** — Talk to any Ollama LLM and hear spoken responses
- **Web Interface** — Browser UI at http://localhost:3000 with real-time mic transcription, TTS synthesis, voice chat, and status dashboard (via `vox serve`)
- **Python Bindings** — Same pipeline available from Python via PyO3
- **HTTP/WebSocket API** — REST endpoints and streaming WebSocket for integration into any stack
- **Fully Local** — No API keys, no cloud dependency
- **Pluggable Backends** — Swap VAD, STT, or TTS engines via traits

## Supported Models

| Component | Model | Size | Notes |
|-----------|-------|------|-------|
| VAD | Silero VAD v5 | 2MB | Speech detection |
| STT | Whisper tiny.en | 75MB | Fast, English |
| STT | Whisper base.en | 142MB | Better accuracy |
| STT | Whisper small.en | 466MB | High accuracy |
| STT | Whisper medium.en | 1.5GB | Highest accuracy |
| STT | Sherpa SenseVoice | 230MB | Multilingual (zh/en/ja/ko/yue) |
| STT | Sherpa Streaming Zipformer | 27MB | Real-time partial results |
| TTS | Kokoro | 310MB | 50+ voices |
| TTS | Piper | 63MB/voice | Multilingual (en/de/es/fr/zh) |
| TTS | Pocket | 82MB | Pure Rust, edge/embedded |
| TTS | Chatterbox | 350MB | Voice cloning |

## Feature Flags

| Flag | Default | Description |
|------|---------|-------------|
| cli | no | CLI binary (vox listen, vox speak, vox chat, vox serve) |
| server | no | HTTP/WebSocket API server |
| whisper | yes | Whisper STT via whisper-rs |
| silero | yes | Silero VAD via ONNX Runtime |
| sherpa | no | Sherpa-ONNX STT (SenseVoice, Zipformer, streaming) |
| piper | no | Piper TTS (multilingual) |
| kokoro | no | Kokoro TTS (50+ voices) |
| pocket | no | Pocket TTS (pure Rust) |
| pocket-metal | no | Pocket TTS with Apple Metal GPU |
| chatterbox | no | Chatterbox TTS (voice cloning) |
| chatterbox-coreml | no | Chatterbox with CoreML (macOS) |
| tts | no | Audio playback for TTS output |

## Platform Support

| Platform | Status |
|----------|--------|
| macOS (Apple Silicon) | Tested |
| macOS (Intel) | Tested |
| Linux (x86_64) | CI tested |
| Windows (x86_64) | CI tested |

## Performance (Apple M1 MacBook Pro)

| Metric | Value |
|--------|-------|
| VAD frame latency | ~1ms per 32ms frame |
| Whisper STT (3s utterance) | ~200ms |
| Streaming STT (per chunk) | <1ms (0.03x real-time) |
| End-to-end (speech end to text) | ~250ms |
| Piper TTS ("Hello world") | ~200ms |
| Chatterbox TTS ("Hello world") | ~2s |
| Memory (idle pipeline) | ~150MB |

API: WebSocket streaming at ws://localhost:3000/v1/listen sends PCM f32 LE frames at 16kHz mono and receives JSON events in real time (speech_start, partial, transcript, speech_end). REST endpoints available for /v1/transcribe and /v1/synthesize.

## Installation

```bash
# Install CLI
cargo install --git https://github.com/mrtozner/vox --features cli

# Transcribe speech from microphone
vox listen

# Text-to-speech
cargo install --git https://github.com/mrtozner/vox --features cli,kokoro
vox speak "Hello from Vox!"

# Voice chat with Ollama
vox chat --llm llama3.2
```

Models auto-download on first run.

## License

MIT OR Apache-2.0