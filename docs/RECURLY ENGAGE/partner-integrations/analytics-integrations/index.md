---
title: Analytics integrations
excerpt: High-level overview of all analytics integrations available in Recurly Engage.
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Overview

Recurly Engage can forward prompt interaction events to major analytics platforms, enabling unified visibility into user engagement alongside your existing tracking data.

### Required plan

This feature or setting is available to all customers on any Recurly Engage subscription plan.

# Definition

**Analytics integrations** allow Recurly Engage to emit prompt impressions, clicks, dismissals, timeouts, and custom goal events directly into your analytics provider of choice, preserving session and user context.

# Key details

* **Google Analytics**: Track prompt events via the Google Analytics JS SDK or server-side Measurement Protocol. ([Learn more](google-analytics))
* **Amplitude**: Forward prompt interactions through the Amplitude JS SDK, with optional inbound data sync via CSV, Webhooks, or Export API. ([Learn more](amplitude))
* **Mixpanel**: Send prompt events and user traits using Mixpanel Service Accounts and project token. ([Learn more](mixpanel))
* **mParticle**: Export prompt events and attributes to mParticle via a Custom Feed integration. ([Learn more](mparticle))
* **Heap**: Capture prompt interactions using Heap’s JavaScript SDK for automatic event capture. ([Learn more](heap))
* **Adobe Analytics**: Emit prompt events through the Experience Platform Web SDK (Alloy.js) to Adobe Analytics. ([Learn more](adobe-analytics))