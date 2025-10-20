---
title: Purchase
deprecated: false
hidden: true
link:
  new_tab: false
metadata:
  robots: index
---
# Purchase API Integration

If you're integrating with the Purchase API, you can combine one-time charges, subscriptions, and other purchase-related components into a single invoice. This makes it easier for businesses with complex sales cycles to generate one invoice for a customer. See [Purchase API](https://docs.recurly.com/recurly-subscriptions/docs/create-subscription#subscription-options-considerations) for further details.

## Payment Notifications

Payment notifications inform you of transaction lifecycle events—ACH schedules, captures, failures, voids, refunds, and status updates. XML payloads include the full `<transaction>` element; JSON payloads focus on event metadata. Most integrations can ignore these legacy webhooks and rely on subscription- and invoice-level notifications or query transactions via the API.

For more information, see [Payment Notifications](https://docs.recurly.com/recurly-subscriptions/docs/payment-notifications#/payment-notifications).

ADditional context for subscriptions:

## Subscription Lifecycle

#### Future

Future subscriptions have a start date in the future. The most common use case for a future subscription is a B2B contract where the subscription is agreed to start on a specific date. The customer is not invoiced until the start date.

#### Active

Active subscriptions are both regular paying subscriptions and subscriptions currently in a trial.

#### Canceled

Canceled subscriptions will automatically expire at the term renewal date. A subscription could be in a canceled state because the customer chose to cancel their auto-renewing subscription or the subscription is set to expire at the end of their current term.

#### Expired

Expired subscriptions are churned subscriptions that cannot be reactivated. A subscription can be expired due to involuntary churn by the dunning cycle or voluntary churn by canceling.

## View Your Subscriptions

[Your subscriptions dashboard][1] provides an overview of all [accounts][2] with subscriptions managed by Recurly. From this view, you can sort your subscriptions by account, plan code, subscription status, subscription creation date, or next subscription invoice date. The filters on this view allow you to bucket accounts by subscription status for easy sorting. Categories overlap and are not necessarily distinct, _e.g._ the **Live** filter will return both **Renewing** and **Canceled** subscriptions.

[1]: https://app.recurly.com/go/subscriptions

[2]: /docs/accounts

#### All

All subscriptions.

#### Renewing

Active subscriptions that will renew. Paused subscriptions are also considered as renewing.

#### Future Start

Subscriptions that will become active when the start date arrives.

#### Last Billing Period

Subscriptions that are in their last remaining billing period in their current term and set to expire at the end of the term.

#### Paused

Active subscriptions that are currently paused and will not be invoiced.

#### Canceled

Subscriptions that will expire at the end of their subscription term.

#### Expired

Subscriptions that are no longer active.

#### Trial

Active subscriptions that are in a trial period.

#### Paying

Active subscriptions that are no longer in trial.

## Create a Subscription

To subscribe your customers to one of your plans, you can create a subscription on the customer's account. A customer can have multiple subscriptions to different plans or the same plan. <a href="https://docs.recurly.com/docs/create-subscription">Learn more</a>

## Change a Subscription

A change to the customer's subscription is most often an upgrade or downgrade, but can also include changes to how the subscription is invoiced. Changes can be made immediately in the current billing cycle or at the next term renewal. <a href="https://docs.recurly.com/docs/change-subscription">Learn more</a>

## Postpone a Subscription's Renewal Date

Postpone a subscription to shorten or lengthen a customer's current billing period. Postpone is useful for backdating or pausing subscriptions. <a href="https://docs.recurly.com/docs/postpone-subscription">Learn more</a>

## Expire a Subscription

When a customer elects to end their subscription at the next bill date, this is called **canceling** the subscription. If you decide to end the subscription early, mid-cycle, this is called **terminating** the subscription. Both result in the subscription **expiring**. Once a subscription is expired, it cannot be reactivated. Only a canceled subscription can be **reactivated**, which just means the customer changed their mind and decided to continue the subscription before the renewal date where the subscription was set to expire.  <a href="https://docs.recurly.com/docs/expire-subscription">Learn more</a>
