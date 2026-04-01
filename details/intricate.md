## Overview

Intricate is a GPU-accelerated library for creating, training, and running neural networks in safe Rust code, leveraging OpenCL for computations on CPU or GPU devices.

## Architecture

- **Models**: Containers for a list of layers, orchestrating forward and backward passes.
- **Layers**: Implement forward pass and backpropagation methods (`optimize_parameters`, `compute_gradients`, `apply_gradients`, `compute_loss_to_input_derivatives`). Examples include Dense layers and activation layers like TanH.
- **Optimizers**: Update layer parameters and gradients, e.g., Basic optimizer.
- **Loss Functions**: Compute model error, e.g., MeanSquared.

## Features

- Mini-batch gradient descent training with configurable epochs, batch size, accuracy computation, and halting conditions.
- OpenCL initialization for device-agnostic acceleration.
- Model save/load using the savefile crate.
- Datasets like MNIST with automatic download.

## Usage Example (XOR)

```rust
use intricate::{Model, layers::{Dense, activations::TanH}, loss_functions::MeanSquared, optimizers, utils::{setup_opencl, DeviceType}, types::{TrainingOptions, HaltingCondition}};

let training_inputs = vec![vec![0.0, 0.0], vec![0.0, 1.0], vec![1.0, 0.0], vec![1.0, 1.0]];
let expected_outputs = vec![vec![0.0], vec![1.0], vec![1.0], vec![0.0]];

let mut layers = vec![Dense::new(2, 3), TanH::new(3), Dense::new(3, 1), TanH::new(1)];
let mut model = Model::new(layers);
let opencl_state = setup_opencl(DeviceType::CPU).unwrap();
model.init(&opencl_state).unwrap();

let mut loss = MeanSquared::new();
let mut optimizer = optimizers::Basic::new(0.1);
model.fit(&training_inputs, &expected_outputs, &mut TrainingOptions::new(&mut loss, &mut optimizer).set_epochs(10000).set_batch_size(4).should_compute_accuracy(true).unwrap().should_print_accuracy(true).unwrap().set_halting_condition(HaltingCondition::MinAccuracyReached(0.95)).unwrap()).unwrap();
```

## Saving and Loading

```rust
model.sync_data_from_buffers_to_host().unwrap();
save_file("model.bin", 0, &model).unwrap();
let loaded_model: Model = load_file("model.bin", 0).unwrap();
loaded_model.init(&opencl_state).unwrap();
```

## Pricing

Free and open-source under the MIT license.