---
title: 'Third Party Checkout: Stripe and Adyen'
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

#### Stripe Gateway

* Stripe Payment or Express Checkout Elements is currently supported when using the Recurly V3 API. Visit our [developer hub](https://recurly.com/developers/guides/) for more information. Read more about enabling Stripe Payment Elements in the [Developer Hub guide](https://recurly.com/developers/guides/third-party-checkout-stripe-elements.html).

#### Adyen Gateway

* Adyen Web Components is currently supported when used in combination with Recurly.js. Visit our [developer hub](https://recurly.com/developers/guides/) for more information. Read more about enabling Adyen Web Components in the [Developer Hub guide](https://recurly.com/developers/guides/).

### Limitations

* Third Party Checkout utilizes Gateway Tokens. Gateway failover and migrating to a different gateway will not be possible without involving the gateway that is storing the payment instruments. Reach out to Recurly support with any questions.
* Certain APMs and payment methods are restricted to merchants operating in certain countries. If you do not see one of the above payment methods available to enable in your Stripe Dashboard, your account merchant country of origin does not qualify to use it.
  * Example: Revolut is restricted to merchants operating in the UK and EU only. US merchants are unable to enable it.