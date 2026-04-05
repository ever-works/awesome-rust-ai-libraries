## Overview

AgentFlow is a trainable multi-agent framework that coordinates four specialized modules through in-the-flow optimization, directly training the planner within multi-turn task loops using Flow-GRPO reinforcement learning.

## Architecture

The framework features four specialized modules:
- **Planner**: Coordinates task decomposition and strategy
- **Executor**: Carries out planned actions
- **Verifier**: Validates outputs and results
- **Generator**: Produces final outputs

## Key Features

- Flow-GRPO reinforcement learning for planner training
- In-the-flow optimization during multi-turn task loops
- Significant performance gains over monolithic approaches
- Smooth integration of any tools: math, coding, scientific, search, finance, news

## Pricing

Free and open-source.