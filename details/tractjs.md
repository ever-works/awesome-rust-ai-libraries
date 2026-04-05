## Overview

tractjs is a JavaScript/WebAssembly library that enables running ONNX and TensorFlow neural network models directly in the browser and in Node.js. It is a thin wrapper around the tract Rust inference engine, compiled to WebAssembly for web execution.

## Features

- **ONNX and TensorFlow Support**: Run models exported from PyTorch, TensorFlow, and MXNet via the ONNX format
- **Extended Operator Support**: Supports operators not available in ONNX.js, including bidirectional LSTMs and recurrent networks
- **ONNX-ML Models**: Supports decision tree classifiers and other ONNX-ML model types
- **Single-file Deployment**: Can build to a single `tractjs.min.js` file with inlined WASM and WebWorker, usable without a bundler
- **Bundler Compatibility**: Installable via npm and usable with any JavaScript bundler
- **Node.js Support**: Models can be loaded from the local file system in Node.js
- **Dynamic Input Dimensions**: Configurable via input facts for models requiring specific shapes, or optimization can be disabled to support fully dynamic dimensions

## Usage

### Without a Bundler

```
<script src="https://unpkg.com/tractjs/dist/tractjs.min.js"></script>
tractjs.load("path/to/your/model").then((model) => {
  model.predict([new tractjs.Tensor(new Float32Array([1, 2, 3, 4]), [2, 2])]);
});
```

### With a Bundler

```
npm install tractjs
import * as tractjs from "tractjs";
```

### In Node.js

```
const tractjs = require("tractjs");
tractjs.load("./path/to/your/model");
```

## Size

Approximately 6.2MB raw (2.1MB gzipped). The WASM can optionally be loaded separately to reduce initial bundle size.

## Licensing

Dual-licensed under Apache License 2.0 and MIT license.