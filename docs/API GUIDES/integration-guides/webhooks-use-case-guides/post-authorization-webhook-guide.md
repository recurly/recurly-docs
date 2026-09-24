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

## Lifecycle of a Subscription&#x20;

The standard path a subscription moves through starts with creation:

1. **Creation** — created fires when the subscription is first established.

2. **Steady state**, with two paths for changes:
   1. Immediate or already-applied changes → `updated` (upgrade, downgrade, or renewal date change — fired right away if the change is immediate, or at renewal if the change was deferred to that point)
   2. `Deferred changes` → `pending_change.scheduled` fires first as advance notice, then `updated` fires later when the change actually takes effect at renewal

3. Each billing term rollover → `renewed` fires whenever the subscription enters a new term, independent of whether payment succeeded.

4. Optional `pause` branch (subscription can enter this from active state):
   1. `pause.scheduled` — pause is scheduled, with&#x20;
      1. paused_at/resumed_at/remaining_pause_cycles set
   2. `pause.modified` — scheduled pause duration changed before it takes effect
   3. `pause.canceled` — scheduled pause called off before it takes effect (fields go nil)
   4. `paused` — subscription actually moves active → paused
   5. `enewal.skipped` — each billing cycle that's skipped while paused, decrementing `remaining_pause_cycles`
   6. `resumed` — subscription moves paused → active again, new billing cycle starts

5. Cancellation branch:
   1. `canceled` — subscription set to not renew, but stays valid until `expires_at`
   2. From here, either:
      1. `reactivated` — customer reactivates before expiration, returning to active state, or
      2. `expired` — the canceled subscription reaches expires_at and is no longer valid

6. Alternate route to cancelation or expiration — `expired` can also fire directly from an active subscription if it's refunded and terminated immediately, bypassing canceled entirely. `canceled` or `expired` can can also occur directly from `active` if the mandate is revoked and rendered inactive.

Cross-cutting events (not part of the linear path, can occur at various points):

1. `mandate.inactive` — the payment madate is revoked (by gateway, bank, or customer), which resolves the subscription to either canceled or expired depending on mandate revocation settings
2. `low_balance` — gift-card-funded subscription's balance runs low

### **Event Types**

* Review our dedicated documentation for [Subscription notifications](https://docs.recurly.com/recurly-subscriptions/docs/subscription-notifications)
* The shortlist is:&#x20;
  * **Basics**: Created, Updated, Cancelled, Expired, Renewed, Paused -- these events are highly recommended for all merchants consuming webhooks to understand the state of their subscriptions at all times.
  * **Advanced**: Reactivated (after cancellation), variations of Pause including Paused Scheduled, Pause Modified, Pause Cancelled), Resumed after Pause, Renewal Skipped, Pending Change Scheduled -- for merchants using pause functionality or advanced pause scheduling, or allowing customers to reactivate / resume after a cancellation or pause, these are also critical, but their importance depends on your business model and integration.
  * **Payment Method Specific:** Mandate inactive, Low Balance (gift cards) -- you will only receive these if you are using Recurly gift card behavior (low balance), or a payment method that uses mandates for subscriptions, such as UPI AutoPay, or SEPA Direct Debit.

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
