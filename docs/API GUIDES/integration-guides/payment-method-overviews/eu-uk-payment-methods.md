---
title: NA (North American) Payment Methods
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

This document provides detailed API instructions for processing payments via Cards, ACH, Venmo, and Cash App with a critical focus on navigating the region's options for payments. You'll find links to our existing guides for subscription management for new and existing customers, Recurly.js requirements, and explanations for payment methods ensuring your integration is fully compliant, reduces transaction declines, and provides a seamless checkout experience for your customers across North America.

# Key Details

There are several gateways and payment methods that support the North American region including **GATEWAYS**. It is recommended to look at our [Quickstart guide](https://docs.recurly.com/recurly-subscriptions/docs/quick-start-guide#/), [Purchase guide](https://docs.recurly.com/recurly-subscriptions/docs/purchases-guide#/), Pricing and billing guides, and [Subscription management guides](https://docs.recurly.com/recurly-subscriptions/docs/managing-subscription-methods-guides#/) as well so you have a full picture of integrating with Recurly outside of specific payment methods.

**Payment Methods and Gateways:**

* **[Cards](https://docs.recurly.com/recurly-subscriptions/docs/credit-cards#/)**: Compliant support on all modern gateways with the exception of Ebanx.
* [ACH](https://docs.recurly.com/recurly-subscriptions/docs/ach-bank-payments#/): Supported on Stripe, Adyen, WorldPay, GoCardless, and Check Commerce. Compliant with NACHA regulations and pre-debit checks on Adyen, WorldPay, and Stripe. If you are using GoCardless or Check Commerce, you must satisfy this requirement via an external solution such as Plaid.
* [Cash App Pay](https://docs.recurly.com/recurly-subscriptions/docs/cash-app-pay#/): Supported on Stripe, Adyen, and Braintree.
* [Venmo](https://docs.recurly.com/recurly-subscriptions/docs/pay-with-venmo#/): Supported on Braintree.
* AmazonPay US: Supported via AmazonPay V1 and V2.

Additionally, integrations supporting credit cards will require 3DS to comply with SCA/PSD2 regulations in the EU and UK regions. For co-badged regions, such as France, Belgium and Denmark, we also support customer preference via [CoBadge](https://docs.recurly.com/recurly-subscriptions/docs/co-badged-cards-guide#/) solutions.

# Payment Methods

## Credit Cards

Generally speaking, when processing cards in the North American region, you can follow standard guides (see below). While 3DS is not strictly required in the US and Canada, the industry is moving in that direction, so it is recommended to discuss options with your gateway and merchant account provider before deciding to implement 3DS behaviors on Recurly.

We offer 3DS on our most popular gateways for both new customers and stored billing information for return customers.

You can find this information separately in our [3DS Integration Guide](https://docs.recurly.com/recurly-subscriptions/docs/3d-secure-20-integration-guide#/). For verifying or using Stored Billing Information with 3DS, see our [Stored billing information guide](https://docs.recurly.com/recurly-subscriptions/docs/using-3d-secure-with-stored-billing-information#/).

## Direct Debit

Recurly supports Direct Debit processing in the US via ACH. ACH is a US only payment method.

### ACH

### BACS

## Realtime Bank Payments

### iDeal

### Sofort / Klarna Debit Risk

## Wallets

### Revolut

# Recommended Webhooks

In the North American region, some payment methods are synchronous and some are Asynchronous. You can find our dedicated webhooks recommendations using the Best Practices guide below:

It is recommended to listen for all webhooks given that some payment methods are asynchronous (they update hours or days later with an official status), and some are synchronous (the payment status is known immediately).

* [Webhooks Best Practices](https://docs.recurly.com/recurly-subscriptions/docs/best-practices#/)
