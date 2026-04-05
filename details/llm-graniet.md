## Overview

LLM is a Rust crate that provides a unified interface for interacting with multiple LLM backends through a consistent builder-pattern API, similar to the Stripe developer experience. It allows developers to use OpenAI, Anthropic (Claude), Ollama, DeepSeek, xAI, Phind, Groq, OpenRouter, Cohere, Mistral, Hugging Face, Google, and ElevenLabs through a single entry point.

## Features

- **Multi-backend support**: Manage OpenAI, Anthropic, Ollama, DeepSeek, xAI, Phind, Groq, OpenRouter, Cohere, ElevenLabs, Google, and Mistral through a single entry point
- **Multi-step chains**: Create multi-step prompt chains with different backends at each step
- **Templates**: Create complex prompts with variables
- **Builder pattern**: Configure LLM parameters (model, temperature, max_tokens, timeouts) with simple method calls
- **Chat & Completions**: Two unified traits (ChatProvider and CompletionProvider) covering most use cases
- **Extensible**: Easy to add new backends
- **Validation**: Add validation to requests to ensure output matches expectations
- **Resilience**: Retry/backoff with exponential backoff and jitter
- **Evaluation**: Score LLM outputs; parallel evaluation of multiple providers
- **Function calling**: Use tools/add function calling to LLM requests
- **REST API**: Serve any LLM backend as a REST API with OpenAI-standard format
- **Vision**: Use images in LLM requests
- **Reasoning**: Add reasoning capabilities to requests
- **Structured output**: Request structured output based on a provided JSON schema
- **Speech-to-text**: Transcribe audio to text
- **Text-to-speech**: Transcribe text to audio (including Rodio playback integration)
- **Memory**: Store and retrieve conversation history with sliding window and shared memory support
- **Agentic**: Build reactive agents that cooperate via shared memory with configurable triggers, roles, and validation
- **CLI tool**: Command-line interface for interacting with different LLM models (`cargo install llm`)

## Installation

```toml
[dependencies]
llm = { version = "1.2.4", features = ["openai", "anthropic", "ollama", "deepseek", "xai", "phind", "google", "groq", "mistral", "elevenlabs"] }
```

## Pricing

Free and open-source.