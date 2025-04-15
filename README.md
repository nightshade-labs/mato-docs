# Mato Documentation

This repository contains the documentation for Mato, built using [mdBook](https://rust-lang.github.io/mdBook/).

## Prerequisites

Before you can build and run this documentation, you need to have the following installed:

- [Rust](https://www.rust-lang.org/tools/install) (mdBook is written in Rust)
- [mdBook](https://rust-lang.github.io/mdBook/guide/installation.html)

## Installation

1. Install Rust if you haven't already:
   ```bash
   curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
   ```

2. Install mdBook:
   ```bash
   cargo install mdbook
   ```

## Building and Running

To build and serve the documentation locally:

1. Clone this repository:
   ```bash
   git clone <repository-url>
   cd mato-docs
   ```

2. Build the book:
   ```bash
   mdbook build
   ```

3. Serve the book locally (this will automatically rebuild when files change):
   ```bash
   mdbook serve
   ```

4. Open your browser and navigate to `http://localhost:3000`
