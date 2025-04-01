---
title: Gateway Token Support
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

### Required plan

This feature is available to all customers on any plan.

### Prerequisites

To use gateway tokens from a supported gateway, or import them, it is important to ensure that Recurly supports the logic to handle this piece of data properly. Overall, for cards and certain Direct Debit payment methods, Recurly stores this information in our systems encrypted, and does not tokenize the payment method. This storage ensures that you, as a merchant, can [configure multiple gateways](https://docs.recurly.com/docs/gateway-configuration#/) for a truly scaleable and flexible business.

In certain cases though, we do tokenize payment methods where necessary or desirable with certain gateways. See below for a supported list:

* **Stripe**: all payment methods are tokenized, though Recurly also retains card data.
* **Braintree**: Dependent on settings in your gateway configuration. See Braintree documentation for more details.
* **Adyen**: Presently, only non-card payment methods are tokenized when using native Recurly checkout flows. When using Adyen Components with Recurly.js, all payment methods are tokenized.
* **Vantiv**: Imported card tokens are supported. Recurly does not tokenize cards with Vantiv.
* **Amazon**: By design, all payment methods are stored at Amazon, and Recurly stores a billing agreement or charge permission ID for renewals and one-time payments with Amazon V1 and V2.
* **PayPal**: By design, all payment methods are stored at PayPal, and Recurly retains a token or billing agreement for renewals and one-time payments with all PayPal gateways.

## Overview

A gateway token, which can be an overloaded term, is a value that references a payment instrument (card, bank account, cash app token, etc.) that is stored at a partner gateway. Gateway tokens are not transferrable to other gateways, meaning if you are using Adyen tokens for renewals on Recurly, that subscription cannot be processed on Stripe.

### Limitations

* Gateway failover to other gateways

* Imported tokens do not display payment methods details

# Key benefits

* **Benefit:** Sentences...
* **Benefit:** Sentences...
* **Benefit:** Sentences...

# Key details

## Additional details

Sentences...

### Best Practices for Descriptors

* Sentences...