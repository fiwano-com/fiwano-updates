---
id: 2026-09-27-messaging-api
title: Brief API and website outage during automatic failover
components: [messaging-api, website]
impact: major
status: resolved
started_at: 2026-09-27T20:46:38Z
resolved_at: 2026-09-28T03:07:18Z
opened_by: bot
updates:
  - at: 2026-09-28T03:07:18Z
    status: resolved
    body: "Resolved. A server failure made the API and website unavailable for under two minutes (20:45–20:47 UTC). Our systems failed over automatically and service has been running normally since. No data was lost, and Meta redelivered the messages that arrived during the gap."
  - at: 2026-09-27T20:48:08Z
    status: monitoring
    by: bot
    body: "External probes report the service reachable again since 20:47 UTC. Watching before this is called resolved."
  - at: 2026-09-27T20:47:18Z
    status: investigating
    by: bot
    body: "External probes report API & message delivery, Website & documentation unreachable since 20:46 UTC. Looking into it."
---

Published automatically from external probe data; updated by hand as we learn more.
