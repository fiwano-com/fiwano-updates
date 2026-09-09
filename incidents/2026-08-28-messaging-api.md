---
id: 2026-08-28-messaging-api
title: Intermittent availability during a network incident at our hosting provider
components: [messaging-api, website]
impact: major
status: resolved
started_at: 2026-08-28T17:28:00Z
resolved_at: 2026-08-28T18:16:00Z
updates:
  - at: 2026-09-09T16:51:00Z
    status: resolved
    body: "Retrospective record, added when the Fiwano status page was launched. On 28 August an incident with network equipment at our hosting provider's Vienna data center (provider report: netcup-status.de, 28 August 2026) caused intermittent availability problems for Fiwano over about 48 minutes. Inbound WhatsApp, Instagram and Messenger messages were held by Meta and delivered after connectivity returned; outbound API requests that failed during this period had to be retried."
  - at: 2026-09-09T16:51:00Z
    status: resolved
    body: "Root cause and fix: automatic failover to our second location did not take over. A configuration defect in the failover setup, uncovered during its switch-over that same week, had kept it out of service. The defect was fixed and the database cluster went live across both locations on 29 August. On 31 August a full failover-and-failback drill confirmed automatic recovery in 94 seconds with no data loss, and since 2 September the standby location keeps a pre-built copy of the current release so a failover does not wait on a deploy. A provider incident at one location now means a short automatic switch, not an outage. We also brought forward the launch of this public status page: since 1 September availability is measured by an independent external prober and published continuously, so the record no longer depends on our own reporting."
---
