---
date: 2026-05-07
tags: [rust, cargo, tooling]
source: ""
status: developing
---

# Hello, Cargo!

**Cargo** is Rust's package manager (similar to `npm`). You use it to initialise a project and add dependencies.

## Creating a new project

```
cargo new <project_name>
```

(Similar to `npm create vite`.)

This creates a project with `src/main.rs` and `Cargo.toml`, and automatically initialises a git repo. You can disable that with `--vcs` options.

## Cargo.toml

`Cargo.toml` is to Rust what `package.json` is to Node.

```toml
[package]
name = "hello_cargo"
version = "0.1.0"
edition = "2024"

[dependencies]
```

> TOML = Tom's Obvious, Minimal Language

- `[package]` is a section header — the lines beneath it configure the package.
- `[dependencies]` is the section header for dependencies. Each dependency listed here is called a **crate**.

## Project layout

Cargo expects source files to live in the `src/` directory. The top-level directory is for README files, configuration files, and license info — nothing else.

You can also run `cargo init` to add a `Cargo.toml` to an existing project (turning a normal project into a cargo project — though it's rarely needed in practice).

## Building

```
cargo build
```

```
PS E:\Projects\rust-projects\hello_cargo> cargo build
   Compiling hello_cargo v0.1.0 (E:\Projects\rust-projects\hello_cargo)
    Finished `dev` profile [unoptimized + debuginfo] target(s) in 1.80s
```

This creates a `target/` folder (similar to `dist/` or `build/`). The executable lives at `target/debug/hello_cargo.exe`:

```
PS E:\Projects\rust-projects\hello_cargo> .\target\debug\hello_cargo.exe
Hello, world!
```

`cargo build` also creates `Cargo.lock`, which pins the exact versions of dependencies in your project.

## Run

Usually you'll just use:

```
cargo run
```

This builds the executable and runs it in one step.

```
PS E:\Projects\rust-projects\hello_cargo> cargo run
    Finished `dev` profile [unoptimized + debuginfo] target(s) in 0.38s
     Running `target\debug\hello_cargo.exe`
Hello, world!
```

If nothing changed since the last build, there's no compile step — it just runs.

## Check

```
cargo check
```

Quickly checks that the code compiles without producing an executable. Useful to run periodically while writing — keeps `cargo build` fast and surprise-free.

## Release

```
cargo build --release
```

Optimised build for production.

Previous: [[Getting Started]]
