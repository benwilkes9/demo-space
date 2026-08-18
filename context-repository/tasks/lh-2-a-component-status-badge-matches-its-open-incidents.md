---
type: story
title: A component's status badge matches its open incidents
authority: prescriptive
id: LH-2
status: awaiting-human-review
---

# A component's status badge matches its open incidents

As a **status page visitor**, I want a component's badge to reflect its
actual open incidents, so that the page never shows "operational" while an
incident against it is still open.

## Acceptance criteria

- The badge is computed from open incidents at read time — no stored status
  column to drift out of sync ([ADR-0001](../architecture/adrs/0001-postgres-as-the-incident-log.md)).
- Two open incidents of different severity against the same component show
  the worse of the two.
- Closing the last open incident against a component returns its badge to
  operational on the next read, with no separate action.

## Notes for the reviewer

Implementation is done and the join performs fine at current component
counts. Flagging for review because the severity-ranking rule (worse of the
two) is asserted in code but not yet written down anywhere a non-engineer
would find it — worth deciding whether that belongs in the glossary before
this closes.
