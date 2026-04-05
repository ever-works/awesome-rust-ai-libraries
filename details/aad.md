## Overview

aad is a pure Rust automatic differentiation library that uses reverse-mode adjoint differentiation to efficiently compute gradients for scalar-valued functions with many inputs.

## Features

- **Supports both f32 and f64**: Generic implementation works with any floating-point type implementing `num_traits::Float`.
- **Reverse-mode autodiff**: Efficiently compute gradients for scalar-valued functions with many inputs.
- **Operator overloading**: Use standard mathematical operators with variables.
- **High performance**: Optimized for minimal runtime overhead. Benchmarks show competitive performance, often outperforming alternatives in gradient computation.
- **Type-agnostic functions**: Write generic mathematical code using the `FloatLike` trait.

## Usage

The library uses a `Tape` to track computations. Variables are created on the tape, mathematical operations build the computation graph, and gradients are computed via a reverse pass.

```rust
use aad::Tape;

fn main() {
    let tape = Tape::default();
    let [x, y] = tape.create_variables(&[2.0_f64, 3.0_f64]);
    let z = (x + y) * x.sin();
    println!("z = {:.2}", z.value());
    let gradients = z.compute_gradients();
    println!("Gradients: dx = {:.2}, dy = {:.2}",
             gradients.get_gradients(&[x, y]));
}
```

## Installation

Add to your `Cargo.toml`:

```toml
[dependencies]
aad = { version = "0.9.0" }
```

## Benchmarks

Run benchmarks with:

```bash
cargo bench --features benchmarks
```

## Pricing

Free and open-source under the MIT License.