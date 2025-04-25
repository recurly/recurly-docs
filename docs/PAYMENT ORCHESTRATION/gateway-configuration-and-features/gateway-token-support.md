---
title: Gateways and Token support
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

Tokens come in all shapes and sizes, and in payments, is an overloaded word. There are different types of tokens that Recurly supports internally and with our various gateways with varying levels of portability, expiry, and interoperability. The three types of tokens this article will focus on are:

* Network Tokens: A card token derived by the Network (such as Visa) that can be sent to many different gateways. It is not bound to a single gateway provider.
* Gateway Tokens: A payment method "token" derived by an individual gateway that can contain payment instrument data for multiple different payment methods including cards, bank details, and wallet details. Gateway tokens are tied to the provider they come from.
  * For example, Adyen gateway tokens can only be used with Adyen, and are not usable on Stripe or Braintree.
* One-time Use Tokens: A type of token that can only be used once, typically has a short lifespan (and sometimes expires), and is only useful for porting sensitive data from a merchant's website to Recurly via API. These tokens cannot be used for renewals and are only created and used for consumer checkout experiences.
  * Examples include: Recurly.js tokens, Stripe c\_tokens (for Payment Elements), and Braintree nonces.

### Required plan

This feature is available to all customers on any plan.

### Prerequisites

To use gateway tokens from a supported gateway, or import them, it is important to ensure that Recurly supports the logic to handle this piece of data properly. Overall, for cards and certain Direct Debit payment methods, Recurly stores this information in our systems encrypted, and does not tokenize the payment method. This storage ensures that you, as a merchant, can [configure multiple gateways](https://docs.recurly.com/docs/gateway-configuration#/) for a truly scaleable and flexible business.

### When does Recurly Tokenize?

In certain cases though, we do tokenize payment methods where necessary or desirable with certain gateways. See below for a supported list:

* **Stripe**: all payment methods are tokenized, though Recurly also retains card data. When using Payment Elements, however, Stripe retains the payment data and Recurly does not have access to raw PAN / card data. We also support Stripe confirmation tokens or 'c-tokens', that we exchange with Stripe for reusable 'Payment Method IDs' which are Stripe's reusable gateway tokens. We only receive gateway tokens from Stripe on approved payments.
* **Braintree**: Dependent on settings in your gateway configuration, but Recurly can create Braintree tokens for future usage. See Braintree documentation for more details. When checking out through Recurly.js or a hosted page such as Checkout, we create a Braintree 'nonce' which is a one-time use token. These tokens can be exchanged for reusable Braintree gateway tokens for renewals.
* **Adyen**: Presently, only non-card payment methods are tokenized when using native Recurly checkout flows. When using Adyen Components with Recurly.js, all payment methods are tokenized.
* **Vantiv**: Imported card tokens are supported. Recurly does not tokenize cards with Vantiv. For imported token usage, Recurly does not have access to the raw PAN / card information for gateway failover or orchestration to other gateway providers.
* **Amazon**: By design, all payment methods are stored at Amazon, and Recurly stores a billing agreement or charge permission ID for renewals and one-time payments with Amazon V1 and V2.
* **PayPal**: By design, all payment methods are stored at PayPal, and Recurly retains a token or billing agreement for renewals and one-time payments with all PayPal gateways. One caveat is PayPal Complete, where we do retain the raw card details or 'PAN' as well as create a PayPal gateway token for renewals.

### Limitations

* Where we only have a Gateway Token, gateway failover to other gateways is not possible.

* Imported tokens do not display payment methods details in most cases.

* Where we only have a Gateway Token, Account Updater for cards is not possible.

# Definition

A gateway token, which can be an overloaded term, is a value that references a payment instrument (card, bank account, cash app token, etc.) that is stored at a partner gateway. Gateway tokens are not transferrable to other gateways, meaning if you are using Adyen tokens for renewals on Recurly, that subscription cannot be processed on Stripe.

# Key benefits

* **Benefit:** Sentences...
* **Benefit:** Sentences...
* **Benefit:** Sentences...

# Key details