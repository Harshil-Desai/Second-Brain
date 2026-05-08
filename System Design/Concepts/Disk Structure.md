---
date: 2026-05-07
tags: [system-design, database, concept, storage]
source: ""
status: developing
---

# Disk Structure

![[Disk Structure.excalidraw]]

## Vocabulary

- **Tracks** — logical concentric circles (❌ not physical). Data is written along tracks.
- **Sectors** — the smallest *physical* storage unit on the disk.
- **Blocks** — the smallest unit of data the OS can read or write. Typically 512 bytes.

A block address can be represented as `(track number, sector number)`.

**Offset** = each byte's address inside a block.

```
block address + offset = a particular byte
```

## How reads work

Data is *never* read directly from disk. It's always brought into main memory first, and the program reads it from there.

## A useful framing

- Organising data in main memory for ease of access → **data structures**
- Organising data on disk for ease of access → **database management**

Related: [[What is indexing]], [[What are B tree and B+ tree]]
