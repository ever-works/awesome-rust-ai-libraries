## Overview

A collection of hands-on lab projects and exercises from the Rust Data Engineering Coursera course, designed for learning Rust in the context of data engineering workflows.

## Course Modules

### Week 1 — Rust Data Structures: Collections
- **Sequences**: Working with `Vec`, `VecDeque`, `LinkedList` through fruit salad exercises and CLI tools
- **Maps**: `HashMap` and `BTreeMap` for frequency counting and language comparison
- **Sets**: `HashSet` and `BTreeSet` operations
- **Misc**: `BinaryHeap` for priority-based operations

### Week 2 — Safety, Security, and Concurrency with Rust
- Mutable data handling with CLI customization
- Data race prevention through Rust's ownership model
- Topics covered: ownership, borrowing, lifetimes, immutability, bounds checking, thread safety
- Exercises: memory leak prevention, null pointer safety with `Option`/`Result`, safe FFI, safe transmute, immutable concurrency, multi-threaded web server

### Week 3 — Rust Data Engineering Libraries and Tools
- CSV data processing and database interaction with **Diesel**
- Data visualization with **plotters**
- Multi-threaded web scraping and REST API consumption
- **Polars** for large-scale data processing
- **Apache Arrow** for columnar data processing
- **Parquet** file read/write operations
- **Delta-rs** for Delta Lake interaction
- **TiKV** distributed key-value store
- **Kafka** producer/consumer applications
- **gRPC** microservices
- **AWS SDK** for Rust (S3, DynamoDB)

### Week 4 — Capstone Projects
- Rust-based ETL pipeline
- REST API server with Diesel ORM
- Delta Lake data lake solution
- Big data processing with Apache Arrow
- gRPC services with CRUD operations
- Distributed systems with Rust concurrency
- GraphQL API with **Juniper**
- Data serialization with **serde**
- Machine learning integration with Rust ML libraries

## Technical Features

- Each subdirectory project uses a standardized Makefile with `format`, `lint`, `test`, and `run` targets
- All projects follow Cargo conventions (`cargo fmt`, `cargo clippy`, `cargo test`, `cargo run`)
- Compatible with both AWS CodeCatalyst and GitHub Codespaces environments
- Fork-and-modify lab workflow for extending existing Rust projects

## Prerequisites

- Rust toolchain installed (cargo, rustc)
- Familiarity with basic Rust syntax and data types
- Understanding of data engineering concepts

## References

- Rust Collections documentation
- GitHub Copilot CLI usage
- Rust Fundamentals tutorial
- Rust MLOps Template