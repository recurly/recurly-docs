---
title: APAC Payment Methods
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

This document provides detailed API instructions for processing payments via UPI AutoPay in India and BECS in Australia. 

# Key Details

There are three gateways and three payment methods that support the APAC region including Stripe, GoCardless, and Ebanx.

**Payment Methods and Gateways:**

* **Cards**: Supported on Stripe only.
* **BECS**: Supported on Stripe (Third PartyCheckout Only), and GoCardless
* **UPI AutoPay**: Supported on Ebanx

# Recommended Webhooks

In the APAC region, all supported payment methods are asynchronous, meaning transactions and invoices will be in a pending/scheduled state for a period of time (usually days) until the customer's bank or gateway integration sends a final status indicator. You can find our dedicated webhooks recommendations using the Best Practices guide below:

It is recommended to listen for all webhooks given that the supported payment methods are asynchronous (they update hours or days later with an official status).

* [Webhooks Best Practices](https://docs.recurly.com/recurly-subscriptions/docs/best-practices#/)
