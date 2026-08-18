---
type: architecture
title: Architecture — as built
authority: descriptive
---

# Architecture — as built

Lighthouse is one Next.js application: server-rendered status pages, an
authenticated dashboard for the owning team, and the API both call. There is
no separate backend service.

## Data

Everything — components, incidents, updates, subscribers — lives in one
Postgres database, reasoned about in [ADR-0001](adrs/0001-postgres-as-the-incident-log.md).
A component's status is never stored; it is derived at read time from its open
incidents, which is what keeps the two from disagreeing.

## Notifications

An update to an open incident enqueues one notification job per subscriber
channel (email, webhook). Delivery is at-least-once: a subscriber can see the
same update twice, never zero times, which is the trade this system takes
against showing nothing during an outage.

## Public pages vs. dashboard

The public status page and the team dashboard are the same read model behind
two authorization checks — a public page shows only resolved-enough detail,
the dashboard shows everything, including draft updates. There is one
incident record, not two views maintained separately.
