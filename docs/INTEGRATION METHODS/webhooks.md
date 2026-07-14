---
title: Webhooks (JSON & XML)
excerpt: >-
  Configure Recurly webhooks to receive real-time notifications about account
  events — with HTTP Basic Authentication, automatic retries, signature
  verification, and support for JSON and XML payloads.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
<div class="rp-page">
  <div class="rp-overview">Webhooks notify your systems and partner applications of events within Recurly in real time. When an event occurs — such as an account being opened — Recurly attempts to send a notification to the endpoint(s) you specify. Webhooks are configured in the Admin UI and work best alongside the Recurly API to ensure data integrity and synchronization.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
  </div>
</div>

<div class="rp-callout rp-callout-note">
  <div><strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> Configuration note</strong>Webhooks are configured in the Recurly Admin UI and cannot be configured via API. Don't rely on webhooks alone for critical functions — use them alongside API responses to ensure data integrity.</div>
</div>

# Definition

<div class="rp-definition">Webhooks are event-driven notifications that alert your systems and partner applications when something happens in Recurly. They're not standalone actions — they signal that an event occurred, and your systems should use the Recurly API to retrieve or confirm the relevant data. Use them in tandem with API responses for reliable, synchronized data handling.</div>

# Key benefits

<div class="rp-benefits rp-benefits-2x2">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-bolt" aria-hidden="true"></i></div>
    <strong>Real-time updates</strong>
    <span>Get notified of significant events in Recurly as they happen — account changes, payment events, subscription lifecycle, and more.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-shield-halved" aria-hidden="true"></i></div>
    <strong>Enhanced security</strong>
    <span>HTTP Basic Authentication and signature verification confirm that notifications originate from Recurly and haven't been tampered with.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-rotate" aria-hidden="true"></i></div>
    <strong>Automatic retries</strong>
    <span>Failed webhook deliveries are retried automatically, with exponentially increasing intervals between attempts.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-code" aria-hidden="true"></i></div>
    <strong>Payload format flexibility</strong>
    <span>Choose JSON or XML per endpoint. JSON is recommended for its lightweight format and alignment with modern best practices.</span>
  </div>
</div>

# Key details

## Configuration and security

Webhooks are configured in the Recurly Admin UI. Recurly supports HTTP Basic Authentication to confirm that requests originate from Recurly's servers. Always check the <a href="https://docs.recurly.com/docs/ip-allowlist" target="_blank">IP Allowlist documentation</a> for the current list of Recurly IP addresses and configure your endpoint to accept only those IPs.

<div class="rp-callout rp-callout-note">
  <div><strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> Apache with ModSecurity</strong>If you're using Apache with ModSecurity, you may need to disable rule #990011 in mod_security to unblock webhook delivery.</div>
</div>

***

## Webhook storage and timestamps

Each webhook notification is stored for 15 days and is accessible through the Admin Console, which also shows failure reasons. Webhook timestamps are in UTC but are translated to your site's configured timezone when viewed in the application.

***

## Automatic retries

If Recurly receives an error in response to a webhook, the notification is retried. After ten failed attempts, Recurly stops sending that notification.

The interval between retries follows this formula: `10 + x * 2^(x+5)` seconds, where `x` is the current attempt number. The first few retries happen quickly, with intervals growing exponentially from there.

***

## Manual retries

Individual notifications can be retried by clicking them and pressing **Retry**.

To bulk retry paused or failed notifications, use the appropriate button in the **Webhook Actions** dropdown.

***

## Notification types

Webhooks can be configured per endpoint — you can opt in to only the notification types relevant to that endpoint. For example, you can configure one endpoint to receive only new account notifications while excluding account update notifications.

For the full list of notification types, see the <a href="https://docs.recurly.com/recurly-subscriptions/v1.3/docs/lifecycle-events#/" target="_blank">Webhooks Developer Docs</a>.

***

## JSON vs. XML payloads

Each webhook endpoint can be configured to receive JSON or XML payloads — not both. Recurly recommends JSON for its lightweight format and alignment with modern best practices.

***

## Signature verification

For JSON payloads, Recurly signs each notification and includes the signature in a `recurly-signature` request header. Verifying this signature confirms the notification came from Recurly and hasn't been modified in transit.

***

## CSRF protection in Rails applications

For Rails applications with `protect_from_forgery` enabled, disable forgery protection for the action that listens for Recurly webhook notifications.

***

## Developer documentation

For full implementation details, see the <a href="https://docs.recurly.com/recurly-subscriptions/docs/overview-webhooks#/" target="_blank">Webhooks developer documentation</a>.
