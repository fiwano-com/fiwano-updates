---
id: 2026-09-12-messaging-api
title: API & message delivery unreachable from external probes
components: [messaging-api]
impact: major
status: resolved
started_at: 2026-09-12T17:49:48Z
resolved_at: 2026-09-12T18:39:33Z
opened_by: bot
updates:
  - at: 2026-09-12T18:39:33Z
    status: resolved
    body: "Resolved. Between 17:48 and 17:50 UTC on 12 September our primary hosting location lost network connectivity. Automatic failover moved the platform to our second location, which has been serving all traffic since; external probes recorded roughly one minute of unreachability. Inbound WhatsApp, Instagram and Messenger messages sent during that window were held by Meta and delivered once we were reachable again; outbound API requests that failed in that window had to be retried. No messages or customer data were lost. Both locations are fully equivalent, so no switch back is required for service continuity. Any future switch between locations is a routine automated operation that completes within seconds, with inbound messages held by Meta in the meantime."
  - at: 2026-09-12T17:50:57Z
    status: monitoring
    by: bot
    body: "External probes report the service reachable again since 17:50 UTC. Watching before this is called resolved."
  - at: 2026-09-12T17:50:08Z
    status: investigating
    by: bot
    body: "External probes report API & message delivery unreachable since 17:49 UTC. Looking into it."
---

Published automatically from external probe data; updated by hand as we learn more.
