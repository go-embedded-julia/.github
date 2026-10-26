<p align="center"><img src="https://raw.githubusercontent.com/go-embedded-julia/brand/main/social/go-embedded-julia.png" alt="go-embedded-julia" width="720"></p>

# go-embedded-julia

🌐 **[Website](https://go-embedded-julia.github.io)** · 📚 **[Documentation](https://go-embedded-julia.github.io/docs/)** · 🗺️ **[Roadmap](https://github.com/go-scikit/roadmap)**

**A pure-Go, embeddable Julia interpreter.** It mirrors [go-embedded-ruby](https://github.com/go-embedded-ruby), whose `rbgo` is the Ruby VM behind go-notebook's `ruby` cells: this one is meant to back its `julia` cells and its WebAssembly playground.

**Status: in development, milestones M0 (the oracle harness) and M1 (the parser).** Nothing is released yet.

## What it will be

- **Julia's front end, in Go.** JuliaSyntax (the parser) and JuliaLowering ported to Go.
- **An interpreter over lowered IR**, running **Julia's own Base unchanged**. Base is evaluated at build time and the resulting heap is shipped as an image.
- **The runtime boundary on fleet libraries.** Intrinsics and `ccall` targets map onto Go, with go-bignum, go-ndarray, go-fft and the regexp stack standing in for GMP and MPFR, BLAS and LAPACK, FFTs and PCRE2.

## Milestones

| | Milestone | Size | State |
|---|---|---|---|
| M0 | oracle harness: a Go tool that runs the reference `julia` on a corpus and stores its outputs | S | in development |
| M1 | parser: a Go port of `JuliaSyntax/src` | L | in development |
| M2 | lowering and macro expansion: a Go port of `JuliaLowering/src` | L | planned |
| M3 | Core runtime: types, subtyping, dispatch, 83 builtins, 94 intrinsics, the interpreter | XL | planned |
| M4 | Base bootstrap and image | XL | planned |
| M5 | numeric boundary: GMP and MPFR on `math/big` and go-bignum, PCRE2, utf8proc, Random, LinearAlgebra | L | planned |
| M6 | notebook bridge and go-scikit/julia | M | planned |
| M7 | WebAssembly playground | M | planned |

Sizes are the plan's: S days, M weeks, L months, XL several months.

## Honest scope

It is an interpreter. It keeps Julia's semantics, not its native speed; heavy computation goes through the Go libraries.

## Licences

Julia is MIT. The GPL parts of SuiteSparse are avoided.

## Repositories

| Repo | What it is |
|------|------------|
| [**docs**](https://github.com/go-embedded-julia/docs) | the documentation site (Hugo + Hextra), served at [/docs/](https://go-embedded-julia.github.io/docs/) |
| [**go-embedded-julia.github.io**](https://github.com/go-embedded-julia/go-embedded-julia.github.io) | the landing page (Hugo) |
| [**brand**](https://github.com/go-embedded-julia/brand) | logo, icons and social images |

The plan is the roadmap's bibliography, [`bib/julia.md`](https://github.com/go-scikit/roadmap/pull/12) in go-scikit/roadmap.
