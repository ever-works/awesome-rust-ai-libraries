## Overview

Scorch is a simple neural network library in Rust focused on feedforward networks.

## Features

- Feedforward Neural Networks: Fully connected layers.
- Activation Functions: ReLU, Sigmoid, Tanh.
- Training Algorithms: Gradient descent with backpropagation.
- Modular Design: Easily extensible for custom functions and optimizers.

## Installation

Add to `Cargo.toml`:

```toml
[dependencies]
scorch = "0.1"
```

## Usage

Basic example training a network on XOR:

```rust
use scorch::{Layer, activation::{relu, sigmoid}, loss::MSE, NeuralNetwork};

let mut layers = vec![
    Layer::new(2, 4, relu),
    Layer::new(4, 1, sigmoid),
];

let mut nn = NeuralNetwork::new(&mut layers);

let inputs = vec![vec![0.0, 0.0], vec![0.0, 1.0], vec![1.0, 0.0], vec![1.0, 1.0]];
let targets = vec![vec![0.0], vec![1.0], vec![1.0], vec![0.0]];

nn.train(&inputs, &targets, 0.1, MSE, 10_000);

// Predictions
for test_input in inputs.iter() {
    let prediction = nn.forward(test_input);
    println!("Input: {:?}, Predicted: {:?}", test_input, prediction);
}
```

## License

MIT.