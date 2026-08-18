---
type: story
title: An update notifies every subscriber channel
authority: prescriptive
id: LH-1
status: done
---

# An update notifies every subscriber channel

As a **subscriber**, I want an incident update to reach me on the channel I
picked, so that I hear about an outage from Lighthouse rather than from
noticing the outage myself.

## Acceptance criteria

- Posting an update enqueues one notification job per subscriber channel
  (email, webhook).
- Delivery is at-least-once — a subscriber may see a duplicate, never a gap.
- A failed webhook delivery retries; it does not block email delivery to the
  same subscriber.

## Notes

Shipped as described in
[Architecture — Notifications](../architecture/architecture.md#notifications).
