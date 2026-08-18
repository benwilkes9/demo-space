---
type: adr
title: "ADR-0001: Postgres as the incident log, component status derived not stored"
status: accepted
date: 2026-06-02
authority: prescriptive
---

# Postgres as the incident log, component status derived not stored

## Context

A component's status page badge (operational, degraded, down) has to agree
with its incident history at all times — those are read by the same visitor
on the same page. Storing status as its own column invites the two to drift:
an incident closes and the column update is a separate write that can be
missed or land out of order.

## Decision

Postgres holds incidents and updates as the source of truth. A component's
status is computed at read time from its open incidents — no status column
exists to fall out of sync.

## Consequences

- Good: there is exactly one fact to get right, not two records that can
  disagree.
- Good: replaying incident history (for uptime windows) uses the same data a
  status read does.
- Bad: every status page read does a small join instead of a column lookup.
  Acceptable at this scale; revisit if a page's component count grows large
  enough to make that join measurable.
