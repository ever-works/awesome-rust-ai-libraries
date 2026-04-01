## Overview

NeuroRust is a neural network crate implemented in Rust, providing core components for model building and training.

## Features

- Optimizers: ADAM and SGD
- BLAS integration for efficient matrix operations
- Support for graph neural networks
- Autograd engine for automatic differentiation

## Usage Example

```rust
model = NN();

for _e in epochs:
    output = model.forward();
    loss_fn = loss_builder(target);
    loss = loss_fn(output);

    dL_da = loss.grad();
    for layer in model.layers:
        da_dz = layer.activation.grad();
        dz_dW = layer.output.weight_grad();

        layer.da_dW = da_dz * dz_dW;
        dL_da = layer.output.activation_grad();
```

## Licensing

Open-source (license details in repository).