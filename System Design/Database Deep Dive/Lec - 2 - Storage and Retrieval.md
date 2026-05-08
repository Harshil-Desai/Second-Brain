---
date: 2026-05-07
tags: [system-design, database, lecture]
source: ""
status: developing
---

# Lec 2 — Storage and Retrieval

## How do databases store data?

**Hardware:** magnetic tape, solid state drives.

**Algorithms used when storing data:**

- B+ trees
- Pages
- Hash tables
- Pointers
- Log-structured merge trees (LSM)

In most cases this part is treated as a black box.

## How do databases read data?

| id (int) | first_name (string) | last_name (string) | email (string) | dob (date) |
| -------- | ------------------- | ------------------ | -------------- | ---------- |
|          |                     |                    |                |            |
|          |                     |                    |                |            |

```sql
select * from table where <condition> group by <clause> having <aggregation> order by <column> limit <number>;
```

The **query optimiser** decides how to run a query so it executes the fastest.

## How indexes are stored

Indexes are stored as **B+ trees**, fast lookups are facilitated by **hash tables**, and foreign-key relationships are implemented with **pointers**.

Related:
- [[What are B tree and B+ tree]]
- [[Write Heavy DB Design]]

Previous: [[Lec - 1 - What are Databases]]
Next: [[Lec - 3 - What is nosql database]]
