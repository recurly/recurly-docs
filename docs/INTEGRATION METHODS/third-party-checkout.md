---
title: 'Third Party Checkout: Stripe Elements'
excerpt: >-
  To better serve our customer base and keep up to speed with the expansion of
  payment methods and wallets, we are building support for our most trusted
  gateway partners' checkout solutions and enabling Recurly merchants to use
  them within the Recurly ecosystem.
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Overview

By using the massive wealth of APMs built by our most trusted and well-established partners, you will be able to quickly and easily enable a wide range of payment options, catering to diverse customer preferences and expanding their potential market reach.

The Ecommerce checkout options from our trusted gateway partners are designed to be user-friendly and highly customizable, allowing you to maintain a consistent brand experience while ensuring secure and reliable payment processing.

## Supported Gateways and Features

#### Stripe gateway

Using Stripe Web Elements is currently supported when using the Recurly V3 API. Visit our [developer hub](https://recurly.com/developers/guides/) for more information:

<Image align="center" className="border" border={true} width="300px" src="https://files.readme.io/bd6ee4314c74650eada8d5e8a62c0318b14857d22b69644925b570645a5a4e61-Stripe_Payment_element.png" />

* When using Stripe Elements, you can build a custom checkout solution and pass a Stripe "confirmation token" to Recurly via API. Recurly will pass that token to Stripe to obtain reusable payment details for recurring and one-time payments.
* If customers wish to update their billing information, they can do so through Stripe Elements, or through an existing Recurly solution such as Checkout, HPP, or Recurly.js. What you choose to offer is up to you!
* Use Stripe's demo website to see what's possible: [https://checkout.stripe.dev/elements](https://checkout.stripe.dev/elements) while keeping in mind limitations to what Recurly has built and allowed.

Read more about enabling Stripe Payment Elements in the [Developer Hub guide](https://recurly.com/developers/guides/).

### Supported Payment Methods

* **Stripe gateway**: Recurly does not support all Stripe payment methods at this time. Presently, the below options are available:
  * Cards, Link by Stripe, Apple Pay, Google Pay, Cash App Pay
  * Direct Debit offerings include: ACH, SEPA, BACS, iDeal, and BECS.
    * [Financial Connections](https://stripe.com/financial-connections) is required for verifying bank information prior to signup.
  * Other APMs include: Klarna Recurring (Pay Now, Pay Later, and BNPL), Revolut

### Limitations

* **Stripe gateway**: We do not support Stripe Payment Links, Stripe Checkout, or Radar at this time. See the limited list of payment methods available, or visit the [Stripe gateway documentation](https://docs.recurly.com/docs/stripe) in Recurly docs.
* Certain APMs and payment methods are restricted to merchants operating in certain countries. If you do not see one of the above payment methods available to enable in your Stripe Dashboard, your account merchant country of origin does not qualify to use it.
  * Example: Revolut is restricted to merchants operating in the UK and EU only. US merchants are unable to enable it.