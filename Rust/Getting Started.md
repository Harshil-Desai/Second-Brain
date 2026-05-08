---
date: 2026-05-07
tags: [rust, language, fundamentals]
source: ""
status: developing
---

# Getting Started with Rust

```rust
fn main() {
    println!("Hello, world!");
}
```

Like in C, every Rust program has a `main` function that runs when the program is executed. To compile:

```
rustc main.rs
```

`.rs` is the Rust file extension. The compiler produces `main.exe` and (on Windows only) `main.pdb`. Run `main.exe` to see the output. The `.pdb` file holds debugging information.

## Macros vs functions

Notice the `!` in `println!`. That makes it a **Rust macro**, not a function (`println` would be a function). Rust macros are a way to write code that generates code — they extend Rust syntax. Macros don't always follow the same rules as functions.

## Syntax note

Rust expressions end with a semicolon.

Next: [[Hello, Cargo!]]
