---
type: story
title: A subscriber can follow one component, not the whole page
authority: prescriptive
id: LH-5
status: backlog
---

# A subscriber can follow one component, not the whole page

As a **subscriber**, I want to follow just the components I depend on, so
that a page with many components does not notify me about ones I don't use.

## Why

Today a subscriber follows the whole page ([glossary](../product/glossary.md)),
which is the right default for a page with two or three components and the
wrong one once a team has ten. This has come up from more than one
customer running a page of that size.

## Acceptance criteria

- A subscriber may choose all components (today's behaviour, still the
  default) or a subset.
- An update against a component the subscriber does not follow sends no
  notification to them.
- Existing subscribers are migrated to "all components" rather than losing
  notifications on this shipping.
