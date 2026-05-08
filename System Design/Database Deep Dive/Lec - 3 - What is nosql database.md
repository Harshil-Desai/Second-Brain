---
date: 2026-05-07
tags: [system-design, database, nosql, lecture]
source: ""
status: developing
---

# Lec 3 — What is a NoSQL Database

Databases that can't be queried using SQL queries are called **NoSQL databases**. They're usually:

- Key-value stores
- Document-oriented stores

Roughly speaking — a persistent version of a hashmap.

## Are databases consistent?

It depends on the application:

- For unimportant data (likes, view counts), strong consistency isn't required.
- Usually databases are consistent (a sort of single source of truth) and should always be available to incoming requests.

## What is a Database Management System (DBMS)?

A DBMS decides:

- **Where** any piece of data should be stored or kept — e.g. when an application has multiple databases for different types of data, the DBMS routes the data to the right one
- **How** to enforce storage configuration (foreign keys, primary keys, constraints)
- **How** to keep read replicas coordinated

Previous: [[Lec - 2 - Storage and Retrieval]]
