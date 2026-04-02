# Rust AI Libraries

Curated directory of Rust-based libraries and crates for AI model training, inference, agentic systems, and related tools. Include popular crates like candle, burn, dfdx, tract, and more. Focus on open-source, high-quality projects with GitHub stars, docs, and examples.
## 📑 Table of Contents

- [Applications (24)](#applications)
- [Frameworks (15)](#frameworks)
- [NLP (18)](#nlp)
- [Data Formats (3)](#data-formats)
- [Inference (5)](#inference)
- [Bindings (3)](#bindings)
- [Compilers (1)](#compilers)
- [Data Processing (6)](#data-processing)
- [Development Tools (1)](#development-tools)
- [Machine Learning (80)](#machine-learning)
- [Math (4)](#math)
- [Optimization (1)](#optimization)
- [Other (2)](#other)
- [Search (6)](#search)
- [Vector Search (2)](#vector-search)
- [Visualization (1)](#visualization)
- [Agentic Systems (16)](#agentic-systems)
- [AI Agents (2)](#ai-agents)
- [AI Assistants (1)](#ai-assistants)
- [AI Tools (2)](#ai-tools)
- [Analysis (1)](#analysis)
- [API Clients (3)](#api-clients)
- [Caching (1)](#caching)
- [Cloud (2)](#cloud)
- [Clustering (2)](#clustering)
- [Code Generation (1)](#code-generation)
- [Computer Vision (4)](#computer-vision)
- [Data Generation (1)](#data-generation)
- [Data Management (1)](#data-management)
- [Data Structures (1)](#data-structures)
- [Data Visualization (1)](#data-visualization)
- [Dataflow Frameworks (1)](#dataflow-frameworks)
- [Differentiation (1)](#differentiation)
- [Distributed (1)](#distributed)
- [Embeddings (1)](#embeddings)
- [Federated Learning (1)](#federated-learning)
- [Generative AI (1)](#generative-ai)
- [Graph Processing (6)](#graph-processing)
- [Linear Algebra (1)](#linear-algebra)
- [LLM Tools (3)](#llm-tools)
- [Memory (3)](#memory)
- [MLOps (4)](#mlops)
- [Model Inference (4)](#model-inference)
- [Model Interpretability (1)](#model-interpretability)
- [Model Transpilation (1)](#model-transpilation)
- [RAG Tools (1)](#rag-tools)
- [Reinforcement Learning (3)](#reinforcement-learning)
- [Retrieval (1)](#retrieval)
- [Services (1)](#services)
- [Speech-to-Text (1)](#speech-to-text)
- [Stream Processing (1)](#stream-processing)
- [Text Processing (4)](#text-processing)
- [Tooling (2)](#tooling)
- [Tools (2)](#tools)
- [Transpiling (1)](#transpiling)
- [Vector Databases (4)](#vector-databases)
- [Vector Stores (1)](#vector-stores)
- [Voice AI (1)](#voice-ai)


## Applications

- [bloop](https://github.com/BloopAI/bloop) - Fast code search engine written in Rust, applicable to AI-powered code analysis and search. Apache-2 licensed with 9.5K stars. ([Read more](/details/bloop.md)) `Code Search` `Semantic Search` `Open Source`
- [ChatGPT](https://github.com/lencx/ChatGPT) - ChatGPT Desktop Application for Mac, Windows, and Linux, built with Rust via Tauri, providing AI chat interface. Unlicensed with 53K GitHub stars. ([Read more](/details/chatgpt.md)) `Chatgpt` `Desktop App` `Open Source`
- [MeiliSearch](https://github.com/meilisearch/meilisearch) - Lightning-fast search API that fits into apps, relevant for ML-powered search and vector similarity in Rust-based systems. MIT licensed with 48K stars. ([Read more](/details/meilisearch.md)) `Search Engine` `Full Text Search` `Open Source`
- [quickwit](https://github.com/quickwit-oss/quickwit) - Cloud-native search engine for observability, an open-source alternative with Rust implementation for ML data retrieval. Unlicensed with 8.3K GitHub stars. ([Read more](/details/quickwit.md)) `Search Engine` `Observability` `Open Source`
- [sonic](https://github.com/valeriansaliou/sonic) - Fast, lightweight, schema-less search backend as an alternative to Elasticsearch, useful for ML search applications. MPL-2.0 licensed with 20K stars. ([Read more](/details/sonic.md)) `Search Backend` `Lightweight` `Open Source`
- [tantivy](https://github.com/quickwit-oss/tantivy) - Full-text search engine library inspired by Apache Lucene, useful for ML retrieval and embedding search. MIT licensed with 12K stars. ([Read more](/details/tantivy.md)) `Search Engine` `Full Text` `Open Source`
- [bayard](https://github.com/mosuka/bayard) - Full-text search and indexing server written in Rust, for ML retrieval systems. MIT licensed with 1.9K stars. ([Read more](/details/bayard.md)) `Full Text Search` `Indexing` `Open Source`
- [chat-ai-desktop](https://github.com/sonnylazuardi/chat-ai-desktop) - Unofficial ChatGPT desktop app for Mac and Windows menubar, AI chat application in Rust. MIT licensed. ([Read more](/details/chat-ai-desktop.md)) `Chatgpt` `Desktop` `Open Source`
- [clerk](https://github.com/blankenshipz/clerk) - LLM-based file organizer that categorizes and manages files using large language models. ([Read more](/details/clerk.md)) `Open Source` `File Management` `Llm`
- [deepwiki-rs](https://github.com/sopaco/deepwiki-rs) - Tool to transform codebases into professional architecture documentation using Rust. ([Read more](/details/deepwiki-rs.md)) `Open Source` `Documentation` `Code Analysis`
- [erdos](https://github.com/erdos-project/erdos) - Dataflow system for building self-driving car and robotics applications, relevant for agentic AI systems. Apache-2 licensed. ([Read more](/details/erdos.md)) `Dataflow` `Robotics` `Open Source`
- [llamacord](https://github.com/rustformers/llmcord) - Discord bot written in Rust that generates responses using LLMs. GPL-3.0 licensed. ([Read more](/details/llamacord.md)) `Discord Bot` `Llm` `Open Source`
- [LlamaEdge](https://github.com/LlamaEdge/LlamaEdge) - Easiest and fastest way to run customized and fine-tuned LLMs anywhere, relevant for AI inference applications in Rust. Apache-2 licensed with 1.1K GitHub stars. ([Read more](/details/llamaedge.md)) `Llm Inference` `Edge Computing` `Open Source`
- [lnx](https://github.com/lnx-search/lnx) - Insanely fast, feature-rich searching engine that is adaptable and typo-tolerant, for ML retrieval tasks. MIT licensed with 1.2K stars. ([Read more](/details/lnx.md)) `Search Engine` `Typo Tolerant` `Open Source`
- [lsp-ai](https://github.com/SilasMarvin/lsp-ai) - Open-source language server backend for AI-powered code completion and assistance. MIT licensed with 2.2K stars. ([Read more](/details/lsp-ai.md)) `Language Server` `Ai Coding` `Open Source`
- [nerve](https://github.com/evilsocket/nerve) - Instrument any LLM to perform actual tasks, enabling agentic workflows. Unlicensed. ([Read more](/details/nerve.md)) `Llm Agent` `Tool Use` `Open Source`
- [opentau](https://github.com/GammaTauAI/opentau) - Uses Large Language Models for repo-wide type prediction, AI code analysis tool. Apache-2 licensed. ([Read more](/details/opentau.md)) `Llm` `Code Analysis` `Type Prediction`
- [RustQuant](https://github.com/avhz/RustQuant) - Rust library for quantitative finance, supporting numerical methods and ML in finance. Apache-2 licensed with 1.2K stars. ([Read more](/details/rustquant.md)) `Quant Finance` `Numerical Methods` `Open Source`
- [shortgpt](https://github.com/rupeshs/shortgpt) - Rust tool for obtaining instant and concise answers from LLMs, optimized for brevity in responses. ([Read more](/details/shortgpt.md)) `Open Source` `Chat Tool` `Concise`
- [tenere](https://github.com/pythops/tenere) - TUI (Terminal User Interface) for interacting with LLMs, providing a command-line interface for model inference and chat. ([Read more](/details/tenere.md)) `Open Source` `Tui` `Llm Chat`
- [Toshi](https://github.com/toshi-search/Toshi) - Full-text search engine in Rust, inspired by Elasticsearch for AI search tasks. MIT licensed with 4.2K stars. ([Read more](/details/toshi.md)) `Search Engine` `Full Text` `Open Source`
- [voy](https://github.com/tantaraio/voy) - WASM vector similarity search written in Rust, for efficient AI embedding search. Apache-2 licensed with 880 stars. ([Read more](/details/voy.md)) `Vector Search` `Wasm` `Open Source`
- [weggli](https://github.com/weggli-rs/weggli) - Fast and robust semantic search tool for C and C++ codebases, useful for ML model analysis in code. Apache-2 licensed with 2.3K stars. ([Read more](/details/weggli.md)) `Semantic Search` `Code Analysis` `Open Source`
- [zombodb](https://github.com/zombodb/zombodb) - Integration between Postgres and Elasticsearch, enabling full-text search capabilities useful for ML data pipelines. Unlicensed with 4.7K stars. ([Read more](/details/zombodb.md)) `Postgres` `Elasticsearch` `Search`

## Frameworks

- [Burn](https://github.com/tracel-ai/burn) - Burn is a new comprehensive dynamic Deep Learning Framework built using Rust. It is ranked highly in the best-of-ml-rust list with a project-quality score of 22 and 9.1K GitHub stars. Suitable for machine learning model training and inference in Rust applications. ([Read more](/details/burn.md)) `Deep Learning` `Rust Crate` `Open Source`
- [Candle](https://github.com/huggingface/candle) - Candle is a minimalist ML framework for Rust with support for running Hugging Face models. It enables efficient inference and training with hardware acceleration. Highly ranked with score 21 and 16K GitHub stars. ([Read more](/details/candle.md)) `Minimalist` `Inference` `Deep Learning` `Open Source`
- [dfdx](https://github.com/coreylowman/dfdx) - dfdx provides deep learning in Rust with shape-checked tensors and neural networks. Supports training and inference. Score 15, 1.7K stars. ([Read more](/details/dfdx.md)) `Deep Learning` `Tensors` `Open Source`
- [leaf](https://github.com/autumnai/leaf) - leaf is an Open Machine Intelligence Framework for Hackers with GPU/CPU support. Dead project. Score 14, 5.6K stars. ([Read more](/details/leaf.md)) `Machine Intelligence` `Gpu` `Open Source`
- [linfa](https://github.com/rust-ml/linfa) - linfa is a Rust machine learning framework consisting of modular crates for common ML tasks. It provides algorithms for clustering, regression, and more. Score 21, 3.8K stars. ([Read more](/details/linfa.md)) `Machine Learning` `Algorithms` `Open Source`
- [luminal](https://github.com/jafioti/luminal) - luminal enables deep learning at the speed of light using Rust. Score 14, 1.5K stars. ([Read more](/details/luminal.md)) `Deep Learning` `High Performance` `Open Source`
- [autograph](https://github.com/charles-r-earp/autograph) - autograph is a machine learning library for Rust. Score 12, 320 stars. ([Read more](/details/autograph.md)) `Machine Learning` `Open Source`
- [juice](https://github.com/fff-rs/juice) - juice is the Hacker's Machine Learning Engine. Inactive. Score 16, 1.1K stars. ([Read more](/details/juice.md)) `Machine Learning` `Open Source`
- [NeuroFlow](https://github.com/MikhailKravets/NeuroFlow) - NeuroFlow is an awesome deep learning crate. Dead project. Score 13, 120 stars. ([Read more](/details/neuroflow.md)) `Deep Learning` `Open Source`
- [ratchet](https://github.com/huggingface/ratchet) - ratchet is a cross-platform browser ML framework built with Rust and WebAssembly. Score 15, 630 stars. ([Read more](/details/ratchet.md)) `Browser` `Wasm` `Open Source`
- [rust-autograd](https://github.com/raskr/rust-autograd) - rust-autograd provides tensors and differentiable operations like TensorFlow in Rust. Dead project. Score 12, 490 stars. ([Read more](/details/rust-autograd.md)) `Autograd` `Tensors` `Open Source`
- [rustlearn](https://github.com/maciejkula/rustlearn) - rustlearn is a machine learning crate for Rust. Dead project. Score 16, 620 stars. ([Read more](/details/rustlearn.md)) `Machine Learning` `Open Source`
- [RustTensor](https://github.com/ramsyana/RustTensor) - Learning-focused, high-performance tensor computation library with automatic differentiation and CPU/CUDA backends. Built from scratch in Rust for AI model development. ([Read more](/details/rusttensor.md)) `Tensors` `Autodiff` `Cuda`
- [rusty-machine](https://github.com/AtheMathmo/rusty-machine) - rusty-machine is a Machine Learning library for Rust. Inactive. Score 17, 1.3K stars. ([Read more](/details/rusty-machine.md)) `Machine Learning` `Open Source`
- [smartcore](https://github.com/smartcorelib/smartcore) - smartcore is a comprehensive library for machine learning and numerical computing in Rust, including algorithms for clustering, regression, and more. Score 19, 710 stars. ([Read more](/details/smartcore.md)) `Machine Learning` `Numerical Computing` `Open Source`

## NLP

- [rust-bert](https://github.com/guillaume-be/rust-bert) - Rust-native ready-to-use NLP pipelines and transformer-based models for inference and fine-tuning. ([Read more](/details/rust-bert.md)) `Transformers` `Bert` `Open Source`
- [tiktoken](https://github.com/openai/tiktoken) - Fast BPE tokenizer for use with OpenAI's models, providing efficient text tokenization optimized for performance in Rust environments. ([Read more](/details/tiktoken.md)) `Tokenization` `Open Source` `Bpe`
- [tokenizers](https://github.com/huggingface/tokenizers) - Fast state-of-the-art tokenizers optimized for research and production, implemented in Rust by Hugging Face for NLP tasks. ([Read more](/details/tokenizers.md)) `Tokenization` `Open Source` `Huggingface`
- [aici](https://github.com/microsoft/aici) - AICI treats prompts as Wasm programs for structured generation and model interaction in Rust. ([Read more](/details/aici.md)) `Prompts` `Wasm` `Open Source`
- [Feste](https://github.com/tag1consulting/feste) - GPT-2 style transformer language model implemented from scratch in Rust for educational purposes. ([Read more](/details/feste.md)) `Transformer` `Educational` `Open Source`
- [lindera](https://github.com/lindera/lindera) - Multilingual morphological analysis library ported from Kuromoji, MeCab, Juman, and Sudachi, suitable for NLP tokenization and analysis in Rust. ([Read more](/details/lindera.md)) `Morphological Analysis` `Multilingual` `Open Source`
- [lingua-rs](https://github.com/pemistahl/lingua-rs) - Accurate natural language detection library supporting 75 languages, optimized for performance in Rust. ([Read more](/details/lingua-rs.md)) `Language Detection` `Open Source`
- [llama-rs](https://github.com/rustformers/llm) - Ecosystem of Rust libraries for running LLMs locally (unmaintained, see README). Supports inference for Llama models and more. ([Read more](/details/llama-rs.md)) `Llm Inference` `Open Source` `Local`
- [nnsplit](https://github.com/segment-any-text/wtpsplit) - Neural network-based toolkit to segment text into sentences or semantic units without language-specific rules. ([Read more](/details/nnsplit.md)) `Text Segmentation` `Neural` `Open Source`
- [ollama-rs](https://github.com/pepperoni21/ollama-rs) - Rust library for interacting with the Ollama API, enabling easy integration of local LLMs in Rust AI applications. ([Read more](/details/ollama-rs.md)) `Ollama` `Llm Inference` `Open Source`
- [outlines-core](https://github.com/dottxt-ai/outlines-core) - Core library for structured generation in Rust, enabling constrained text generation with LLMs. ([Read more](/details/outlines-core.md)) `Structured Generation` `Open Source`
- [rust-sbert](https://github.com/cpcdoy/rust-sbert) - Rust port of sentence-transformers for generating sentence embeddings. ([Read more](/details/rust-sbert.md)) `Sentence Embeddings` `Open Source`
- [sudachi.rs](https://github.com/WorksApplications/sudachi.rs) - Rust implementation of Sudachi Japanese tokenizer, a new generation of SudachiPy for efficient NLP processing. ([Read more](/details/sudachirs.md)) `Japanese Tokenizer` `Open Source`
- [text-splitter](https://github.com/benbrandt/text-splitter) - Library to split text into semantic chunks up to a desired size, useful for RAG and LLM applications. ([Read more](/details/text-splitter.md)) `Text Splitting` `Semantic Chunks` `Open Source`
- [Tictonix](https://github.com/Ave-Sergeev/Tictonix) - Converts tokens into embeddings and encodes positions. Useful for token-based embeddings in NLP pipelines. ([Read more](/details/tictonix.md)) `Embeddings` `Tokens` `Open Source`
- [tiktoken-rs](https://github.com/zurawiki/tiktoken-rs) - Library for tokenizing text with OpenAI models using tiktoken. Essential for LLM input processing in Rust. ([Read more](/details/tiktoken-rs.md)) `Tokenization` `Openai` `Open Source`
- [whatlang-rs](https://github.com/greyblake/whatlang-rs) - Natural language detection library for Rust with online demo, detects over 100 languages. ([Read more](/details/whatlang-rs.md)) `Language Detection` `Open Source`
- [whichlang](https://github.com/quickwit-oss/whichlang) - Rust library for language detection using a multiclass logistic regression model, useful for NLP preprocessing in LLM pipelines. ([Read more](/details/whichlang.md)) `Open Source` `Language Detection` `Ml Model`

## Data Formats

- [arrow-rs](https://github.com/apache/arrow-rs) - Official Rust implementation of Apache Arrow, the columnar in-memory analytics format. ([Read more](/details/arrow-rs.md)) `Arrow` `Columnar` `Open Source`
- [lance](https://github.com/lancedb/lance) - Modern columnar data format for ML and LLMs implemented in Rust, supporting efficient storage and querying of vector data. ([Read more](/details/lance.md)) `Columnar` `Ml Data` `Open Source`
- [delta-rs](https://github.com/delta-io/delta-rs) - Native Rust library for Delta Lake table format, with Python bindings for ML workflows. ([Read more](/details/delta-rs.md)) `Delta Lake` `Open Source`

## Inference

- [mistral.rs](https://github.com/EricLBuehler/mistral.rs) - mistral.rs provides blazingly fast LLM inference in Rust. Optimized for performance in running large language models. Score 21, 4.6K stars. ([Read more](/details/mistralrs.md)) `Llm` `Inference` `Open Source`
- [tract](https://github.com/sonos/tract) - tract is a tiny, no-nonsense, self-contained TensorFlow and ONNX inference engine in Rust. Popular for model inference with no external dependencies. Score 19, 2.2K stars. ([Read more](/details/tract.md)) `Onnx` `Tensorflow` `Inference` `Open Source`
- [llm-chain](https://github.com/sobelio/llm-chain) - Rust library for chaining multiple LLMs together to enable complex interactions and workflows. Supports integration with various LLM backends for building advanced AI applications. ([Read more](/details/llm-chain.md)) `Open Source` `Llm Chaining` `Rust`
- [onnxruntime-rs](https://github.com/nbigaouette/onnxruntime-rs) - onnxruntime-rs is a Rust wrapper for Microsoft's ONNX Runtime. Dead project. Score 15, 280 stars. ([Read more](/details/onnxruntime-rs.md)) `Onnx` `Runtime` `Open Source`
- [Plano](https://github.com/katanemo/plano) - AI-native proxy server and data plane for agentic apps. Enables efficient inference and agent workflows in Rust. ([Read more](/details/plano.md)) `Agentic` `Proxy` `Open Source`

## Bindings

- [tch-rs](https://github.com/LaurentMazare/tch-rs) - tch-rs offers Rust bindings for the C++ API of PyTorch, allowing PyTorch models to be used in Rust. Supports tensor operations and model inference. Score 20, 4.4K stars. ([Read more](/details/tch-rs.md)) `Pytorch` `Bindings` `Deep Learning` `Open Source`
- [rust-numpy](https://github.com/PyO3/rust-numpy) - rust-numpy provides PyO3-based Rust bindings for the NumPy C-API, enabling seamless integration between Rust and Python's NumPy. Useful for numerical computing in AI pipelines. Score 21, 1.1K stars. ([Read more](/details/rust-numpy.md)) `Numpy` `Bindings` `Pyo3` `Open Source`
- [tensorflow/rust](https://github.com/tensorflow/rust) - Rust language bindings for TensorFlow, enabling TensorFlow usage in Rust applications. Inactive since 2023. Score 15, 5.2K stars. ([Read more](/details/tensorflowrust.md)) `Tensorflow` `Bindings` `Open Source`

## Compilers

- [TVM](https://github.com/apache/tvm) - Apache TVM is an open deep learning compiler stack for CPUs, GPUs, and specialized accelerators. Rust bindings enable its use in Rust AI workflows. Score 20, 12K stars. ([Read more](/details/tvm.md)) `Compiler` `Deep Learning` `Open Source`

## Data Processing

- [arrow-datafusion](https://github.com/apache/datafusion) - Apache DataFusion SQL query engine built on Arrow, for high-performance data processing in Rust. ([Read more](/details/arrow-datafusion.md)) `Sql` `Query Engine` `Open Source`
- [cramjam](https://github.com/milesgranger/cramjam) - cramjam (pyrus-cramjam) provides easy access to compression algorithms optimized for speed. Useful for data handling in ML pipelines. Score 19, 93 stars. ([Read more](/details/cramjam.md)) `Compression` `Open Source`
- [Polars](https://github.com/pola-rs/polars) - High-performance DataFrame library in Rust, serving as a faster alternative to pandas for data manipulation in AI workflows. ([Read more](/details/polars.md)) `Open Source` `Dataframe` `High Performance`
- [siteone-crawler](https://github.com/janreges/siteone-crawler) - Comprehensive website crawler, auditor, offline archiver, and AI-ready markdown exporter with built-in CI/CD quality checks. A Rust crate for high-quality web data collection tailored for AI and LLM training datasets. ([Read more](/details/siteone-crawler.md)) `Open Source` `Web Crawler` `Ai Ready`
- [webclaw](https://github.com/0xMassi/webclaw) - Web content extraction tool optimized for LLMs, featuring TLS fingerprinting, MCP server support, and headless operation without browsers. Ideal for Rust-based data pipelines preparing content for AI model inference. ([Read more](/details/webclaw.md)) `Open Source` `Llm` `Web Scraping`
- [weld](https://github.com/weld-project/weld) - weld is a high-performance runtime for data analytics applications, useful for ML data processing. Dead project. Score 17, 3K stars. ([Read more](/details/weld.md)) `Analytics` `Runtime` `Open Source`

## Development Tools

- [evcxr](https://github.com/evcxr/evcxr) - evcxr is a Jupyter kernel for Rust with support for plotting and rich REPL. Score 18, 5.6K stars. ([Read more](/details/evcxr.md)) `Jupyter` `Repl` `Open Source`

## Machine Learning

- [Rayon](https://github.com/rayon-rs/rayon) - Data parallelism library for Rust, enabling easy parallel iteration and computation, widely used in machine learning crates for efficient training. ([Read more](/details/rayon.md)) `Open Source` `Parallelism`
- [Anofox Regression](https://github.com/sipemu/anofox-regression) - Statistical regression models including OLS, Elastic Net, GLM, Quantile & Isotonic with R-like inference and Wasm support. ([Read more](/details/anofox-regression.md)) `Regression` `Statistics` `Wasm`
- [arrayfire-rust](https://github.com/arrayfire/arrayfire-rust) - Rust bindings for ArrayFire, a high-performance software library for parallel computing with an easy-to-use API. ([Read more](/details/arrayfire-rust.md)) `Open Source` `Gpu` `Parallel Computing`
- [atoma-infer](https://github.com/atoma-network/atoma-infer) - Rust library for fast AI model inference at scale using Candle. Features FlashAttention2, PagedAttention for KV-cache, multi-GPU support, and OpenAI API compatibility. ([Read more](/details/atoma-infer.md)) `Open Source` `Inference` `Multi Gpu`
- [burn-onnx](https://github.com/tracel-ai/burn-onnx) - Repository for Burn's ONNX support, containing crates for ONNX model import (burn-import), IR (onnx-ir), runtime (burn-onnx), and examples including ONNX inference, Raspberry Pi Pico, and web image classification. Provides specialized tools for converting and running ONNX models with Burn. ([Read more](/details/burn-onnx.md)) `Open Source` `Onnx` `Inference`
- [candle-core](https://github.com/huggingface/candle/tree/main/candle-core) - Core component of the Candle ML framework providing fundamental tensor operations, devices, and the Tensor struct. Essential for building ML models in Rust. ([Read more](/details/candle-core.md)) `Open Source` `Tensors` `Core`
- [candle-coursera-ml](https://github.com/vishpat/candle-coursera-ml) - Rust implementations of machine learning algorithms from Coursera's Machine Learning Specialization course, built using the Candle framework. ([Read more](/details/candle-coursera-ml.md)) `Open Source` `Education` `Algorithms`
- [candle-datasets](https://github.com/huggingface/candle/tree/main/candle-datasets) - Datasets and data loaders for the Candle ML framework. Facilitates data handling for training and inference in Rust ML applications. ([Read more](/details/candle-datasets.md)) `Open Source` `Datasets` `Data Loading`
- [candle-einops](https://github.com/tomsanbear/candle-einops) - Pure Rust implementation of the Python einops library for Candle. Simplifies tensor manipulations with Einstein summation notation and tensor rearrangements. ([Read more](/details/candle-einops.md)) `Open Source` `Tensor Ops` `Einops`
- [candle-ext](https://github.com/mokeyish/candle-ext) - Extension library for Candle providing PyTorch functions not yet available in Candle core. Enhances Candle's capabilities with additional tensor operations and utilities. ([Read more](/details/candle-ext.md)) `Open Source` `Extensions` `Pytorch Compat`
- [candle-flash-attn](https://github.com/huggingface/candle/tree/main/candle-flash-attn) - Implementation of Flash Attention v2 in Candle for efficient attention computation. Improves performance for transformer models on GPUs. ([Read more](/details/candle-flash-attn.md)) `Open Source` `Attention` `Flash Attention`
- [candle-kernels](https://github.com/huggingface/candle/tree/main/candle-kernels) - Custom CUDA kernels for the Candle ML framework. Enables optimized computations for GPU acceleration in ML models. ([Read more](/details/candle-kernels.md)) `Open Source` `Cuda` `Kernels`
- [candle-lora](https://github.com/EricLBuehler/candle-lora) - Efficient and ergonomic LoRA implementation for the Candle ML framework in Rust. Provides out-of-the-box LoRA support for many models supported by Candle, focusing on performance and ease of use. ([Read more](/details/candle-lora.md)) `Open Source` `Lora` `Fine Tuning`
- [candle-nn](https://github.com/huggingface/candle/tree/main/candle-nn) - Neural network building blocks for the Candle framework. Includes layers, activations, and utilities for constructing real-world ML models. ([Read more](/details/candle-nn.md)) `Open Source` `Neural Networks` `Layers`
- [candle-onnx](https://github.com/huggingface/candle/tree/main/candle-onnx) - ONNX model evaluation support for Candle. Allows running ONNX models within the Candle Rust ML framework. ([Read more](/details/candle-onnx.md)) `Open Source` `Onnx` `Interoperability`
- [candle-sampling](https://github.com/EricLBuehler/candle-sampling) - Rust library providing advanced sampling techniques for the Candle ML framework. Supports various sampling methods for improved generation in language models and other tasks. ([Read more](/details/candle-sampling.md)) `Open Source` `Sampling` `Generation`
- [candle-transformers](https://github.com/huggingface/candle/tree/main/candle-transformers) - Transformers-related utilities and model implementations for Candle. Supports loading and running transformer models like BERT, GPT variants. ([Read more](/details/candle-transformers.md)) `Open Source` `Transformers` `Llm`
- [candle-video](https://github.com/FerrisMind/candle-video) - Rust library for text-to-video generation built on Candle, supporting LTX-Video and related models. Emphasizes fast, Python-free inference for video generation tasks. ([Read more](/details/candle-video.md)) `Open Source` `Text To Video` `Inference`
- [collenchyma](https://github.com/autumnai/collenchyma) - Extensible, pluggable, backend-agnostic framework for parallel, high-performance computations on CUDA, OpenCL, and CPU, ideal for AI workloads. ([Read more](/details/collenchyma.md)) `Open Source` `Parallel Computing` `Gpu`
- [CubeCL](https://github.com/tracel-ai/cubecl) - CubeCL is a Rust crate developed by Tracel AI as part of the Burn AI framework's projects. It supports Burn's goal of portable AI model training and inference across various hardware platforms. This open-source library contributes to the ecosystem of Rust-based AI tools. ([Read more](/details/cubecl.md)) `Open Source`
- [cv](https://github.com/rust-cv/cv) - Rust library implementing computer vision algorithms, abstractions, and systems. Supports `#[no_std]` environments, making it suitable for embedded AI and vision applications. ([Read more](/details/cv.md)) `Computer Vision` `No Std` `Algorithms`
- [Darwin-RS](https://github.com/willi-kappler/darwin-rs) - Evolutionary algorithms library supporting genetic computation for AI model optimization and evolution. ([Read more](/details/darwin-rs.md)) `Evolutionary Algorithms` `Open Source`
- [DeepIron](https://github.com/LordSaumya/DeepIron) - A simple Rust library for machine learning and deep learning tasks. Provides essential functionality for building and running ML/DL models in Rust. Supports the growing ecosystem of Rust AI tools. ([Read more](/details/deepiron.md)) `Open Source` `Deep Learning`
- [dicom-rs](https://github.com/Enet4/dicom-rs) - Pure Rust implementation of the DICOM standard for working with medical imaging data. Enables interaction with DICOM objects in AI/ML applications for healthcare imaging analysis. ([Read more](/details/dicom-rs.md)) `Dicom` `Medical Imaging` `Computer Vision`
- [dominant_color](https://github.com/marekm4/dominant_color) - Extracts dominant colors from images using clustering algorithms. Useful for image analysis and feature extraction in machine learning workflows. ([Read more](/details/dominant_color.md)) `Image Analysis` `Color Extraction` `Clustering`
- [emu](https://github.com/calebwin/emu) - A language and library for GPGPU numerical computing, suitable for AI model training and inference on GPUs. ([Read more](/details/emu.md)) `Open Source` `Gpu Computing` `Numerical`
- [faer](https://github.com/sarah-quinones/faer-rs) - Linear algebra foundation for Rust, providing high-performance primitives for numerical computations in AI and machine learning. ([Read more](/details/faer.md)) `Open Source` `Linear Algebra`
- [gemini-client-api](https://crates.io/crates/gemini-client-api) - Library to use Google Gemini API with automatic context management, schema generation, function calling and more. Rust bindings for Gemini integration in AI applications. ([Read more](/details/gemini-client-api.md)) `Google Gemini` `Api Client` `Open Source`
- [Genevo](https://github.com/innoave/genevo) - Execute genetic algorithm (GA) simulations in a customizable and extensible way. Relevant for evolutionary computation in Rust AI applications. ([Read more](/details/genevo.md)) `Genetic Algorithms` `Open Source`
- [ghost-flow](https://github.com/choksi2212/ghost-flow) - A complete machine learning framework in Rust featuring tensors, neural networks, over 85 ML algorithms, GPU acceleration, WASM, FFI, model serving, optimizations, distributed training, and hardware acceleration. Comprehensive toolkit for AI model training and inference in Rust. ([Read more](/details/ghost-flow.md)) `Open Source` `Neural Networks` `Gpu`
- [hypergraph](https://github.com/yamafaktory/hypergraph) - Data structure library for directed hypergraphs, enabling modeling of complex relationships beyond pairwise edges. Applicable to graph neural networks, knowledge graphs, and agentic systems in AI. ([Read more](/details/hypergraph.md)) `Hypergraphs` `Graphs` `Data Structures`
- [image](https://github.com/image-rs/image) - Imaging processing library providing basic functions for image manipulation and format conversion. Essential foundation for computer vision and AI image processing in Rust. ([Read more](/details/image.md)) `Image Processing` `Computer Vision` `Open Source`
- [img_hash](https://github.com/abonander/img_hash) - Perceptual image hashing library for comparing images for equality and similarity. Useful for duplicate detection and similarity search in AI image processing pipelines. ([Read more](/details/img_hash.md)) `Image Processing` `Perceptual Hashing` `Similarity`
- [intricate](https://github.com/gabrielmfern/intricate) - GPU-accelerated neural network library in safe Rust using OpenCL for computations. Supports building models from layers like Dense and activations like TanH, training with optimizers and loss functions, and saving/loading models. Includes examples for XOR and MNIST datasets. ([Read more](/details/intricate.md)) `Open Source` `Neural Networks` `Gpu`
- [kalosm](https://github.com/floneum/floneum/tree/master/interfaces/kalosm) - Multi-modal meta-framework in Rust for interfacing with local pre-trained models using Candle. Supports controlled generation, custom samplers, in-memory vector DBs, audio transcription, and more. ([Read more](/details/kalosm.md)) `Open Source` `Multi Modal` `Agents`
- [lightgbm3-rs](https://github.com/Mottl/lightgbm3-rs) - Rust bindings for LightGBM gradient boosting framework. Useful for machine learning model training and inference. ([Read more](/details/lightgbm3-rs.md)) `Gradient Boosting` `Bindings` `Open Source`
- [linfa-bayes](https://crates.io/crates/linfa-bayes) - Naive Bayes classifiers for supervised learning tasks. Supports Bernoulli, Gaussian, and Multinomial variants. Part of the linfa Rust machine learning framework. ([Read more](/details/linfa-bayes.md)) `Open Source` `Supervised Learning` `Naive Bayes`
- [linfa-clustering](https://crates.io/crates/linfa-clustering) - Clustering algorithms for unsupervised learning on unlabeled data. Includes K-Means, Gaussian Mixture Models, DBSCAN, and OPTICS. Benchmarked and tested as part of linfa. ([Read more](/details/linfa-clustering.md)) `Open Source` `Unsupervised Learning` `Clustering`
- [linfa-elasticnet](https://crates.io/crates/linfa-elasticnet) - Elastic Net regularization for linear regression in supervised learning. Combines L1 and L2 penalties. Part of the linfa framework. ([Read more](/details/linfa-elasticnet.md)) `Open Source` `Supervised Learning` `Regression`
- [linfa-ensemble](https://crates.io/crates/linfa-ensemble) - Ensemble learning methods for supervised learning. Implements bagging, random forests, and AdaBoost. Integrated into the linfa machine learning toolkit. ([Read more](/details/linfa-ensemble.md)) `Open Source` `Supervised Learning` `Ensemble Methods`
- [linfa-ftrl](https://crates.io/crates/linfa-ftrl) - Follow The Regularized Leader (FTRL) proximal optimizer with L1 and L2 regularization. Supports incremental updates and partial fitting. Benchmarked in linfa. ([Read more](/details/linfa-ftrl.md)) `Open Source` `Optimization` `Incremental Learning`
- [linfa-hierarchical](https://crates.io/crates/linfa-hierarchical) - Agglomerative hierarchical clustering for unsupervised learning. Builds cluster hierarchies. Tested implementation in linfa. ([Read more](/details/linfa-hierarchical.md)) `Open Source` `Unsupervised Learning` `Hierarchical Clustering`
- [linfa-ica](https://crates.io/crates/linfa-ica) - Independent Component Analysis (ICA) for unsupervised learning. Features FastICA implementation. Part of linfa toolkit. ([Read more](/details/linfa-ica.md)) `Open Source` `Unsupervised Learning` `Ica`
- [linfa-kernel](https://crates.io/crates/linfa-kernel) - Kernel methods for preprocessing and data transformation. Maps features to higher-dimensional spaces. Tested in linfa. ([Read more](/details/linfa-kernel.md)) `Open Source` `Preprocessing` `Kernel Methods`
- [linfa-lars](https://crates.io/crates/linfa-lars) - Least Angle Regression (LARS) for linear regression in supervised learning. Provides sparse regression capabilities. Part of the linfa Rust machine learning framework. ([Read more](/details/linfa-lars.md)) `Open Source` `Supervised Learning` `Regression`
- [linfa-linear](https://crates.io/crates/linfa-linear) - Linear regression models including Ordinary Least Squares (OLS) and Generalized Linear Models (GLM) for supervised learning. Core regression tools in linfa. ([Read more](/details/linfa-linear.md)) `Open Source` `Supervised Learning` `Linear Regression`
- [linfa-logistic](https://crates.io/crates/linfa-logistic) - Logistic regression for two-class classification with partial fit support. Builds probabilistic models for supervised learning. Integrated in linfa. ([Read more](/details/linfa-logistic.md)) `Open Source` `Supervised Learning` `Classification`
- [linfa-nn](https://crates.io/crates/linfa-nn) - Nearest Neighbors algorithms and distance metrics with spatial indexing. Used for preprocessing and similarity search. Benchmarked in linfa. ([Read more](/details/linfa-nn.md)) `Open Source` `Preprocessing` `Nearest Neighbors`
- [linfa-pls](https://crates.io/crates/linfa-pls) - Partial Least Squares (PLS) for dimensionality reduction and regression in supervised learning. Effective for high-dimensional data. ([Read more](/details/linfa-pls.md)) `Open Source` `Supervised Learning` `Dimensionality Reduction`
- [linfa-preprocessing](https://crates.io/crates/linfa-preprocessing) - Data preprocessing tools including normalization, whitening, count vectorization, and TF-IDF. Essential for ML pipelines in linfa. Benchmarked. ([Read more](/details/linfa-preprocessing.md)) `Open Source` `Preprocessing` `Normalization`
- [linfa-reduction](https://crates.io/crates/linfa-reduction) - Dimensionality reduction techniques: Diffusion maps, PCA, and random projections. Preprocessing tools tested in linfa. ([Read more](/details/linfa-reduction.md)) `Open Source` `Preprocessing` `Pca`
- [linfa-svm](https://crates.io/crates/linfa-svm) - Support Vector Machines for classification and regression on labeled datasets. Supervised learning algorithm in linfa. ([Read more](/details/linfa-svm.md)) `Open Source` `Supervised Learning` `Svm`
- [linfa-trees](https://crates.io/crates/linfa-trees) - Decision trees for supervised learning. Implements linear decision trees, benchmarked in linfa. ([Read more](/details/linfa-trees.md)) `Open Source` `Supervised Learning` `Decision Trees`
- [linfa-tsne](https://crates.io/crates/linfa-tsne) - t-SNE for dimensionality reduction in unsupervised learning. Supports exact and Barnes-Hut approximation. ([Read more](/details/linfa-tsne.md)) `Open Source` `Unsupervised Learning` `Tsne`
- [machine_learning](https://github.com/isaka-james/machine-learning) - A Rust library implementing various machine learning algorithms. Designed for developers building ML models in Rust, it provides foundational tools for the AI ecosystem. Relevant for model training and inference in pure Rust environments. ([Read more](/details/machine_learning.md)) `Open Source` `Algorithms`
- [ndarray](https://github.com/rust-ndarray/ndarray) - N-dimensional array library supporting array views, multidimensional slicing, and efficient operations on numerical data. Fundamental for scientific computing, simulations, and machine learning workflows in Rust. ([Read more](/details/ndarray.md)) `Multidimensional Arrays` `Numerical Computing` `Open Source`
- [neurorust](https://github.com/Clearbloo/neurorust) - Neural network library written in Rust, supporting optimizers like ADAM and SGD, BLAS-accelerated matrix operations, graph neural networks, and automatic differentiation via autograd. Designed for building and training neural network models efficiently. ([Read more](/details/neurorust.md)) `Open Source` `Neural Networks` `Autograd`
- [NumKong](https://github.com/ashvardanian/NumKong) - SIMD-accelerated library for vector distances and similarity functions, optimized for x86 AVX2/AVX-512 and Arm NEON. Ideal for high-performance nearest neighbor search and embedding similarity in AI applications. ([Read more](/details/numkong.md)) `Simd` `Similarity Search` `Vector Distances`
- [optimisers](https://github.com/KGrewal1/optimisers) - Rust crate collection of optimizers including SGD with momentum, AdaGrad, AdaDelta, AdaMax, NAdam, RAdam, and RMSprop. Designed for use in machine learning applications with Candle compatibility. ([Read more](/details/optimisers.md)) `Open Source` `Optimizers` `Training`
- [optimization-engine](https://github.com/alphaville/optimization-engine) - Optimization Engine (OpEn) is a solver for constrained nonconvex optimization problems, useful for machine learning optimization tasks. ([Read more](/details/optimization-engine.md)) `Open Source` `Optimization`
- [Oxigen](https://github.com/Martin1887/oxigen) - Fast, parallel, extensible and adaptable genetic algorithm library. Solves N-Queens for N=255 in seconds using less than 1MB RAM. ([Read more](/details/oxigen.md)) `Genetic Algorithms` `Parallel` `Open Source`
- [Perpetual](https://github.com/perpetual-ml/perpetual) - Self-generalizing gradient boosting machine that doesn't require hyperparameter optimization. Crate available for Rust ML workflows. ([Read more](/details/perpetual.md)) `Gradient Boosting` `Automation` `Open Source`
- [Radiate](https://github.com/pkalivas/radiate) - Customizable parallel genetic programming engine for supervised, unsupervised, and reinforcement learning. Includes NEAT and Evtree implementations. ([Read more](/details/radiate.md)) `Genetic Programming` `Reinforcement Learning` `Open Source`
- [roaring-rs](https://github.com/RoaringBitmap/roaring-rs) - Rust implementation of Roaring Bitmaps, an efficient compressed bitmap data structure for handling large sets of integers. Valuable for sparse data representation in machine learning and data processing. ([Read more](/details/roaring-rs.md)) `Bitmaps` `Compression` `Sparse Data`
- [rpds](https://github.com/orium/rpds) - Persistent data structures library providing immutable, thread-safe collections like lists, vectors, maps, and sets. Supports functional programming patterns useful in concurrent AI systems and simulations. ([Read more](/details/rpds.md)) `Persistent Data` `Immutable` `Functional`
- [RsGenetic](https://github.com/m-decoster/RsGenetic) - Genetic Algorithm library in maintenance mode. Provides foundational GA tools for AI optimization tasks in Rust. ([Read more](/details/rsgenetic.md)) `Genetic Algorithms` `Open Source`
- [russell](https://github.com/cpmech/russell) - Rust Scientific Library providing numerical mathematics, ODE solvers, special functions, and high-performance sparse linear algebra for AI research. ([Read more](/details/russell.md)) `Open Source` `Scientific Computing` `Linear Algebra`
- [rust-opencl](https://github.com/luqmana/rust-opencl) - Rust bindings for OpenCL, enabling GPU-accelerated computations for machine learning and scientific applications. ([Read more](/details/rust-opencl.md)) `Open Source` `Opencl` `Gpu`
- [RustNN](https://github.com/jackm321/RustNN) - Easy-to-use feedforward neural network library in Rust for creating fully connected multi-layer networks trained via backpropagation. Supports incremental training with configurable options like learning rate and momentum. Includes XOR example and documentation. ([Read more](/details/rustnn.md)) `Open Source` `Neural Networks`
- [rusty-ml](https://crates.io/crates/rusty-ml) - Comprehensive machine learning library providing classic algorithms for clustering, regression, classification, including Random Forests and Gradient Boosted Regression Trees. Designed to be simple, fast, and easy-to-use with support for supervised and unsupervised learning. Features multiple metrics like Mean Square Error and Hamming Loss while maintaining a small footprint. ([Read more](/details/rusty-ml.md)) `Open Source` `Supervised Learning` `Unsupervised Learning`
- [rustyml](https://github.com/SomeB1oody/RustyML) - A high-performance machine learning and deep learning library written in pure Rust. It supports ML algorithms and neural networks, ideal for training and inference tasks. Key addition to Rust's AI library landscape with focus on performance. ([Read more](/details/rustyml.md)) `Open Source` `Deep Learning` `Neural Networks`
- [scirs](https://github.com/cool-japan/scirs) - Production-ready pure Rust scientific computing library including linear algebra, optimization, statistics, neural networks, and more. API inspired by Python's SciPy. ([Read more](/details/scirs.md)) `Open Source` `Scientific Computing` `Neural Networks`
- [Scorch](https://github.com/Sa4dUs/scorch) - Rust crate for building, training, and evaluating feedforward neural networks, designed for educational purposes and quick experiments. Supports activation functions like ReLU, Sigmoid, and Tanh, with backpropagation-based gradient descent training. Provides modular components for easy extension. ([Read more](/details/scorch.md)) `Open Source` `Neural Networks`
- [steganography](https://github.com/teovoinea/steganography) - Simple steganography library for embedding and extracting data in images. Useful for secure data transmission or watermarking in AI-generated images. ([Read more](/details/steganography.md)) `Steganography` `Image Processing` `Security`
- [TensorBase](https://crates.io/crates/tensorbase) - TensorBase is a library for high-performance, distributed computing designed from the ground up in Rust. It offers a powerful abstraction layer over a distributed system, enabling work with large datasets by leveraging storage, compute, and communication layers. Comparable to Apache Spark and TensorFlow, it provides APIs for common machine learning operations like logistic regression, support vector machines, and deep learning. ([Read more](/details/tensorbase.md)) `Open Source` `Distributed` `Machine Learning`
- [tinguely](https://gitlab.com/matthiaseiholzer/tinguely) - A machine learning library in Rust. Offers tools for ML development within the Rust ecosystem. Suitable for researchers and developers exploring ML in Rust. ([Read more](/details/tinguely.md)) `Open Source`
- [tissue](https://github.com/psiace/tissue) - A Rust crate to quickly showcase machine learning models or magic. Facilitates rapid prototyping and demonstration of ML work in Rust. Useful for presentations and quick AI experiments. ([Read more](/details/tissue.md)) `Open Source` `Prototyping`
- [utah](https://github.com/kernelmachine/utah) - DataFrame library providing columnar data structures and operations for high-performance data manipulation. Supports Rust-native data processing pipelines suitable for ML feature engineering. ([Read more](/details/utah.md)) `Dataframes` `Columnar` `Data Processing`
- [vikos](https://github.com/blue-yonder/vikos) - A machine learning library focused on supervised training of parametrized models. Enables model training in Rust for AI applications. Contributes to Rust's ML capabilities with emphasis on supervised learning. ([Read more](/details/vikos.md)) `Open Source` `Supervised Learning`
- [vllm.rs](https://github.com/guoqingbao/vllm.rs) - Minimalist vLLM implementation in Rust based on Candle. Enables efficient serving and inference of large language models with a lightweight footprint. ([Read more](/details/vllmrs.md)) `Open Source` `Inference` `Serving`

## Math

- [nalgebra](https://github.com/dimforge/nalgebra) - nalgebra is a linear algebra library for Rust. It features high-dimensional vectors, matrices, and mathematical objects with a focus on performance and usability. Ranked with a project-quality score of 22 and 4.1K GitHub stars, essential for numerical computations in AI. ([Read more](/details/nalgebra.md)) `Linear Algebra` `Numerical` `Open Source`
- [cgmath](https://github.com/rustgd/cgmath) - Linear algebra and mathematics library for computer graphics, useful in AI for 3D data processing. ([Read more](/details/cgmath.md)) `Linear Algebra` `Graphics` `Open Source`
- [Peroxide](https://github.com/Axect/Peroxide) - Peroxide is a Rust numeric library with high performance and friendly syntax. It supports numerical analysis, linear algebra, and statistics for AI applications. Ranked with score 22 and 550 GitHub stars. ([Read more](/details/peroxide.md)) `Numerical` `Linear Algebra` `Open Source`
- [statrs](https://github.com/statrs-dev/statrs) - statrs is a statistical computation library for Rust. It provides distributions, statistics, and random variable functionality. With a project-quality score of 22 and 600 GitHub stars. ([Read more](/details/statrs.md)) `Statistics` `Probability` `Open Source`

## Optimization

- [argmin](https://github.com/argmin-rs/argmin) - argmin provides numerical optimization algorithms in pure Rust, useful for training ML models. Supports various solvers and cost functions. Score 17, 1K stars. ([Read more](/details/argmin.md)) `Optimization` `Solvers` `Open Source`

## Other

- [Rust-CUDA](https://github.com/Rust-GPU/Rust-CUDA) - Ecosystem of libraries and tools for writing and executing CUDA kernels in Rust, accelerating AI model training and inference. Apache-2 licensed with 3.2K stars. ([Read more](/details/rust-cuda.md)) `Cuda` `Gpu Acceleration` `Open Source`
- [zkml](https://github.com/ddkang/zkml) - Zero-knowledge machine learning library in Rust. Apache-2 licensed. ([Read more](/details/zkml.md)) `Zero Knowledge` `Ml Privacy` `Open Source`

## Search

- [hora](https://github.com/hora-search/hora) - hora is efficient approximate nearest neighbor search algorithm collections. Dead project. Score 13, 2.6K stars. ([Read more](/details/hora.md)) `Ann` `Open Source`
- [faiss-rs](https://github.com/Enet4/faiss-rs) - faiss-rs provides Rust bindings for Faiss, a library for efficient similarity search and clustering of dense vectors. Score 16, 200 stars. ([Read more](/details/faiss-rs.md)) `Similarity Search` `Vector Search` `Open Source`
- [granne](https://github.com/granne/granne) - granne is Graph-based Approximate Nearest Neighbor Search. Dead project. Score 16, 320 stars. ([Read more](/details/granne.md)) `Ann` `Graph` `Open Source`
- [hnsw](https://github.com/rust-cv/hnsw) - hnsw implements HNSW ANN for efficient approximate nearest neighbor search. Dead project. Score 14, 220 stars. ([Read more](/details/hnsw.md)) `Hnsw` `Ann` `Open Source`
- [instant-distance](https://github.com/djc/instant-distance) - instant-distance provides fast approximate nearest neighbor searching in Rust. Score 12, 310 stars. ([Read more](/details/instant-distance.md)) `Ann` `Nearest Neighbor` `Open Source`
- [kdtree-rs](https://github.com/mrhooray/kdtree-rs) - kdtree-rs is a K-dimensional tree in Rust for fast geospatial indexing and lookup. Score 12, 230 stars. ([Read more](/details/kdtree-rs.md)) `Kdtree` `Geospatial` `Open Source`

## Vector Search

- [Qdrant](https://github.com/qdrant/qdrant) - An open-source vector similarity search engine with extended filtering support. Widely used in AI for efficient vector search, recommendation systems, and semantic search applications. ([Read more](/details/qdrant.md)) `Vector Search` `Open Source` `Filtering`
- [USearch](https://github.com/unum-cloud/usearch) - A similarity search engine for vectors and strings, optimized for high-performance approximate nearest neighbor search in AI applications. ([Read more](/details/usearch.md)) `Similarity Search` `Ann` `Open Source`

## Visualization

- [rerun](https://github.com/rerun-io/rerun) - Visualization tool for multimodal data streams, supporting image, point clouds, and logs for AI and ML debugging. ([Read more](/details/rerun.md)) `Visualization` `Multimodal` `Open Source`

## Agentic Systems

- [Agent of Empires](https://github.com/njbrake/agent-of-empires) - TUI/CLI for managing multiple AI coding agent sessions with tmux, git worktrees, and Docker sandboxing. Facilitates parallel AI agent operations in development workflows. ([Read more](/details/agent-of-empires.md)) `Open Source` `Ai Agents` `Tui`
- [ajeto](https://github.com/bausano/ajeto) - LLM-powered personal assistant implemented in Rust for handling various tasks via large language models. ([Read more](/details/ajeto.md)) `Open Source` `Personal Assistant` `Llm`
- [AutoAgents](https://github.com/liquidos-ai/AutoAgents) - Multi Agent Framework for building AI agents with native edge support. Enables creation of agentic systems in Rust. ([Read more](/details/autoagents.md)) `Multi Agent` `Edge` `Open Source`
- [browser-agent](https://github.com/m1guelpf/browser-agent) - Headless browser controlled by GPT-4, using simplified page representations to receive and execute instructions for web automation. ([Read more](/details/browser-agent.md)) `Open Source` `Web Automation` `Gpt 4`
- [cc-switch](https://github.com/farion1231/cc-switch) - All-in-one GUI assistant and profile manager for Claude Code, Codex, and Gemini CLI tools. ([Read more](/details/cc-switch.md)) `Open Source` `Gui` `Ai Coding`
- [Codex](https://github.com/openai/codex) - Codex CLI is a coding agent from OpenAI that runs locally. Supports AI-assisted coding workflows. ([Read more](/details/codex.md)) `Coding Agent` `Openai` `Open Source`
- [Cortex Memory](https://github.com/sopaco/cortex-mem) - Complete solution for agent memory, including extraction, vector search, automated optimization, and insights dashboard. ([Read more](/details/cortex-memory.md)) `Memory` `Vector Search` `Open Source`
- [git-ai](https://github.com/git-ai-project/git-ai) - Git extension that tracks AI-generated code in repositories, linking lines to the agent, model, and transcripts. Enhances version control for AI-assisted development workflows. ([Read more](/details/git-ai.md)) `Open Source` `Git` `Ai Workflows`
- [GitButler](https://github.com/gitbutlerapp/gitbutler) - Modern Git-based version control interface with GUI and CLI, designed specifically for AI-powered workflows. Provides an intuitive interface for managing repositories in AI development contexts. ([Read more](/details/gitbutler.md)) `Open Source` `Git` `Ai Workflows`
- [hcom](https://github.com/aannoo/hcom) - Rust PTY wrapper enabling AI agents to message, watch, and spawn each other across terminals. Supports Claude Code, Gemini CLI, Codex, OpenCode with screen tracking, TUI, and daemon. ([Read more](/details/hcom.md)) `Open Source` `Ai Agents` `Tui`
- [innerwarden](https://github.com/InnerWarden/innerwarden) - Self-defending security agent for Linux and macOS featuring eBPF kernel hooks, detectors, and AI-driven incident response. ([Read more](/details/innerwarden.md)) `Open Source` `Security` `Ai Agent` `Ebpf`
- [Memvid](https://github.com/memvid/memvid) - Single-file portable memory layer for AI agents with vector search, full-text search, and long-term recall in one .mv2 file. ([Read more](/details/memvid.md)) `Memory` `Vector Search` `Portable`
- [Rig](https://github.com/0xplaygrounds/rig) - Library for creating agents and modular, scalable LLM-powered applications. ([Read more](/details/rig.md)) `Agents` `Llm` `Open Source`
- [smartgpt](https://github.com/Cormanz/smartgpt) - Rust implementation enabling LLMs to complete complex tasks using plugins. Provides agentic capabilities for LLMs similar to Auto-GPT. ([Read more](/details/smartgpt.md)) `Open Source` `Agents` `Plugins`
- [tfmcp](https://github.com/nwiizo/tfmcp) - Terraform MCP Tool, a CLI for AI assistants to manage Terraform environments via Model Context Protocol. Enables agentic interaction with infrastructure as code for AI systems. ([Read more](/details/tfmcp.md)) `Open Source` `Terraform` `Ai Assistants`
- [worktrunk](https://github.com/max-sixty/worktrunk) - CLI for git worktree management designed for running AI agents in parallel, with hooks, LLM commit messages, and merge workflows. ([Read more](/details/worktrunk.md)) `Open Source` `Ai Agents` `Git`

## AI Agents

- [Forgecode](https://forgecode.dev) - A terminal-based AI pair programmer for code generation and editing. It supports AI-assisted coding directly in the terminal environment. ([Read more](/details/forgecode.md)) `Open Source` `Ai Coding` `Terminal Ui`
- [Goose](https://github.com/block/goose) - An open-source, local AI agent that automates engineering tasks. Designed to run locally for privacy and efficiency in development workflows. ([Read more](/details/goose.md)) `Open Source` `Ai Agent` `Local`

## AI Assistants

- [Tabby](https://github.com/TabbyML/tabby) - Self-hosted AI coding assistant and open-source alternative to GitHub Copilot. Provides GPU support and an OpenAPI interface for code completion and generation using local or remote AI models. ([Read more](/details/tabby.md)) `Self Hosted` `Code Generation` `Open Source`

## AI Tools

- [Models](https://github.com/arimxyer/models) - Terminal user interface (TUI) application for browsing AI models, benchmarks, and coding agents. Provides a convenient command-line tool for exploring and managing AI resources. ([Read more](/details/models.md)) `Tui` `Ai Models` `Benchmarks`
- [Saga Reader](https://github.com/sopaco/saga-reader) - Blazing-fast and extremely lightweight internet reader driven by AI. Supports fetching information from search engines and RSS feeds for efficient content consumption. ([Read more](/details/saga-reader.md)) `Ai Driven` `Rss` `Web Reader`

## Analysis

- [vega](https://github.com/rajasekarv/vega) - Faster implementation of Apache Spark from scratch in Rust, for data analysis in ML pipelines. Apache-2 licensed with 2.2K stars. ([Read more](/details/vega.md)) `Spark Alternative` `Big Data` `Open Source`

## API Clients

- [async-openai](https://github.com/64bit/async-openai) - Ergonomic Rust bindings for OpenAI API based on OpenAPI spec. ([Read more](/details/async-openai.md)) `Openai` `Async` `Open Source`
- [Harmony](https://github.com/openai/harmony) - Renderer for the harmony response format to be used with gpt-oss. OpenAI-related tooling for response handling. ([Read more](/details/harmony.md)) `Openai` `Response Format` `Open Source`
- [rust-openai-chatgpt-api](https://github.com/uiuifree/rust-openai-chatgpt-api) - Strongly typed Rust client library for the OpenAI API, supporting chat completions and other endpoints. ([Read more](/details/rust-openai-chatgpt-api.md)) `Open Source` `Openai` `Client`

## Caching

- [Curvine](https://github.com/CurvineIO/curvine) - A high-performance, concurrent distributed cache system designed for low-latency and high-throughput workloads in AI and big data environments. ([Read more](/details/curvine.md)) `Distributed Cache` `Ai` `High Performance`

## Cloud

- [azure-sdk-for-rust](https://github.com/Azure/azure-sdk-for-rust) - Azure SDK for Rust provides official libraries for Azure services, useful for integrating cloud ML workflows. Listed in ML frameworks with score 20 and 720 stars. ([Read more](/details/azure-sdk-for-rust.md)) `Azure` `Sdk` `Open Source`
- [rusoto](https://github.com/rusoto/rusoto) - rusoto is an AWS SDK for Rust, useful for cloud-based ML deployments and services. Dead project. Score 22, 2.7K stars. ([Read more](/details/rusoto.md)) `Aws` `Sdk` `Open Source`

## Clustering

- [gap-statistic](https://github.com/milesgranger/gap_statistic) - gap-statistic dynamically gets the suggested clusters in data for clustering analysis. Dead project. Score 16, 220 stars. ([Read more](/details/gap-statistic.md)) `Clustering` `Open Source`
- [kodama](https://github.com/diffeo/kodama) - kodama is fast hierarchical agglomerative clustering in Rust. Inactive. Score 13, 91 stars. ([Read more](/details/kodama.md)) `Clustering` `Open Source`

## Code Generation

- [autorust](https://github.com/minskylab/auto-rust) - Rust macros that generate AI-driven Rust code at compile time, leveraging LLMs for code generation. ([Read more](/details/autorust.md)) `Open Source` `Macros` `Ai Code Gen`

## Computer Vision

- [imageproc](https://github.com/image-rs/imageproc) - Image processing library built on image crate, offering filters, geometry, and drawing primitives. ([Read more](/details/imageproc.md)) `Image Processing` `Open Source`
- [kornia-rs](https://github.com/kornia/kornia-rs) - Low-level computer vision library in Rust with differentiable image transformations. ([Read more](/details/kornia-rs.md)) `Differentiable` `Cv` `Open Source`
- [opencv-rust](https://github.com/twistedfall/opencv-rust) - Rust bindings for OpenCV 3 and 4, enabling computer vision tasks like object detection and image manipulation. ([Read more](/details/opencv-rust.md)) `Opencv` `Bindings` `Open Source`
- [RuView](https://github.com/ruvnet/RuView) - Privacy-preserving human pose estimation system using WiFi Channel State Information (CSI) and machine learning. A Rust-based tool for non-intrusive pose detection without requiring cameras, relevant for edge AI and computer vision applications. ([Read more](/details/ruview.md)) `Open Source` `Machine Learning` `Pose Estimation`

## Data Generation

- [synth](https://github.com/shuttle-hq/synth) - Declarative data generator for creating realistic synthetic datasets for ML training. ([Read more](/details/synth.md)) `Synthetic Data` `Open Source`

## Data Management

- [Oxen](https://github.com/Oxen-AI/Oxen) - Core Rust library, server, and CLI for Oxen.ai versioned data lakes for ML. ([Read more](/details/oxen.md)) `Data Lake` `Versioning` `Open Source`

## Data Structures

- [fst](https://github.com/BurntSushi/fst) - Finite state transducers for compact representation of large sets and maps. ([Read more](/details/fst.md)) `Fst` `Compact` `Open Source`

## Data Visualization

- [plotters](https://github.com/plotters-rs/plotters) - Rust plotting library capable of high-quality plots using bitmap or vector graphics backends. Useful for visualizing machine learning results, data distributions, and model performance metrics. ([Read more](/details/plotters.md)) `Plotting` `Charts` `Open Source`

## Dataflow Frameworks

- [Dora](https://github.com/dora-rs/dora) - A fast and simple dataflow-oriented framework for building robotic and multi-AI applications, supporting Python, Rust, and C/C++ APIs. ([Read more](/details/dora.md)) `Dataflow` `Robotics` `Multi Ai`

## Differentiation

- [Enzyme](https://github.com/EnzymeAD/Enzyme) - Enzyme is high-performance automatic differentiation of LLVM and MLIR, useful for gradient computations in ML. Score 14, 1.3K stars. ([Read more](/details/enzyme.md)) `Autodiff` `Llvm` `Open Source`

## Distributed

- [rain](https://github.com/substantic/rain) - rain is a framework for large distributed pipelines, applicable to ML workflows. Dead project. Score 14, 750 stars. ([Read more](/details/rain.md)) `Pipelines` `Distributed` `Open Source`

## Embeddings

- [cleora](https://github.com/BaseModelAI/cleora) - Cleora AI is a general-purpose open-source model for efficient representation learning on tabular data. Score 16, 500 stars. ([Read more](/details/cleora.md)) `Representation Learning` `Tabular Data` `Open Source`

## Federated Learning

- [xaynet](https://github.com/xaynetwork/xaynet) - xaynet is an agnostic Federated Machine Learning framework. Dead project. Score 18, 200 stars. ([Read more](/details/xaynet.md)) `Federated` `Ml` `Open Source`

## Generative AI

- [artcraft](https://github.com/storytold/artcraft) - AI-powered IDE and tangible computing surface for molding scenes, videos, and images like clay. A Rust-based tool for generative content creation. ([Read more](/details/artcraft.md)) `Open Source` `Ai Powered` `Creative Tools`

## Graph Processing

- [graph-rs](https://github.com/sreeise/graph-rs-sdk) - Microsoft Graph API Client and Identity Platform Client implemented in Rust, useful for integrating graph data in AI applications. MIT licensed. ([Read more](/details/graph-rs.md)) `Microsoft Graph` `Api Client` `Open Source`
- [graphlib](https://github.com/purpleprotocol/graphlib) - Simple but powerful graph library for Rust, applicable to ML graph tasks. MIT licensed. ([Read more](/details/graphlib.md)) `Graph` `Library` `Open Source`
- [GraphScope](https://github.com/alibaba/GraphScope) - One-stop large-scale graph computing system from Alibaba, supporting graph processing and analytics for ML tasks. Apache-2 licensed with 3.3K stars. ([Read more](/details/graphscope.md)) `Graph Computing` `Large Scale` `Open Source`
- [petgraph](https://github.com/petgraph/petgraph) - Graph data structure library for Rust, ideal for graph processing, clustering, embedding, and machine learning tasks. Features robust graph algorithms and is Apache-2 licensed with over 3K GitHub stars. ([Read more](/details/petgraph.md)) `Graph` `Data Structures` `Open Source`
- [propagon](https://github.com/Refefer/propagon) - Fast, large-scale library for computing rankings and features on graphs, relevant for graph ML. Unlicensed. ([Read more](/details/propagon.md)) `Graph Features` `Rankings` `Open Source`
- [Raphtory](https://github.com/Pometry/Raphtory) - Scalable graph analytics database powered by a multithreaded engine, suitable for temporal graph processing in AI and ML workflows. GPL-3.0 licensed. ([Read more](/details/raphtory.md)) `Graph Analytics` `Temporal Graphs` `Open Source`

## Linear Algebra

- [sprs](https://github.com/sparsemat/sprs) - sprs is a sparse linear algebra library for Rust, supporting sparse matrices and vectors. Essential for efficient computations in ML. Score 20, 420 stars. ([Read more](/details/sprs.md)) `Sparse` `Matrices` `Open Source`

## LLM Tools

- [aichat](https://github.com/sigoden/aichat) - All-in-one LLM CLI tool with Shell Assistant, Chat-REPL, RAG, AI Tools & Agents. Supports OpenAI, Claude, Gemini, Ollama, Groq, and more. ([Read more](/details/aichat.md)) `Open Source` `Llm` `Cli`
- [awful_aj](https://github.com/graves/awful_aj) - CLI for working with OpenAI-compatible APIs using YAML templates for prompt engineering. Includes a built-in vector database for persistent memories. ([Read more](/details/awful_aj.md)) `Open Source` `Llm` `Vector Database` `Cli`
- [oneiromancer](https://github.com/0xdea/oneiromancer) - Reverse engineering assistant that uses a locally running LLM to aid with source code analysis. ([Read more](/details/oneiromancer.md)) `Open Source` `Llm` `Reverse Engineering` `Cli`

## Memory

- [indexify](https://github.com/diptanu/indexify) - Retrieval and long-term memory service designed for LLMs, enabling persistent context and search. ([Read more](/details/indexify.md)) `Open Source` `Retrieval` `Long Term Memory`
- [memex](https://github.com/spyglass-search/memex) - Rust-powered document store with semantic search capabilities for LLM projects and memory management. ([Read more](/details/memex.md)) `Open Source` `Semantic Search` `Doc Store`
- [motorhead](https://github.com/getmetal/motorhead) - Memory and information retrieval server for LLMs, using Redis as a vector store for long-term memory and compatible with OpenAI API. ([Read more](/details/motorhead.md)) `Open Source` `Retrieval` `Redis`

## MLOps

- [candle-vllm](https://github.com/EricLBuehler/candle-vllm) - Efficient platform for inference and serving local LLMs including support for continuous batching. MIT licensed. ([Read more](/details/candle-vllm.md)) `Llm Inference` `Model Serving` `Open Source`
- [h2o-kubernetes](https://github.com/h2oai/h2o-kubernetes) - H2O Open Source Kubernetes operator and command-line tool for managing ML pipelines on Kubernetes. Apache-2 licensed. ([Read more](/details/h2o-kubernetes.md)) `Kubernetes` `Mlops` `Open Source`
- [mosec](https://github.com/mosecorg/mosec) - High-performance ML model serving framework with dynamic batching, designed for deploying and maintaining ML pipelines. Apache-2 licensed with 800 GitHub stars. ([Read more](/details/mosec.md)) `Model Serving` `Dynamic Batching` `Open Source`
- [TensorZero](https://github.com/tensorzero/tensorzero) - Data and learning flywheel for LLMs that unifies inference, observability, optimization, and experimentation. Designed as an MLOps platform for LLM workflows. ([Read more](/details/tensorzero.md)) `Open Source` `Llm` `Mlops`

## Model Inference

- [diffusers](https://github.com/pykeio/diffusers) - Rust port of Stable Diffusion diffusers library, offering 45% faster performance than PyTorch implementation for image generation tasks. ([Read more](/details/diffusers.md)) `Open Source` `Diffusion Models` `Image Generation`
- [Koharu](https://github.com/mayocream/koharu) - ML-powered manga translator with automatic speech bubble detection, OCR, inpainting, and LLM translation capabilities. Built with Candle for machine learning components and Tauri for cross-platform UI. ([Read more](/details/koharu.md)) `Ocr` `Translation` `Candle`
- [PostgresML](https://github.com/postgresml/postgresml) - Postgres extension for machine learning, enabling model fetching and inference directly via SQL within a Postgres database instance. ([Read more](/details/postgresml.md)) `Open Source` `Postgres Extension` `Sql Ml`
- [rllama](https://github.com/Noeda/rllama) - Pure Rust implementation of LLaMA model inference, suitable for embedding into applications or scripting languages. ([Read more](/details/rllama.md)) `Open Source` `Llama` `Pure Rust`

## Model Interpretability

- [eval-metrics](https://github.com/benjarison/eval-metrics) - Evaluation metrics library for machine learning models, aiding in model interpretability, visualization, explanation, debugging, and evaluation. ([Read more](/details/eval-metrics.md)) `Evaluation Metrics` `Ml Evaluation` `Open Source`

## Model Transpilation

- [m2cgen](https://github.com/BayesWitnesses/m2cgen) - CLI tool to transpile trained classic machine learning models into native Rust code with zero dependencies. ([Read more](/details/m2cgen.md)) `Open Source` `Machine Learning` `Deployment`

## RAG Tools

- [screenpipe](https://github.com/screenpipe/screenpipe) - 24/7 local AI screen and microphone recording tool to provide full context for AI apps. Compatible with Ollama and other local models. ([Read more](/details/screenpipe.md)) `Open Source` `Ai Context` `Recording`

## Reinforcement Learning

- [gym-rs](https://github.com/MrRobb/gym-rs) - gym-rs provides OpenAI Gym bindings for Rust. Dead project. Score 13, 60 stars. ([Read more](/details/gym-rs.md)) `Gym` `Rl` `Open Source`
- [rsrl](https://github.com/tspooner/rsrl) - rsrl is a fast, safe reinforcement learning framework in Rust. Dead project. Score 14, 180 stars. ([Read more](/details/rsrl.md)) `Rl` `Open Source`
- [rurel](https://github.com/milanboers/rurel) - rurel is a flexible, reusable reinforcement learning (Q learning) implementation in Rust. Score 11, 140 stars. ([Read more](/details/rurel.md)) `Rl` `Q Learning` `Open Source`

## Retrieval

- [Edgequake](https://github.com/raphaelmansuy/edgequake) - High-performance Graph-RAG framework that transforms documents into intelligent knowledge graphs for AI applications. ([Read more](/details/edgequake.md)) `Graph Rag` `Knowledge Graphs` `Open Source`

## Services

- [dust](https://github.com/dust-tt/dust) - Full service for running workflows with composable blocks using LLMs, with core implemented in Rust. ([Read more](/details/dust.md)) `Open Source` `Workflows` `Composable`

## Speech-to-Text

- [Vibe](https://github.com/thewh1teagle/vibe) - Desktop application that transcribes audio or video files in every language across platforms. Rust implementation providing accessible speech-to-text capabilities for AI-driven transcription workflows. ([Read more](/details/vibe.md)) `Open Source` `Transcription` `Multi Language`

## Stream Processing

- [arroyo](https://github.com/ArroyoSystems/arroyo) - Distributed stream processing engine in Rust for real-time data pipelines. ([Read more](/details/arroyo.md)) `Streaming` `Sql` `Open Source`

## Text Processing

- [aho-corasick](https://github.com/BurntSushi/aho-corasick) - Fast implementation of the Aho-Corasick string search algorithm in Rust, useful for multiple pattern matching in text data. ([Read more](/details/aho-corasick.md)) `String Search` `Aho Corasick` `Open Source`
- [fancy-regex](https://github.com/fancy-regex/fancy-regex) - Rust library for regular expressions with advanced features like lookaround and backreferences, enhancing text processing capabilities. ([Read more](/details/fancy-regex.md)) `Regex` `Open Source` `Advanced`
- [grex](https://github.com/pemistahl/grex) - Command-line tool and Rust library for generating regular expressions from natural language descriptions. ([Read more](/details/grex.md)) `Regex Generation` `Cli` `Open Source`
- [memchr](https://github.com/BurntSushi/memchr) - Optimized string search routines for Rust, essential for efficient text processing in AI and NLP applications. ([Read more](/details/memchr.md)) `String Search` `Open Source` `Performance`

## Tooling

- [BAML](https://github.com/BoundaryML/baml) - Simple prompting language for building reliable AI workflows and agents. Compiler written in Rust. ([Read more](/details/baml.md)) `Prompting` `Agents` `Open Source`
- [Monty](https://github.com/pydantic/monty) - Minimal, secure Python interpreter for running LLM-generated code in AI agents, with microsecond startup and sandboxing. ([Read more](/details/monty.md)) `Interpreter` `Sandbox` `Agents`

## Tools

- [gptcommit](https://github.com/zurawiki/gptcommit) - Tool to generate Git commit messages using GPT models directly from the command line. ([Read more](/details/gptcommit.md)) `Open Source` `Git` `Commit Messages`
- [spider](https://github.com/spider-rs/spider) - Rust-based web crawler/spider for dumping entire websites, useful for data collection in LLM training or RAG systems. ([Read more](/details/spider.md)) `Open Source` `Web Crawler` `Data Collection`

## Transpiling

- [aleph_ollama](https://github.com/aleph-lang/aleph_ollama) - AI-powered source code translation tool that uses the local Ollama API. ([Read more](/details/aleph_ollama.md)) `Open Source` `Ai Coding` `Ollama`

## Vector Databases

- [HelixDB](https://github.com/HelixDB/helix-db) - A powerful graph-vector database designed for intelligent data storage, particularly for RAG (Retrieval-Augmented Generation) and AI applications. It combines graph and vector capabilities to handle complex relationships and embeddings. ([Read more](/details/helixdb.md)) `Graph Database` `Vector Database` `Rag`
- [LanceDB](https://github.com/lancedb/lancedb) - A serverless, low-latency vector database for AI applications. It supports efficient storage and retrieval of high-dimensional vectors essential for AI/ML workflows like semantic search and recommendation systems. ([Read more](/details/lancedb.md)) `Vector Database` `Open Source` `Ai`
- [RuVector](https://github.com/ruvnet/ruvector) - A self-learning vector database and cognitive container that runs LLMs locally and scales horizontally. Designed for local AI inference and scalable vector operations. ([Read more](/details/ruvector.md)) `Vector Database` `Llm` `Self Learning`
- [Valentinus](https://github.com/kn0sys/valentinus) - Next generation vector database built with LMDB bindings, providing efficient storage and querying for vector embeddings in AI systems. ([Read more](/details/valentinus.md)) `Vector Database` `Lmdb` `Open Source`

## Vector Stores

- [pgvecto.rs](https://github.com/tensorchord/pgvecto.rs) - Vector database plugin for Postgres written in Rust, optimized for LLM applications and 20x faster than pgvector. ([Read more](/details/pgvectors.md)) `Open Source` `Postgres` `Vector Db`

## Voice AI

- [tambourine-voice](https://github.com/kstonekuan/tambourine-voice) - Personal AI voice interface for any app with customizable dictation using chosen models and prompts. Built in Rust. ([Read more](/details/tambourine-voice.md)) `Open Source` `Voice` `Dictation`


## ™️ Legal

All product names, logos, and brands are the property of their respective owners. All company, product, and service names used in this repository, related repositories, and associated websites are for identification purposes only. The use of these names, logos, and brands does not imply endorsement, affiliation, or sponsorship.

This directory may include content generated by artificial intelligence (AI). While efforts have been made to ensure the accuracy and reliability of the information, we make no representations or warranties of any kind, express or implied, about the completeness, accuracy, reliability, suitability, or availability of the information contained herein. Users are advised to independently verify the information before making decisions based on it.

We disclaim any responsibility for errors, omissions, or inaccuracies in the content, whether generated by humans, AI, or any other means. By using this directory, you agree to use it at your own risk and acknowledge that the information provided may not always be current or accurate.

If you believe that your intellectual property rights or other legal rights have been infringed, please contact us immediately at legal@ever.co and we will take appropriate action.

## 🛡️ License

Shield: [![CC BY-SA 4.0][cc-by-sa-shield]][cc-by-sa]

This work is licensed under a

[Creative Commons Attribution-ShareAlike 4.0 International License][cc-by-sa].

[![CC BY-SA 4.0][cc-by-sa-image]][cc-by-sa]

[cc-by-sa]: http://creativecommons.org/licenses/by-sa/4.0/

[cc-by-sa-image]: https://licensebuttons.net/l/by-sa/4.0/88x31.png

[cc-by-sa-shield]: https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg