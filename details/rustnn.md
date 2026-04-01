## Overview

RustNN generates fully connected multi-layer artificial neural networks trained using backpropagation in an incremental training mode.

## Features

- Network creation via `NN::new(&[layer_sizes])`
- Training with `train(&examples)` supporting options like:
  - `halt_condition(HaltCondition::Epochs(n))`
  - `log_interval(Some(n))`
  - `momentum(f64)`
  - `rate(f64)`
- Inference via `run(inputs)`

## Example

```rust
use nn::{NN, HaltCondition};

let examples = [
    (vec![0f64, 0f64], vec![0f64]),
    (vec![0f64, 1f64], vec![1f64]),
    (vec![1f64, 0f64], vec![1f64]),
    (vec![1f64, 1f64], vec![0f64]),
];

let mut net = NN::new(&[2, 3, 1]);
net.train(&examples)
    .halt_condition(HaltCondition::Epochs(10000))
    .log_interval(Some(100))
    .momentum(0.1)
    .rate(0.3)
    .go();
```

## Resources

- Crate: https://crates.io/crates/nn
- Documentation: https://jackm321.github.io/RustNN/doc/nn/

## Pricing

Free and open-source under Apache-2.0 license.