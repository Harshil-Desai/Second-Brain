---
date: 2026-05-07
tags: [system-design, database, lecture]
source: ""
status: developing
---

# Lec 1 — What are Databases

A database is a system where you can store data — anywhere you need to **store, update, or retrieve** structured data, that's a database.

## Should the frontend talk to the database directly?

A database can technically act like a server (the frontend talking to it directly), but it's not a good practice. Doing that tightly couples your application/business logic to the database. If you ever need to switch databases, you end up rewriting the business logic too.

## Database vs file structure

A database is similar to a file structure but a lot more structured. It has:

- Well-defined types
- Unique identifiers
- Relations
- Memory management through types

## Persistence

Databases are *expected* to be persistent (almost — replicas help, but corrupted hardware is still a real risk). In-memory data doesn't persist — it dies when the machine crashes or shuts down. The trade-off: in-memory databases are faster than disk-backed ones.

Next: [[Lec - 2 - Storage and Retrieval]]
