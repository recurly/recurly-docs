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