## Overview

RustFL is a federated learning framework designed to securely and asynchronously train machine learning models while preserving the privacy of client data. By integrating Differential Privacy (DP) and Secure Multiparty Computation (SMPC), the framework ensures that sensitive information remains confidential throughout the training and aggregation process.

## Architecture

RustFL operates with a central server and multiple clients. Clients perform local model training and then update the global model securely and privately.

### Client Workflow
- Retrieve the latest global model from the server
- Perform local training using local datasets
- Generate shares of updated model weights using Shamir's Secret Sharing
- Apply Differential Privacy to the shares to prevent individual client data leakage

### Encryption and Transmission
- Noisy shares are encrypted for additional privacy protection
- Encrypted shares are transmitted to the server for aggregation

### Server Aggregation
- Receives encrypted noisy shares from clients
- Aggregates shares using Secure Multiparty Computation (SMPC) techniques
- Reconstructs the updated global model from aggregated shares
- Updates the global model with new aggregated weights

## Key Features

- **Privacy-Preserving**: Differential Privacy is applied to each model update to obfuscate sensitive information from individual clients
- **Secure Aggregation**: The server performs model updates using encrypted shares, ensuring no client data is exposed during aggregation
- **Asynchronous Communication**: The framework utilizes asynchronous communication between clients and the server via tokio

## Technologies Used

- **Rust**: Main programming language for the federated learning framework
- **tokio**: Asynchronous runtime for handling concurrent tasks efficiently
- **tch**: PyTorch bindings for implementing deep learning models and tensor operations in Rust
- **reqwest**: HTTP communication between clients and server
- **log**: Logging for information, warnings, and errors

## Distribution

- Available on crates.io: https://crates.io/crates/RustFL
- Includes an example application demonstrating usage
- Supports Docker containerization for server and client deployments