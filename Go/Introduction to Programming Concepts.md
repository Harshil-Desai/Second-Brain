---
date: 2026-05-07
tags: [programming, fundamentals, go]
source: ""
status: developing
---

# Introduction to Programming Concepts

## What programming is and how computers execute code

Programming is just telling the computer what to do. You write high-level logic in a programming language, and that gets converted into something the computer actually understands — 0s and 1s — because under the hood, a computer is just billions of switches turning on and off via electricity. Compilers and interpreters do the converting.

The path:

```
High-level code → IR (Intermediate Representation) → Assembly → Machine code
```

Assembly looks like:

```asm
MOV R1, 5
ADD R1, 3
CALL print
```

The CPU only understands **machine code** — the binary form of assembly. It runs a **fetch–decode–execute** cycle: fetch the binary, decode which instruction it represents, execute it.

The CPU does every operation through memory — registers or RAM. To write to disk, it uses an IO controller's register, and the IO controller writes to disk on its behalf. `if/else` and loops in a high-level language are just `JUMP` and `FLAG` instructions underneath.

## Variables, data types, basic operations

A **variable** is a space in memory. It takes the size of its data type — or, for dynamically typed languages, enough space to store a *reference* to the value. When a variable is declared, it gets a few bytes allocated, the binary form of its value is stored there, and the variable name points to that location.

**Data types** exist to fix how many bytes get allocated for a variable. The same value `5` takes different amounts of memory as an `int` vs `float` vs `string` vs `double`. The type tells the system:

- How many bytes to allocate
- How to encode/decode the value
- Which CPU instruction to use

### Basic operations

In Go:

```go
a := 5 + 3
```

In the CPU:

```asm
MOV R1, 5
MOV R2, 3
ADD R1, R2
```

### Stack vs heap

| Storage | Holds                                                                  |
| ------- | ---------------------------------------------------------------------- |
| Stack   | Value types (int, float, double, struct), function params, local variables, pointers |
| Heap    | Objects, arrays, strings, dynamically allocated data                   |

## Algorithms and problem-solving

An **algorithm** is a precise sequence of steps that transforms input into output.

A good algorithm is:

- **Deterministic** — same input produces same output
- **Finite** — it must terminate
- **Step-by-step** — clear, ordered steps
- **Unambiguous** — no room for interpretation

> A program is not the same as code. Program = code + algorithm. The code is the implementation, the algorithm is the logic — and the algorithm is free of any programming language.

Related: [[Getting Started with Go]]
