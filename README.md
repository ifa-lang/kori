# Kori — Package Manager & Build Orchestrator for IFA

`kori` is the official, deterministic package manager, dependency resolver, and build orchestrator for the **IFA Systems Programming Language** (`ifa-lang`).

## Features

- **Autonomous & Pure IFA Architecture**: Self-contained toolchain designed to build, resolve, package, and test IFA modules.
- **Deterministic SemVer Resolution**: Reproducible dependency graph resolution conforming to Semantic Versioning 2.0.0.
- **Content-Addressable Package Cache**: Packages cached and verified using cryptographically strict BLAKE3 checksums.
- **Multi-Target Build Orchestration**: Native standalone binaries, IFA libraries (`.ifalib`), C-ABI dynamic/static shared objects, and WebAssembly (`wasm32-wasi`, `wasm32-unknown`).
- **Integrated Unit Testing Engine**: Automated test runner discovering and executing autonomous unit and integration tests across package boundaries.

## Package Manifest (`kori.toml`)

```toml
[package]
name = "my_service"
version = "0.1.0"
edition = "2026"
authors = ["Author Name <author@example.com>"]
license = "MIT OR Apache-2.0"
description = "High-performance network microservice"

[dependencies]
std = { path = "../std" }

[targets]
bin = [
    { name = "my_service", path = "src/main.ifa" }
]
lib = { name = "my_service", path = "src/lib.ifa", crate_types = ["ifalib"] }
```

## CLI Usage

```bash
# Build the project defined in kori.toml
kori build

# Run project unit and integration tests
kori test

# Package the project into an autonomous distributable archive
kori package

# Format IFA source files
kori fmt
```

## License

Licensed under either of:
- Apache License, Version 2.0 ([LICENSE-APACHE](LICENSE-APACHE))
- MIT license ([LICENSE-MIT](LICENSE-MIT))

at your option.
