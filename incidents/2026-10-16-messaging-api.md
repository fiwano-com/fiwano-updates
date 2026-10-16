---
id: 2026-10-16-messaging-api
title: Brief API and website outage
components: [messaging-api, website]
impact: major
status: resolved
started_at: 2026-10-16T17:55:41Z
resolved_at: 2026-10-16T19:02:44Z
opened_by: bot
updates:
  - at: 2026-10-16T19:02:44Z
    status: resolved
    body: "One of our servers had a network problem, which caused a brief interruption of the API and website between 17:55 and 17:57 UTC on 16 October, lasting under two minutes. No data was lost. API requests that failed during the interruption should be retried."
  - at: 2026-10-16T17:57:10Z
    status: monitoring
    by: bot
    body: "External probes report the service reachable again since 17:56 UTC. Watching before this is called resolved."
  - at: 2026-10-16T17:56:19Z
    status: investigating
    by: bot
    body: "External probes report API & message delivery, Website & documentation unreachable since 17:55 UTC. Looking into it."
---

Published automatically from external probe data; updated by hand as we learn more.
