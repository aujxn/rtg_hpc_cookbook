# Introduction

This is a simple guide to getting set up using NGsolve on the
Coeus (see-us) High Performance Computing (HPC) cluster.

The [OIT RC website](https://sites.google.com/pdx.edu/research-computing/home)
has lots of usefull information as well, some of which is repeated in this guide.

Other useful resources include:
- [Slurm Reference](https://slurm.schedmd.com/documentation.html)
- [MPI Specification](https://www.mpi-forum.org/docs/mpi-4.0/mpi40-report.pdf)
- [Ubuntu's Linux command line for beginners](https://ubuntu.com/tutorials/command-line-for-beginners#1-overview)
- [Git Reference](https://git-scm.com/docs)
- [NGSolve Docs](https://docu.ngsolve.org/latest/)
- [Python Docs](https://docs.python.org/3/)

The Basic, Intermediate, and Advanced chapters contain general tips and
procedures for working remotely on Linux servers. All of the topics covered
are only briefly mentioned and are not meant to be complete guides, but act
as a starting point for doing more in depth research.

The NGSolve chapter has specific instructions for getting setup and running
the example codes.

## Building this book

To build the `html` locally you must have `cargo` and `mdBook` installed.

### Getting dependencies

```bash
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
cargo install mdbook
```

### Clone and build

```bash
git clone https://github.com/aujxn/rtg_hpc_cookbook.git hpc_book
cd hpc_book
mdbook build
```

Check out:
- [mdBook book](https://rust-lang.github.io/mdBook/index.html)
- [rustlang](https://www.rust-lang.org/)

## Contributing

Contributions welcome, just submit a merge request through github.
