## Overview

Rapid-NN is a lightweight and fast neural network library written in Rust, designed to be easy to use for building and training custom neural network architectures.

## Features

- Support for multi-layer neural networks with customizable architectures
- Multiple activation functions: `None`, `LeakyReLU`, `Linear`
- Configurable learning rates for training
- Standard train/predict workflow with epoch-based training loops
- Mean error tracking during training for monitoring convergence
- Simple API with `NeuralNetwork::new()`, `add_layer()`, `train()`, and `predict()` methods

## Usage

The library provides a straightforward API:

- Create a network with `NeuralNetwork::new()`
- Add layers with `add_layer(neurons, activation_function, learning_rate_parameter)` — input, hidden, and output layers are all configured the same way
- Train with `nn.train(inputs, targets, learning_rate)` which returns the error for each sample
- Predict with `nn.predict(inputs)`

## Example

```rust
use rapid_nn::{ActivationFunction, NeuralNetwork};

let mut nn = NeuralNetwork::new();
nn.add_layer(3, ActivationFunction::None, 0.0);       // Input layer
nn.add_layer(5, ActivationFunction::LeakyReLU, 0.1);  // Hidden layer
nn.add_layer(2, ActivationFunction::Linear, 0.1);      // Output layer

for epoch in 1..=epochs {
    for (inputs, targets) in &training_data {
        let error = nn.train(inputs, targets, 0.01);
    }
}

let output = nn.predict(&inputs);
```

## Pricing

Free and open-source under its license.