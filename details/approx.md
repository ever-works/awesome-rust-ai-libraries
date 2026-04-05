## Overview

The approx crate provides traits and macros for approximate floating-point comparisons, supporting machine epsilon, absolute difference, and relative epsilon comparisons.

## Features

- `assert_abs_diff_eq!`, `assert_relative_eq!`, and `assert_ulps_eq!` macros for test assertions
- `ApproxEq` trait for custom approximate equality implementations
- Support for absolute epsilon comparisons:
  ```rust
  use approx::assert_abs_diff_eq;
  use half::f16;
  
  let res = f16::from_f32(0.1) + f16::from_f32(0.2);
  assert_abs_diff_eq!(f32::from(res), 0.3, epsilon = 1e-3);
  ```
- ULPs (Units in the Last Place) comparison for precise float equivalence
- Works with complex number types via `Complex` trait implementations
- Compatible with `num-complex` and other numeric crates

## Use Cases

- Testing ML model outputs where exact float equality is unreliable
- Comparing model inference results across different backends
- Validating numerical optimization convergence

## Pricing

Free and open-source under the BSD-3-Clause license.