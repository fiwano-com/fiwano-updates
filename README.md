# Fiwano updates

The public record behind [status.fiwano.com](https://status.fiwano.com): every incident and every
planned maintenance window of the Fiwano platform, one file per event.

The status page renders what this repository holds and nothing else. Updates are appended to the
event's file as we learn more, so the git history is the audit trail: what was said, when, and
by whom. Nothing here is rewritten or removed afterwards.

## Layout

| Path | Contents |
|---|---|
| `incidents/YYYY-MM-DD-<component>.md` | An incident: `title`, affected `components`, `impact`, lifecycle `status` (`investigating` → `identified` → `monitoring` → `resolved`), `started_at`, `resolved_at`, and the `updates` trail |
| `maintenance/YYYY-MM-DD-<component>.md` | A planned maintenance window: `title`, `components`, `status` (`scheduled` → `in_progress` → `completed`), `scheduled_start`, `scheduled_end`, `updates` |

All timestamps are UTC. Updates marked `by: bot` were written automatically from external probe
data; the status page labels them "automated". Everything else was written by a person.

Component ids match the rows on the status page: `messaging-api` (API & message delivery) and
`website` (Website & documentation).

## Follow the status

- Current status: https://status.fiwano.com
- Incident history: https://status.fiwano.com/incidents
- Atom feed: https://status.fiwano.com/history.atom
- JSON, Statuspage v2 format: https://status.fiwano.com/api/v2/summary.json
- How availability is measured: https://status.fiwano.com/#how-we-measure

## Contributing

This repository is a record, not a project: pull requests and issues are not accepted. Questions
go to [contact@fiwano.com](mailto:contact@fiwano.com).

## License

The content is published under [CC BY-ND 4.0](LICENSE): share it with attribution, unmodified.
