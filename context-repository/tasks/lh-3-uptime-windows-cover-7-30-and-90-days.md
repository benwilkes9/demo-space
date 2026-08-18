---
type: story
title: Uptime windows cover 7, 30 and 90 days
authority: prescriptive
id: LH-3
status: in-progress
---

# Uptime windows cover 7, 30 and 90 days

As a **status page visitor**, I want to see how reliable a component has been
recently, so that one open incident today does not read the same as a
component down all month.

## Acceptance criteria

- Each component shows uptime percentage for trailing 7, 30 and 90 day
  windows, derived from incident history per the [glossary](../product/glossary.md).
- A component with no incident history in a window shows 100%, not blank or
  an error.
- A component created less than 90 days ago shows only the windows it has
  history for.

## Notes for whoever picks this up

7- and 30-day windows are done. 90-day is blocked on deciding how far back
Lighthouse is expected to retain incident history at all — no retention
policy exists yet, so the query has nothing to bound it to.
