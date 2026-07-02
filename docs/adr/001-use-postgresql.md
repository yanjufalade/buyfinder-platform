# ADR-001

## Title

Use PostgreSQL as the primary relational database.

---

## Status

Accepted

---

## Context

BuyFinder requires:

- ACID transactions
- Referential integrity
- Complex relational queries
- Future scalability
- Excellent Spring Boot support

---

## Decision

PostgreSQL will be used as the primary relational database.

---

## Consequences

Positive

- Excellent SQL compliance
- Rich indexing
- JSON support
- Strong transaction guarantees

Negative

- Slightly steeper learning curve compared to MySQL