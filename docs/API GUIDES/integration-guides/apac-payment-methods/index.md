---
title: APAC Payment Methods
excerpt: >-
  Learn how to implement APAC payment methods with Recurly to accept payments
  across the APAC (Asia Pacific) regions.
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

This document provides detailed API instructions for processing payments via Card processing in India on Stripe, UPI AutoPay in India on Ebanx, GCash on dLocal in the Philippines, and BECS in Australia on supported gateways.

# Key Details

There are four gateways and four payment methods that support the APAC region including Stripe, GoCardless, dLocal, and Ebanx.

**Payment Methods and Gateways:**

* **Cards**: Supported on Stripe only.
* **BECS**: Supported on Stripe (Third PartyCheckout Only), and GoCardless
* **UPI AutoPay**: Supported on Ebanx
* **GCash:&#x20;**&#x53;upported on dLocal

Card acceptance in India on Stripe requires usage of 3DS. You can find 3DS documentation in our dedicated Recurly.js guides.

# Recommended Webhooks

In the APAC region, most supported payment methods are asynchronous, meaning transactions and invoices will be in a pending/scheduled state for a period of time (usually days) until the customer's bank or gateway integration sends a final status indicator. You can find our dedicated webhooks recommendations using the Best Practices guide below:

It is recommended to listen for all webhooks given that the supported payment methods are asynchronous (they update hours or days later with an official status).

* [Webhooks Best Practices](https://docs.recurly.com/recurly-subscriptions/docs/best-practices#/)
