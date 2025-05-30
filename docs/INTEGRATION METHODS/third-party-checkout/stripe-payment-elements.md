---
title: Stripe payment elements
excerpt: >-
  Accept and tokenize Stripe Payment Elements in Recurly for a fully
  customizable, secure checkout experience.
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

Stripe offers powerful tools to support quick and dynamic consumer checkout solutions including Payment Elements and Express Checkout Elements. Recurly supports ingesting the Stripe confirmation token in our V3 APIs for payment processing.

### Prerequisites & limitations

* Requires a working Recurly V3 API integration and Recurly.js setup.
* Some Stripe payment methods and APMs are restricted by merchant country—if you don’t see a method in your Stripe Dashboard, your account’s country may not qualify (e.g. Revolut is available only in the UK/EU).
* Stripe Payment Links, Stripe Checkout, and Radar are not supported through this integration.

# Definition

Stripe Payment Elements lets you build a fully branded checkout UI using Stripe’s hosted components, then pass a “confirmation token” to Recurly’s V3 API to process payments and store reusable payment details for both one-time and recurring charges.

# Key benefits

* **Customizable checkout**: Design your own UI with Stripe Elements for a seamless, on-brand experience.
* **Seamless tokenization**: Send Stripe confirmation tokens to Recurly for secure, PCI-compliant payment processing.
* **Wide payment support**: Offer cards, wallets, direct debits, and select APMs—all within your custom checkout flow.

# Key details

## Supported features

* Build a bespoke checkout solution with Stripe Payment Elements or Express Checkout Elements and pass the resulting confirmation token to Recurly via the V3 API.
* Allow customers to update their billing information through Stripe Elements or existing Recurly solutions (Checkout, HPP, Recurly.js).
* Preview Stripe Elements capabilities on Stripe’s demo site: [https://checkout.stripe.dev/elements](https://checkout.stripe.dev/elements)

<Image align="center" className="border" border={true} width="300px" src="https://files.readme.io/bd6ee4314c74650eada8d5e8a62c0318b14857d22b69644925b570645a5a4e61-Stripe_Payment_element.png" />

Read more about enabling Stripe Payment Elements in the [Developer Hub guide](https://recurly.com/developers/guides/).

## Supported payment methods

* **Cards, Link by Stripe, Apple Pay, Google Pay, Cash App Pay**
* **Direct Debit**: ACH, SEPA, BACS, iDEAL, BECS (requires [Financial Connections](https://stripe.com/financial-connections))
* **Other APMs**: Klarna Recurring (Pay Now, Pay Later, BNPL), Revolut