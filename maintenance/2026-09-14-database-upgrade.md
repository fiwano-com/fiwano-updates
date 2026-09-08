---
id: 2026-09-14-database-upgrade
title: PostgreSQL minor version upgrade
components: [messaging-api, message-delivery, portal]
status: scheduled
scheduled_start: 2026-09-14T01:00:00Z
scheduled_end: 2026-09-14T02:00:00Z
updates:
  - at: 2026-09-08T10:00:00Z
    status: scheduled
    body: Announced more than 72 hours in advance, so this window is excluded from the uptime calculation.
---

Sample event used while the page is being built.

The database is upgraded to the latest minor version. A short switchover is expected;
sending may return errors for a few seconds and inbound messages are retried by Meta.
