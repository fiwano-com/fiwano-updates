---
id: 2026-09-05-messaging-api-errors
title: Elevated error rate on the Messaging API
components: [messaging-api]
impact: minor
status: resolved
started_at: 2026-09-05T09:12:00Z
resolved_at: 2026-09-05T09:41:00Z
updates:
  - at: 2026-09-05T09:15:00Z
    status: investigating
    body: We are seeing elevated 5xx responses on message sending and are investigating.
  - at: 2026-09-05T09:28:00Z
    status: identified
    body: A backlog in the outbound relay is causing the errors. A fix is being applied.
  - at: 2026-09-05T09:41:00Z
    status: resolved
    body: Error rates are back to normal. Messages that failed to send returned an error and were not lost silently.
---

Sample event used while the page is being built.

For about 29 minutes, part of the requests to `POST /api/v1/messages` returned 5xx errors.
Inbound messages from Meta were unaffected and were processed after the backlog cleared.
