---
title: Global Payment Methods
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview 

blah

# Payment Methods

## Credit Cards

Generally speaking, when processing cards in the EMEA region, you can follow standard guides (see below), however these countries require authenticating the consumer via 3DS. We offer 3DS on our most popular gateways for both new customers and stored billing information for return customers.

You can find this information separately in our [3DS Integration Guide](https://docs.recurly.com/recurly-subscriptions/docs/3d-secure-20-integration-guide#/). For verifying or using Stored Billing Information with 3DS, see our [Stored billing information guide](https://docs.recurly.com/recurly-subscriptions/docs/using-3d-secure-with-stored-billing-information#/).

## Mobile Wallets

### Apple Pay

<br />

### Google Pay

### Amazon Pay

### PayPal 

# Recommended Webhooks

In the EMEA region, some payment methods are synchronous and some are Asynchronous. You can find our dedicated webhooks recommendations using the Best Practices guide below:

It is recommended to listen for all webhooks given that some payment methods are asynchronous (they update hours or days later with an official status), and some are synchronous (the payment status is known immediately).

* [Webhooks Best Practices](https://docs.recurly.com/recurly-subscriptions/docs/best-practices#/)
