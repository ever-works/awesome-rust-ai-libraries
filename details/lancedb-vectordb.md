## Overview

LanceDB is an open-source database for vector search built with persistent storage, which greatly simplifies retrieval, filtering, and management of embeddings. It runs in-process, eliminating the need for server management while still providing production-scale capabilities.

## Features

- **Production-scale vector search** with no servers to manage
- **Multi-modal data support**: store, query, and filter vectors, metadata, and multi-modal data including text, images, videos, and point clouds
- **Multi-query support**: vector similarity search, full-text search, and SQL
- **Multi-language support**: native Rust, Python, and JavaScript/Typecript APIs
- **Zero-copy, automatic versioning**: manage versions of your data without needing extra infrastructure
- **GPU support** for building vector indices (Python SDK)
- **Ecosystem integrations** with LangChain, LlamaIndex, Apache Arrow, Pandas, Polars, DuckDB, and more

## Rust API

The Rust crate (`vectordb`) provides the following capabilities:

- **Connection**: Connect to local databases (`/path/to/database`), cloud object stores (`s3://` or `gs://`), or Lance Cloud (`db://dbname`)
- **ConnectOptions**: Configure connection parameters such as index cache size
- **Table creation**: Create tables using Arrow schemas and RecordBatch streams
- **Vector index creation**: Build IVF_PQ indices with configurable partitions
- **Search**: Execute vector similarity searches on tables

### Key Types

- `Connection` / `Database` – LanceDB database connection
- `Table` / `TableRef` – LanceDB table APIs
- `ConnectOptions` – Connection configuration
- `Error` / `Result` – Error handling
- `WriteMode` – Dataset write mode configuration

### Storage Options

- Local filesystem paths
- AWS S3 object storage
- Google Cloud Storage
- Lance Cloud managed service

## Usage Example

```rust
use vectordb::connect;

let db = connect("data/sample-lancedb").await.unwrap();
```

## Licensing

Open-source under the Apache 2.0 license.