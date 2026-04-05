## Overview

Border is a reinforcement learning library in Rust that provides a modular architecture with multiple specialized crates. It is currently experimental and under development with an unstable API.

## Crates

### Core and Utility
- **border-core** — Provides basic traits and functions for environments and RL agents. License: MIT OR Apache-2.0
- **border-tensorboard** — Implements the TensorboardRecorder struct for writing records that can be visualized in Tensorboard, based on tensorboard-rs. License: MIT OR Apache-2.0
- **border-mlflow-tracking** — Provides MLflow tracking support for logging metrics during training via REST API. License: MIT OR Apache-2.0
- **border-async-trainer** — Defines traits and functions for asynchronous training of RL agents using multiple actors. Each actor runs a sampling process in parallel, where an agent interacts with an environment to collect samples for a shared replay buffer. License: MIT OR Apache-2.0
- **border** — Serves as a collection of examples. License: GPL-2.0-or-later

### Environment
- **border-py-gym-env** — Provides a wrapper for Gymnasium environments written in Python. License: MIT OR Apache-2.0
- **border-atari-env** — Implements a wrapper for atari-env, which is part of gym-rs. License: GPL-2.0-or-later
- **border-minari** — Provides a wrapper for Minari. License: MIT OR Apache-2.0

### Agent
- **border-tch-agent** — Implements RL agents based on tch, including Deep Q Network (DQN), Implicit Quantile Network (IQN), and Soft Actor-Critic (SAC). License: MIT OR Apache-2.0
- **border-candle-agent** — Implements RL agents based on candle. License: MIT OR Apache-2.0
- **border-policy-no-backend** — Implements policies that are independent of any deep learning backend, such as Torch. License: MIT OR Apache-2.0

## Examples

Example scripts are available in the examples directory and have been tested in Docker containers. Some training scripts require several days to complete, as tested on an Ubuntu 22.04 virtual machine.

## Docker

Docker configuration files for development and testing are available in the dev-border repository, supporting both aarch64 (e.g., M2 MacBook Air) and amd64 architectures.

## Licensing

Most crates are dual-licensed under MIT OR Apache-2.0. The border-atari-env and border (examples) crates are licensed under GPL-2.0-or-later.