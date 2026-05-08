---
date: 2026-05-07
tags: [system-design, data-structures, concept]
source: ""
status: developing
---

# M-Way Search Tree

![[M-way-search-tree.excalidraw]]

## Binary search tree (recap)

- Each node holds 1 key
- At most 2 children
- Left child is always smaller than the root
- Right child is always bigger than the root
- The root is larger than the whole left subtree
- The root is smaller than the whole right subtree

## M-way search tree

- Each node holds at most `m - 1` keys
- At most `m` children
- The 1st child is smaller than all the keys
- The 2nd child lies between the 1st and 2nd key
- …and so on
- The same property must hold recursively for every subtree

> A binary search tree is just a 2-way search tree.

Related: [[What are B tree and B+ tree]]
