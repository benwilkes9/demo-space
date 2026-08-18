---
type: vision
title: Product vision
authority: prescriptive
---

# Lighthouse — product vision

A team's status page is usually the last thing built and the first thing
customers check during an outage. Most teams either hand-edit a static page
during the incident itself, or bolt a status page onto a tool built for
something else — a wiki, a spreadsheet, a chat channel — and it drifts out of
date the moment the incident is over.

Lighthouse is a status page that a small ops team can update from the same
place they triage the incident, and that update is what subscribers see —
there is no second step where someone "publishes" the page separately from
resolving the problem.

## Who it is for

A team of five to fifty engineers running a handful of services, who need a
public or customer-facing page but do not need — and do not want to pay for —
an enterprise incident-management suite.

## What it is not

Not a paging or on-call tool: Lighthouse does not wake anyone up. It assumes
an incident has already been noticed and starts once someone opens a page for
it. Not a monitoring tool: it has no probes of its own and takes no
measurements; every uptime figure it shows is derived from the incidents
logged against a component, not from polling it.

## What "done" looks like

An engineer sees the outage, opens an incident in Lighthouse, and writes one
update. Subscribers who opted in see that update within a minute, on the
channel they chose. When the incident closes, the page reflects that without
anyone doing a second thing.
