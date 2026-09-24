---
title: Subscription lifecycle webhook guide
excerpt: Learn how to manage your subscriptions' lifecycles through webhooks.
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

This guide helps you understand which webhooks you need to properly manage subscription lifecycle and manual or automated changes to subscriptions that can occur due to anything from expiry after dunning ceases, to a bank invalidating an external mandate.

### Prerequisites

* Familiarity with Recurly Webhooks
* Basic understanding of RESTful APIs and JSON
* Access to Recurly with valid API credentials

***

# Definition

In the context of webhooks, **subscription lifecycle&#x20;**&#x69;s a long-term trackong of the health and status of a given subscription and associated behaviors can can occur during the lifetime of the customer's subscription.&#x20;

### **Event Types**

* Review our dedicated documentation for [Subscription notifications](https://docs.recurly.com/recurly-subscriptions/docs/subscription-notifications)
* The shortlist is:&#x20;
  * Basics: Created, Updated, Cancelled, Expired, Renewed, Paused
  * More specific: Reactivated (after cancellation), variations of Pause including Paused Scheduled, Pause Modified, Pause Cancelled), Resumed after Pause, Renewal Skipped, Pending Change Scheduled
  * Very specific: Mandate cancelled/inactive, Low Balance (gift cards)

### Best Practices and Notable Information

* Don't mistake `update` for `pending_change.scheduled` -- update occurs **after** a modification takes effect while `pending_change` is advanced notice (before).
* Don't treat `renewed` as a successful payment. Ensure you're listening for payment webhooks as well.&#x20;
* Use the UUID to correlate events to a subscription&#x20;
* Check the account, payment method, and subscription state before reacting to a `mandate.inactive` event. The mandate may be inactive while the subscription is active and in dunning -- for example, the customer may come into session and update their billing info.
* Subscription status events may arrive alongside a mandate.inactive event -- for example, if your Mandate settings are set to automatically expire a subscription during a customer revocation scenario, you'll receive both an expired event and a mandate.inactive event. Look for both. If you're not listening for both, query the subscription UUID to see what the status is.

<br />

<br />

<br />

<br />

<br />

<br />

<br />
