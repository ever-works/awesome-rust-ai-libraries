## Overview

IndraDB is a graph database consisting of a server and an underlying library. It was originally inspired by TAO, Facebook's graph datastore, emphasizing simplicity of implementation and query semantics. It is designed with the assumption that it may represent graphs large enough that full graph processing is not feasible.

## Features

- **Directed and typed graphs** with support for JSON-based properties tied to vertices and edges
- **Multi-hop queries** and queries on indexed properties
- **Cross-language support** via gRPC with official bindings for Python and Rust
- **Pluggable datastores** including in-memory, RocksDB, PostgreSQL, and Sled (the latter two available as separate crates)
- **CLI tooling** for interacting with a running server
- **Plugin system** loaded via dynamically linked libraries to extend server functionality
- Written in Rust for high performance, no GC pauses, and memory safety

## Usage Modes

### Server
The server uses gRPC for cross-language support. Start with `indradb-server` and connect via Python or Rust bindings.

### Rust Library
Embed directly in Rust applications without a server:
```toml
indradb-lib = { version = "*", features = ["rocksdb-datastore"] }
```

### CLI
Interact with a running server via command line, e.g. `indradb-client grpc://127.0.0.1:27615 count vertex`.

## Datastores

| Datastore | Description |
|-----------|-------------|
| Memory | Default in-memory datastore; fastest but limited by available RAM |
| RocksDB | Persistent on-disk datastore via RocksDB backend |
| PostgreSQL | Available through the `indradb-postgres` crate |
| Sled | Available through the `indradb-sled` crate |

## Installation

- **Pre-compiled releases** available for Linux and macOS
- **From source**: Requires Rust and GCC 5+ with protobuf toolchain, then `cargo install`
- **Docker**: Build and run server/client images with Docker BuildKit

## Plugins

The server supports plugins loaded as dynamically linked libraries, callable via the gRPC `ExecutePlugin` function. Examples include a hello world plugin and a naive vertex plugin.

## Pricing

Free and open-source.