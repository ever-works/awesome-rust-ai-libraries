## Overview

Llama Moonlight is part of the Llama Ecosystem, a collection of modular, interoperable Rust crates designed for sophisticated web automation, scraping, and AI integration. Each crate focuses on solving a specific problem while working seamlessly with the others.

## Core Crate: llama-moonlight

A powerful browser automation framework with MLX and Llama integration.

- Multi-browser support (Chrome, Firefox, Safari)
- Headless and headed modes
- Network interception
- Screenshots and video recording
- Stealth mode via llama-headers-rs integration
- AI integration for intelligent automation

## Companion Crates

### llama-headers-rs
A sophisticated HTTP header generation library for realistic browser emulation.
- Realistic browser fingerprinting
- User-agent generation
- Language and locale-aware headers
- Referer generation
- Modern security-related headers

### llama-cloudflare (Coming Soon)
Tools for bypassing Cloudflare and other anti-bot protections.
- TLS fingerprint customization
- JavaScript challenge solver
- Proxy rotation
- Rate limiting and request pacing

### llama-mlx (Coming Soon)
MLX integration for AI-powered automation.
- MLX model loading and inference
- Computer vision for visual analysis
- Text recognition and processing
- Decision making for automation scenarios

### llama-agents (Coming Soon)
AI agent abstractions for automation tasks.
- Autonomous web agent framework
- Task planning and execution
- LLM integration
- Memory and context management

## Getting Started

```rust
use llama_moonlight_core::{Moonlight, BrowserType};

#[tokio::main]
async fn main() -> Result<(), Box<dyn std::error::Error>> {
    let moonlight = Moonlight::new().await?;
    let browser_type = moonlight.browser_type("chromium").unwrap();
    let browser = browser_type.launch().await?;
    let context = browser.new_context().await?;
    let page = context.new_page().await?;
    page.goto("https://example.com").await?;
    page.screenshot("example.png").await?;
    Ok(())
}
```

## Use Cases

- Web Scraping: Extract data from websites while avoiding bot detection
- Browser Automation: Automate UI testing and web interactions
- Data Collection: Gather information across multiple sites
- Security Testing: Test web applications for security vulnerabilities
- AI-Powered Automation: Combine browser automation with AI for intelligent decision-making

## Documentation

Comprehensive documentation is available for each crate. Generate documentation with:
```
cargo doc --no-deps --open
```

## Pricing

Free and open-source under Apache 2.0 or MIT license (at your option).