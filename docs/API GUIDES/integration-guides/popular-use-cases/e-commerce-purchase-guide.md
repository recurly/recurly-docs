---
title: E-Commerce Purchase Guide
excerpt: >-
  Learn how to use the store_billing_info field to optionally store payment data
  for pure ecommerce processing.
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

This guide shows you how to use the V3 <Anchor target="_blank" href="https://recurly.com/developers/api/v2021-02-25/#operation/create_purchase">Purchases endpoint</Anchor> to create a transaction where Recurly \_does not store the payment details\_. This behavior is limited to specific payment methods presently, so ensure you are using the right gateway and payment method.

If you have a gateway payment method combo that is not listed below -- please submit a [feature request](https://example.com).

### Prerequisites & limitations

* Familiarity with Recurly’s API and basic REST concepts
* [Completed the Quickstart Guide](https://docs.recurly.com/recurly-subscriptions/docs/quick-start-guide#/)
* A gateway + payment method where Recurly supports ecommerce transactions
* Supported Gateways and Payment Methods&#x20;
  * GCash when using dLocal (requires non-storage)
  * Credit Cards when using Adyen
* For Credit Card payments on Adyen, all customer-initiated features are supported including Level 2 processing, Level 3 processing, dynamic descriptors, Adyen's fraud ID usage, Kount, 3DS, and more. For any specific questions, please reach out to Support.

# Definition

**Creating Purchases** refers to the process of generating new customer accounts alongside a transaction in a single, consolidated call to the Recurly Purchase endpoint. This streamlines checkout experiences by bundling all required resources into one request.

**eCommerce** **Transaction** refers to an online-based transaction, where the customer is in session in your Checkout flow, and wants to make a one-time purchase (for physical or digital items, as an example) rather than signing up for a subscription.

**Billing Info and Payment Method Storage** refers to the ability and practice of storing a payment method instrument on file for future usage.&#x20;

## eCommerce Use Cases

If you have specific need to allow customers to process transactions without storing their billing info, this page is for you. Example use cases:&#x20;

* Guest / Checkout - a logged-in subscriber wants to buy a one-off item (merch, add-on, upsell) and pay with a different card than the one on file, without disturbing the subscription's default payment method.
* Time-based subscription models - a subscription-model where customers make one time purchases and must return to session after a period of time.&#x20;
* Single-use APMs by design - payment methods like GCash that are inherently redirect/voucher-based and have no vaulting concept — you still need a way to complete the purchase.
* Gift-Subscriptions: A customer buys a subscription or one-time item for someone else and doesn't want their card or payment method to become that recipient's stored payment method. Keep in mind, this would appear as a line item via API versus a plan code with no set payment method.
* An AP team pays down an outstanding invoice or past-due balance with a corporate card that isn't meant to become the account's recurring payment method.
* Regional data residency rules -- jurisdictions that restrict cross-border card storage, so one-time processing sidesteps the residency requirement entirely.
* Short trials -- customer wants to test a purchase flow or make a small one-off buy without risk of it silently becoming the subscription's payment method on next renewal.

## Requirements&#x20;

* You must be using the Purchase endpoint&#x20;
* You must pass the `store_billing_info` field set to `false`&#x20;
* You must be using a supported gateway and payment method. See limitations and prerequisits.

<br />

&#x20;

<br />
