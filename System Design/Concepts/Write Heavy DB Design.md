---
date: 2026-05-07
tags: [system-design, database, concept, scaling]
source: ""
status: developing
---

# Write-Heavy DB Design

Databases usually use [[What are B tree and B+ tree|B+ trees]] to store data:

```
Insertion: O(log n)
Search:    O(log n)
```

Both operations need an acknowledgement from the database.

## How to scale write-heavy workloads

Reduce the unnecessary acknowledgements and headers, and reduce the IO calls.

If we condense multiple requests into a single block, send that block, and get a single acknowledgement back, we cut both ack overhead and IO calls.

```
Single IO call → single IO response
→ better utilisation of time and bandwidth
```

Condense the data query into a single query.

## Trade-off

- **Drawback:** the server needs extra memory to condense these queries.
- **Advantage:** fewer IO operations.

> [!Information]- Fastest data structure that can help you write quickly?
> Linked list — O(1).

A log follows the same pattern.
