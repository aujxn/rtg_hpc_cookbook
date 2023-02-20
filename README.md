# RTG HPC Cookbook

A collection of guides and tips for getting started with HPC
targeted towards mathematics students at PSU getting started
with research computing who have little to no background in
working with Linux systems.

# Building this book

To build the `html` locally you must have `cargo` and `mdBook` installed.

## Getting dependencies

```bash
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
cargo install mdbook
```

## Clone and build

```bash
git clone https://github.com/aujxn/rtg_hpc_cookbook.git hpc_book
cd hpc_book
mdbook build
```

Check out:
- [mdBook book](https://rust-lang.github.io/mdBook/index.html)
- [rustlang](https://www.rust-lang.org/)

# Contributing

Contributions welcome, just submit a merge request through github.

# License

[MIT](./LICENSE.md)
