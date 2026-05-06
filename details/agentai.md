# AgentAI

AgentAI is a Rust library designed to simplify the creation of AI agents. It leverages the GenAI library to interface with a wide range of popular Large Language Models (LLMs), making it versatile and powerful. Written in Rust, AgentAI benefits from strong static typing and robust error handling, ensuring reliable and maintainable code.

## Features

- Connect to any major LLM provider: Support for OpenAI, Anthropic, Gemini, Ollama, and other OpenAI-compatible APIs.
- Choose the right model for the job: Flexibly select the best-suited model for each step in your agent's workflow.
- Build custom tools with ease: A simple interface for creating and managing your own tools using the ToolBox.
- MCP Server Support: Leverage existing solutions based on the Model-Context-Protocol, eliminating the need to build agent tools from scratch.
- Structured Output: No need to parse raw text from model, just provide structure, and AI agent will provide response in defined format.

## Installation

To add the AgentAI crate to your project, run the following command in your project's root directory:

```bash
cargo add agentai MM
```

This command adds the crate and its dependencies to your project.

## Feature Flags

Available features for agentai crate. To enable any of these features, you need to enter this command:

```bash
cargo add agentai -F <feature-name>
```

Features list:

- `mcp-client` (enabled by default) — Enables experimental support for Agent Tools based on MCP Servers
- `macros` (enabled by default) — Enables support for macro `#[toolbox]`
- `tools-buildin` (enabled by default) — Enables support for builtin tools
- `tools-web` (enabled by default) — Enables support for web tools

## Usage

Here is a basic example of how to create an AI agent using AgentAI:

```rust
use agentai::Agent;

#[tokio::main]
async fn main() -> anyhow::Result<()> {
    let mut agent = Agent::new("You are a useful assistant");
    let answer: String = agent.run("gpt-4o", "Why is the sky blue?", None).await?;
    println!("Answer: {}", answer);
    Ok(())
}
```

## Examples

For more examples, check out the examples directory. To run an example, use the following command, replacing `<example_name>` with the name of the example file (without the .rs extension):

```bash
cargo run --example <example_name>
```

For instance, to run the simple example:

```bash
cargo run --example simple
```

## Documentation

Full documentation is available on [docs.rs](https://docs.rs/agentai).

## Contributing

Contributions are welcome! Please see our CONTRIBUTING.md for more details.

## License

This project is licensed under the MIT License. See the LICENSE file for details.

## Acknowledgements

Special thanks to the creators of the GenAI library for providing a robust framework for interfacing with various LLMs.
