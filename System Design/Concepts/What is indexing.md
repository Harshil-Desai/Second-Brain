---
date: 2026-05-07
tags: [system-design, database, indexing, concept]
source: ""
status: developing
---

# What is Indexing

## Setup

| 10 bytes | 50 bytes | 10 bytes    | 8 bytes  | 50 bytes |     |     |             |
| -------- | -------- | ----------- | -------- | -------- | --- | --- | ----------- |
| eid      | name     | dept        | section  | add      |     | eid | pointer     |
| 1        | Harshil  | Engineering | Software | AMD      |     | 1   | its address |
| 2        | Hemanshi | Product     | product  | PUN      |     | 2   | its address |
| ...      | ...      | ...         | ...      | ...      |     | ... | ...         |
| 100      | Chinki   | Catnip      | catpin   | PUN      |     | 100 | its address |

```
Total bytes per row  = 128 bytes
Bytes in a block     = 512
Rows per block       = 4
Total blocks used    = 25
```

## The naive case

If I run `select * from employees where eid = 1`, how does it find the row quickly?

It has to visit 25 blocks at most. Slow. Quicker way?

## With an index

Indexes (shown on the right of the table above) are also stored on disk:

```
eid      = 10 bytes (assumed)
pointer  =  6 bytes (assumed)
Total    = 16 bytes per row
Rows per block   = 32
Blocks required  = 100 / 32  ≈ 4
```

Now we only visit ~4 blocks to find a row.

## Sparse index

If the data grows much larger — say 1,000 rows — that becomes ~40 blocks of index, which is again a lot to scan.

**Solution:** create another index on top of the first one. For every 32 blocks of the lower-level index, add one entry in this new index. Now only ~2 blocks are needed.

This is called a **==sparse index==**.

## Multilevel indexing

![[Multilevel Indexing.excalidraw]]

So far we've talked about creating indexes manually, which isn't feasible. We want something that:

- Creates indexes automatically as the database grows
- Removes indexes when data is deleted and multi-level indexes are no longer needed

> If you turn the diagram above upside down, it looks like a tree (B-tree / B+ tree 😉).

Related: [[What are B tree and B+ tree]], [[Disk Structure]]
