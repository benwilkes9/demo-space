---
type: glossary
title: Glossary
authority: descriptive
---

# Glossary

**Component** — a named part of the service a status page reports on, such as
"API" or "Dashboard". A component has exactly one status at any time and that
status is derived from its open incidents, never set directly.

**Incident** — a record of a problem affecting one or more components, from
open to resolved. An incident is the only way a component's status changes;
there is no separate "set status" action.

**Update** — a timestamped note posted to an open incident. Subscribers are
notified on each update, not just on open and resolve.

**Subscriber** — someone who has opted in to notifications for a status page,
by email or webhook. A subscriber follows the whole page, not individual
components.

**Uptime window** — the percentage of a trailing period (7, 30 or 90 days)
during which a component had no open incident. Computed from incident
history; Lighthouse holds no independent measurement of whether a component
was actually reachable.
