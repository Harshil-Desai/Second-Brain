---
date: 2026-05-07
tags: [system-design, data-structures, database, concept]
source: ""
status: developing
---

# What are B-tree and B+ tree

Before this note, it helps to read:

- [[Disk Structure]]
- [[What is indexing]]
- [[M-Way Search Tree]]

## Why not just use an M-way search tree?

If you read [[M-Way Search Tree]] it looks fine — so why do we need B-trees?

Because the M-way search tree's *creation process* isn't under any control. Even when the first layer isn't fully filled, it'll jump to create another layer/depth. That makes searching in an M-way search tree almost equivalent to linear search.

Suppose there are `n` elements where `n < M`. All `n` elements *should* go to the root node — no children needed. But that doesn't happen automatically because we don't control the creation process.

## The B-tree fix

A B-tree is an M-way search tree with these extra rules:

1. Each node should have at least `ceil(M / 2)` children before creating a new node.
2. The root can have a minimum of 2 children.
3. All leaf nodes must be at the same level.
4. The creation process is bottom-up.

## How a B-tree is filled

```
M =
Keys = [10, 20, 40, 50, 60, 70, 80, 30, 35]
```

![[B tree filling.excalidraw]]

Each key also contains a record pointer.

## B+ tree — what's different

In a B+ tree, **all the keys also live in the leaf nodes** — every key has a copy at the leaf level. And all leaf nodes are connected like a linked list.

![[B+ tree.excalidraw]]
