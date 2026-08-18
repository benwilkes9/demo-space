---
type: story
title: An incident can be scheduled maintenance
authority: prescriptive
id: LH-6
status: backlog
---

# An incident can be scheduled maintenance

As an **incident owner**, I want to announce planned maintenance in advance,
so that a known, scheduled window does not read on the status page the same
as an unplanned outage.

## Acceptance criteria

- A maintenance incident carries a start and end time and is visible on the
  status page before it starts, labelled distinctly from an active outage.
- A component under scheduled maintenance does not count against its uptime
  windows for that period.
- Subscribers are notified once on scheduling and once on start, not on
  every edit to the announcement beforehand.

## Open question

Whether a maintenance window should auto-close at its end time or require an
owner to close it — needs a decision before this is ready to build.
