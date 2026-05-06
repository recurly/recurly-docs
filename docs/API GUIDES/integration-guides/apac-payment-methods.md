---
title: APAC Payment Methods
deprecated: false
hidden: true
metadata:
  robots: index
---
# Recommended Webhooks

In the APAC region, all supported payment methods are asynchronous, meaning transactions and invoices will be in a pending/scheduled state for a period of time (usually days) until the customer's bank or gateway integration sends a final status indicator. You can find our dedicated webhooks recommendations using the Best Practices guide below:

It is recommended to listen for all webhooks given that the supported payment methods are asynchronous (they update hours or days later with an official status).

* [Webhooks Best Practices](https://docs.recurly.com/recurly-subscriptions/docs/best-practices#/)
