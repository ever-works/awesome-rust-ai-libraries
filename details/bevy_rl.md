## Overview

bevy_rl is a Rust library that brings Reinforcement Learning Gym environments to the Bevy game engine. It allows developers to train AI agents that can learn from screen pixels or defined observation states within Bevy-based simulations and games.

## Features

- **OpenAI Gym Interface** — Set of APIs implementing standard Gym operations: reset, step, render, and associated simulator states
- **Multi-Agent Support** — Train multiple agents simultaneously, each with its own camera handle
- **Pixel Rendering to RAM** — Renders screen pixels from GPU memory to RAM buffers for training agents with raw visual input
- **REST API** — HTTP endpoints to control agents, retrieve state observations, reset environments, and step through simulations
- **Event-Driven Architecture** — Communicates with the environment through events (EventReset, EventControl, EventPause) for clean simulation lifecycle management

## REST API Endpoints

| Endpoint | Method | Description |
|---|---|---|
| `/visual_observations` | GET | Retrieve camera pixel data |
| `/state` | GET | Get current environment state |
| `/reset` | GET | Reset the environment to initial state |
| `/step` | GET | Step simulation with action payload (`?payload=ACTION`) |

All endpoints are served on `localhost:7878` by default.

## AIGymState API

Key methods available on the `AIGymState` resource:

| Method | Description |
|---|---|
| `set_reward(agent_index, score)` | Set reward for a specific agent |
| `set_terminated(agent_index, result)` | Set termination status for an agent (useful for multi-agent) |
| `reset()` | Reset bevy_rl state and clear exported state history |
| `set_env_state(state)` | Set current serialized environment state |
| `send_reset_result(result)` | Send reset result to REST API for synchronization |

## Configuration

The `AIGymState` is configured with settings including:
- Screen width and height (must exceed 256 to avoid wgpu panic)
- Number of agents (each gets a camera handle)
- Render-to-buffer toggle for pixel export
- Pause interval for simulation control (e.g., 0.01 for 100 Hz)

## Examples

- **bevy_rl_shooter** — Example FPS project demonstrating RL agent training
- **bevy_quadruped_neural_control** — Quadruped locomotion using bevy_mujoco and bevy_rl

## Licensing

Open-source project. Check the repository for license details.