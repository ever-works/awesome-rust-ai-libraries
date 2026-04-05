## Overview

Anda is an AI agent framework built with Rust, integrating with the Internet Computer Protocol (ICP) blockchain and decentralized Trusted Execution Environments (dTEEs). It aims to create a highly composable, autonomous, and perpetually memorizing network of AI agents, with the long-term vision of building a super AGI system.

## Key Features

- **Composability**: Agents specialize in domain-specific problems and can flexibly combine with other agents to tackle complex tasks, forming a robust problem-solving network.
- **Simplicity**: Designed for ease of use, enabling developers to quickly build powerful agents. Non-developers can also create agents through simple configurations.
- **Trustworthiness**: Agents operate within a decentralized trusted execution environment (dTEE) based on TEEs, ensuring security, privacy, and data integrity.
- **Autonomy**: Agents derive permanent identities and cryptographic capabilities from the ICP blockchain, combined with LLM reasoning and decision-making abilities for autonomous problem-solving.
- **Perpetual Memory**: Agent memory states are stored on the ICP blockchain and within the trusted storage network of dTEE, enabling continuous algorithm upgrades, knowledge accumulation, and evolution.

## Project Structure

- `anda_cli` — Command line interface for Anda engine server
- `anda_core` — Core library containing base types and interfaces
- `anda_engine` — Engine implementation for agent runtime and management
- `anda_engine_server` — HTTP server to serve multiple Anda engines
- `anda_web3_client` — Rust SDK for Web3 integration in non-TEE environments
- `agents/` — Various AI agent implementations (e.g., `anda_bot` — the Anda ICP example agent)
- `tools/` — Tool libraries including:
  - `anda_bnb` — Integration with the BNB Chain
  - `anda_icp` — Integration with the Internet Computer (ICP)
- `characters/` — Character examples
- `examples/` — AI agent examples

## Usage

- **For Non-Developers**: Follow agents in the `agents/` directory (e.g., `anda_bot`). A cloud service for one-click deployment is planned.
- **For Developers**: Add integration tools in `tools/`, create agent applications in `agents/`, or enhance the core engines `anda_core` and `anda_engine`.

## Related Projects

- **IC-TEE**: Makes Trusted Execution Environments (TEEs) work with the Internet Computer.
- **IC-COSE**: A decentralized configuration service with Signing and Encryption on the Internet Computer.

## Pricing

Free and open-source under the MIT License.