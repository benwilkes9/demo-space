---
type: story
title: A draft update is invisible on the public page
authority: prescriptive
id: LH-4
status: ready
---

# A draft update is invisible on the public page

As an **incident owner**, I want to draft an update before it goes out, so
that I can get the wording right without subscribers seeing an
in-progress note.

## Acceptance criteria

- A draft update appears on the dashboard read model but not the public page
  read model, per [Architecture — Public pages vs. dashboard](../architecture/architecture.md#public-pages-vs-dashboard).
- Publishing a draft is the action that triggers subscriber notification —
  saving a draft does not.
- A draft is visible to any teammate with dashboard access, not only its
  author.
