# Eino

A fork of [cloudwego/eino](https://github.com/cloudwego/eino) — a powerful LLM application development framework for Go.

## Overview

Eino provides a comprehensive set of tools and abstractions for building LLM-powered applications in Go. It offers:

- **Component abstractions**: Standardized interfaces for LLMs, embeddings, retrievers, and more
- **Graph-based orchestration**: Build complex AI pipelines using directed graphs
- **Streaming support**: First-class support for streaming responses
- **Type safety**: Strongly typed components leveraging Go generics

## Features

- 🔗 **Chain & Graph orchestration** — compose LLM components into pipelines
- 🌊 **Streaming** — native support for streaming LLM responses
- 🧩 **Extensible components** — plug in any LLM, vector store, or tool
- 🔒 **Type-safe** — compile-time type checking with Go generics
- 📦 **Modular** — use only what you need

## Installation

```bash
go get github.com/your-org/eino
```

## Quick Start

```go
package main

import (
    "context"
    "fmt"
    "log"

    "github.com/your-org/eino/components/model"
)

func main() {
    ctx := context.Background()

    // Initialize your LLM model
    // (see examples/ for provider-specific setup)
    _ = ctx
    fmt.Println("Eino is ready!")
}
```

## Project Structure

```
eino/
├── components/        # Core component interfaces
│   ├── model/         # LLM model abstractions
│   ├── embedding/     # Embedding model abstractions
│   ├── retriever/     # Document retriever abstractions
│   └── tool/          # Tool/function calling abstractions
├── compose/           # Graph and chain composition
├── flow/              # Pre-built flow patterns
├── schema/            # Shared data schemas
├── experiments/       # My WIP experiments (not for upstream)
└── examples/          # Usage examples
```

## Personal Notes

> **Note (personal fork):** I'm using this primarily to experiment with the graph-based orchestration and custom retriever implementations. The `examples/` directory contains my own test cases alongside the upstream examples. Anything under `experiments/` is work-in-progress and not intended for upstream.

### My Experiments

- `experiments/custom-retriever/` — experimenting with a BM25-based retriever
- `experiments/graph-loops/` — testing cyclic graph patterns for multi-step reasoning
- `experiments/streaming-debug/` — adding verbose logging middleware to trace streaming chunk flow; useful for debugging dropped tokens
- `experiments/ollama-local/` — wiring up a local Ollama instance as a drop-in model backend; handy for offline dev without burning API credits

## Contributing

We welcome contributions! Please see our [Pull Request Template](.github/PULL_REQUEST_TEMPLATE.md) and follow the existing code style.

1. Fork the repository
2. Create your feature branch (`git checkout -b feat/my-feature`)
3. Commit your changes following our [commit conventions](.github/.commit-rules.json)
4. Push to the branch and open a Pull Request

## License

This project is licensed under the Apache License 2.0 — see the [LICENSE](LICENSE) file for details.

## Acknowledgements

Th