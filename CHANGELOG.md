# Changelog

New capabilities and meaningful improvements to Fiwano, newest first. Follow new entries in your feed reader via the [Atom feed](https://fiwano.com/changelog.atom). The same record is published on [GitHub](https://github.com/fiwano-com/fiwano-updates).

> **How we ship.** Fiwano has no version numbers. The API contract is `v1`, and it has been stable since the public launch in March 2026. Every change is additive: new endpoints, new optional fields and parameters, new webhook event types. Existing fields keep their names, types and meaning, and new webhook events are never enabled on your channels without your action. Your integration only needs to ignore fields and event types it does not know. If a breaking change ever becomes unavoidable, it ships as a new API version alongside `v1`, announced here and by email in advance, and `v1` keeps working.

## 11 September 2026

### New: Public changelog

This page. New capabilities and meaningful improvements, newest first, with an [Atom feed](https://fiwano.com/changelog.atom) and a copy on [GitHub](https://github.com/fiwano-com/fiwano-updates).

## September 2026

### New: Public status page

[status.fiwano.com](https://status.fiwano.com): live component status, uptime history and an incident record kept in public git, so past events cannot be quietly rewritten.

### New: Instagram and Messenger conversation routing

Conversations that another app controls through Meta's handover protocol are handled explicitly: messages arriving while your channel is on standby are still delivered as `message.received`, and a send into such a conversation is rejected with an actionable hint instead of a generic Meta error. [Docs: Errors](https://fiwano.com/documentation#errors)

### New: Message echo events

`message.echo` delivers a copy of messages your business sends outside Fiwano (WhatsApp Business app, Instagram inbox, Facebook Page inbox, Meta Business Suite, another integration), with optional delivered and read statuses for those echoes. Opt-in per channel. [Docs: Event Types](https://fiwano.com/documentation/webhooks#event-types)

## August 2026

### Improved: Ownership conflicts

A WhatsApp number, Instagram account or Page that is already connected in another Fiwano account is reported clearly at connect time, with a contact path, instead of failing silently.

### Improved: Outbound pacing

Sends are paced per channel to stay within Meta's limits. When a channel or the platform is momentarily at capacity, the API answers with an explicit retry hint (`429` or `503` with `Retry-After`) instead of a rejected Meta call. [Docs: Sending Messages](https://fiwano.com/documentation/sending-messages)

### Improved: Infrastructure refactored for 99.99% availability

Our high-availability setup was rebuilt with a 99.99% uptime target: faster, fully automatic recovery from component failures, with incoming messages preserved throughout.

### Improved: Delivery failure notifications

Failure notifications to channel owners are consolidated into one digest email per channel, with the exact error and what to do about it, instead of one email per event.

## July 2026

### Improved: WhatsApp recipient validation

Obviously invalid recipients are rejected before any Meta call, with a specific reason in the response. [Docs: Sending Messages](https://fiwano.com/documentation/sending-messages)

### Improved: Sender profiles

The sender profile endpoint returns richer Messenger profiles (name and picture, when Meta provides them), with fallback sources when the primary lookup is unavailable. [Docs: Sender Profile](https://fiwano.com/documentation/webhooks#sender-profile)

### Improved: Template sends tracked like any message

WhatsApp template sends get the same Fiwano message ID and delivery status events as free-form messages. [Docs: Templates](https://fiwano.com/documentation/templates)

### New: Subscriptions endpoint

`GET /subscriptions` lists your plans and free channel slots, so an integration can check capacity before connecting a channel. [Docs: Subscriptions](https://fiwano.com/documentation/subscriptions)

### Improved: Connecting Instagram and Messenger with several accounts

Connecting is more convenient and reliable when one Facebook user manages several Instagram accounts or Pages: choose the right one in Meta's dialog in a single login, and Fiwano resolves Meta's asset selection reliably even when accounts change over time. [Docs: Channels](https://fiwano.com/documentation/channels)

## June 2026

### New: Integration playbook on GitHub

The [Fiwano cookbook](https://github.com/fiwano-com/fiwano-cookbook): a step-by-step integration playbook with the API reference alongside it, written for AI coding agents and people alike.

### New: Multi-page documentation

Documentation rebuilt as task-oriented pages with a Quickstart, an OpenAPI spec and an interactive API reference; also available as one Markdown file for AI agents. [Docs](https://fiwano.com/documentation)

### Improved: Connect and reconnect flow

Instagram and Messenger connections moved to Meta's Facebook Login for Business: fewer steps, asset selection inside Meta's own dialog. Any channel can be reconnected in place: same channel ID, same webhook settings, same license. [Docs: Channels](https://fiwano.com/documentation/channels)

## May 2026

### Improved: Media sending

Media sends are validated before the Meta call (URL, type) and return specific errors instead of a generic Meta failure. [Docs: Sending Messages](https://fiwano.com/documentation/sending-messages)

### New: Brazil and India

Localized pages for [Brazil](https://fiwano.com/br) (pt-BR, including the documentation) and [India](https://fiwano.com/in), with reference pricing in BRL and INR.

### New: Verified n8n node

`n8n-nodes-fiwano` is a verified n8n community node: WhatsApp, Instagram and Messenger in n8n workflows without code. [Docs: n8n](https://fiwano.com/documentation/n8n)

### New: WhatsApp Embedded Signup

Connect a WhatsApp number through Meta's official Embedded Signup flow in minutes: Cloud API, or Coexistence to keep using the WhatsApp Business app alongside the API. [Docs: Channels](https://fiwano.com/documentation/channels)

## April 2026

### Improved: Inbound path rebuilt

The inbound webhook path was rebuilt for higher throughput and lower relay latency from Meta to your endpoint.

### Improved: Automatic retries

Failed webhook deliveries and outbound sends are retried with backoff; the delivery status is reported once the outcome is known. [Docs: Retry Policy](https://fiwano.com/documentation/webhooks#retry-policy)

### New: Per-channel webhook events

Choose which events each channel delivers (`message.received`, `message.delivered`, `message.read` and more). Nothing is delivered until you enable it. [Docs: Event Types](https://fiwano.com/documentation/webhooks#event-types)

## March 2026 (Public launch)

### New: Public launch

Fiwano goes public: fiwano.com, self-service sign-up, licenses and billing. The `v1` API contract is frozen from this point.

### New: Facebook Messenger

Third channel behind the same API: connect a Facebook Page, then receive and send Messenger messages with the same request and webhook formats.

## February 2026 (Alpha)

### New: Delivery status events

Sent, delivered and read statuses arrive as webhook events.

### New: WhatsApp message templates

Create, submit for approval and send WhatsApp templates from the portal and the API.

## January 2026 (Alpha)

### New: Alpha with integrator friends

A few integrators we know start building on the API. First production traffic outside our own platform.

### New: Meta Tech Provider

Fiwano becomes a Meta Tech Provider: businesses connect WhatsApp and Instagram through Fiwano's verified app, without their own Meta app or app review.

## November 2025 (Private use)

### New: Fiwano begins as an internal API

Built for our own client platform: WhatsApp and Instagram conversations behind one interface.
