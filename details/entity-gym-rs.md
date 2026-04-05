## Overview

entity-gym-rs is a Rust crate that provides bindings for EntityGym, a Python library defining a novel entity-based abstraction for reinforcement learning environments. It enables Rust programs to be used as EntityGym training environments and to load and run neural network agents trained with the Entity Neural Network Trainer natively in pure Rust applications.

## Core Abstraction

The core abstraction is the `Agent` trait, which defines a high-level API for neural network agents to directly interact with Rust data structures. To use any Agent implementation, you derive the `Action` and `Featurizable` traits:

- **Action trait**: Allows a Rust type to be returned as an action by an Agent. Can be derived automatically for enums with only unit variants.
- **Featurizable trait**: Converts objects into a format that can be processed by neural networks. Derivable for most fixed-size structs and enums with unit variants. Agents can observe collections containing any number of Featurizable objects.

## Features

- Entity-based observation system for RL environments
- Derive macros for `Action` and `Featurizable` traits
- Load trained neural network agents from checkpoints
- Random agent support for baseline testing
- Pure Rust inference — no Python runtime required
- Integration with the Entity Neural Network Trainer ecosystem

## Examples

- **bevy_snake**: Demonstrates using entity-gym-rs in a Bevy game to train an agent to play Snake.
- **bevy-snake-ai**: More complex Bevy application with adversarial training of multiple agents to create AI opponents.

## Licensing

Open-source. See the repository for license details.