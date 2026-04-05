## Overview

RLtools is a fast, portable deep reinforcement learning library written in C++ designed for continuous control tasks. It emphasizes performance, portability across devices (from data center GPUs to microcontrollers), and ease of use for implementing custom RL algorithms and environments.

## Algorithms

| Algorithm | Examples |
|-----------|----------|
| TD3 | Pendulum, Racing Car, MuJoCo Ant-v4, Acrobot |
| PPO | Pendulum, Racing Car, MuJoCo Ant-v4 (CPU/CUDA) |
| Multi-Agent PPO | Bottleneck |
| SAC | Pendulum (CPU/CUDA), Acrobot |

## Features

- Header-only C++17 library with compile-time configuration
- Fast training: Pendulum benchmarks show ~4s on M3, ~6s on Zen 5, ~18s on M1
- CUDA support for GPU acceleration
- CPU backend support via Apple Accelerate (macOS) and OpenBLAS (Linux)
- Python bindings available via PyPI (`pip install rltools`)
- Interactive C++ notebook documentation
- Embedded platform inference support

## Platform Support

### Inference & Training
- iOS
- Teensy

### Inference Only
- Crazyflie
- ESP32
- PX4

## Performance

- Benchmarks for Pendulum swing-up training across different RL libraries (PPO and SAC)
- Device-agnostic training benchmarks (SAC across CPU architectures)
- Microcontroller inference frequency benchmarks for two-layer [64, 64] fully-connected neural networks

## Python Interface

```python
from rltools import SAC
import gymnasium as gym
from gymnasium.wrappers import RescaleAction

sac = SAC(env_factory)
state = sac.State(seed)
finished = False
while not finished:
    finished = state.step()
```

## Getting Started

Clone the repository and build a Zoo example:

```bash
g++ -std=c++17 -O3 -ffast-math -I include src/rl/zoo/l2f/sac.cpp
./a.out 1337  # run with seed
./tools/serve.sh  # visualize results
```

## Documentation

Interactive C++ notebooks available at [docs.rl.tools](https://docs.rl.tools). Run locally via Docker:

```bash
docker run -p 8888:8888 rltools/documentation
```

## Notable Projects

- **Learning to Fly in Seconds**: GitHub / arXiv / YouTube / IEEE Spectrum
- **Data-Driven System Identification of Quadrotors Subject to Motor Delays**: GitHub / arXiv / YouTube

## Pricing

Free and open-source.