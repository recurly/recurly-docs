---
title: Gateways and Token support
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

Tokens come in all shapes and sizes, and in payments, is an overloaded word. There are different types of tokens that Recurly supports internally and with our various gateways with varying levels of portability, expiry, and interoperability. The three types of tokens this article will focus on are:

### Required plan

This feature is available to all customers on any plan.

### Prerequisites

To use gateway tokens from a supported gateway, or import them, it is important to ensure that Recurly supports the logic to handle this piece of data properly. Overall, for cards and certain Direct Debit payment methods, Recurly stores this information in our systems encrypted, and does not tokenize the payment method. This storage ensures that you, as a merchant, can [configure multiple gateways](https://docs.recurly.com/docs/gateway-configuration#/) for a truly scaleable and flexible business.

### Limitations

* Where we only have a Gateway Token, gateway failover to other gateways is not possible.

* Imported tokens do not display payment methods details in most cases.

* Where we only have a Gateway Token, Account Updater for cards is not possible.

# Definition

A gateway token, which can be an overloaded term, is a value that references a payment instrument (card, bank account, cash app token, etc.) that is stored at a partner gateway. Gateway tokens are not transferrable to other gateways, meaning if you are using Adyen tokens for renewals on Recurly, that subscription cannot be processed on Stripe. We support other types of tokens as well, so the space becomes confusing as Recurly makes use of all types of tokens to support the complex payments space.

* **Network Tokens**: A card token derived by the Network (such as Visa) that can be sent to many different gateways. It is not bound to a single gateway provider.
* **Gateway Tokens**: A payment method "token" derived by an individual gateway that can contain payment instrument data for multiple different payment methods including cards, bank details, and wallet details. Gateway tokens are tied to the provider they come from.
  * For example, Adyen gateway tokens can only be used with Adyen, and are not usable on Stripe or Braintree.
* **One-time Use Tokens**: A type of token that can only be used once, typically has a short lifespan (and sometimes expires), and is only useful for porting sensitive data from a merchant's website to Recurly via API. These tokens cannot be used for renewals and are only created and used for consumer checkout experiences.
  * Examples include: Recurly.js tokens, Stripe c\_tokens (for Payment Elements), and Braintree nonces.

# Key benefits

* **Network Tokens:** Using a network token instead of a gateway token assures that you can failover to other gateways if you use multiple providers. You can also move existing subscriptions to other gateways if you choose to leave your current gateway for another one that supports network tokens.
* **Gateway Tokens:** With gateway tokens, this assures that your gateway has full control over the payment instrument, and if you are using Account Updater with your gateway partner, those details will remain up to date. Downsides arise when you wish to move to another gateway partner with Recurly, or use certain features that require the full payment instrument stored in our system. See limitations for more information.
* **One-time Use Tokens:** Security and reduced PCI Scope! Usage of an R.js token or Stripe confirmation tokens (ctokens) ensure that your customer's sensitive data does not touch your servers. However, these tokens are ephemeral, and cannot be stored for future usage. Ensure you are passing these tokens to Recurly in a timely manner to avoid complications and data loss.

## Key Details

### When does Recurly Tokenize?

In certain cases though, we do tokenize payment methods where necessary or desirable with certain gateways. See below for a supported list:

* **Stripe**: all payment methods are tokenized, though Recurly also retains card data. When using Payment Elements, however, Stripe retains the payment data and Recurly does not have access to raw PAN / card data. We also support Stripe confirmation tokens or 'c-tokens', that we exchange with Stripe for reusable 'Payment Method IDs' which are Stripe's reusable gateway tokens. We only receive gateway tokens from Stripe on approved payments.
* **Braintree**: Dependent on settings in your gateway configuration, but Recurly can create Braintree tokens for future usage. See Braintree documentation for more details. When checking out through Recurly.js or a hosted page such as Checkout, we create a Braintree 'nonce' which is a one-time use token. These tokens can be exchanged for reusable Braintree gateway tokens for renewals.
* **Adyen**: Presently, only non-card payment methods are tokenized when using native Recurly checkout flows. When using Adyen Components with Recurly.js, all payment methods are tokenized.
* **Vantiv**: Imported card tokens are supported. Recurly does not tokenize cards with Vantiv. For imported token usage, Recurly does not have access to the raw PAN / card information for gateway failover or orchestration to other gateway providers.
* **Amazon**: By design, all payment methods are stored at Amazon, and Recurly stores a billing agreement or charge permission ID for renewals and one-time payments with Amazon V1 and V2.
* **PayPal**: By design, all payment methods are stored at PayPal, and Recurly retains a token or billing agreement for renewals and one-time payments with all PayPal gateways. One caveat is PayPal Complete, where we do retain the raw card details or 'PAN' as well as create a PayPal gateway token for renewals.

### Who Stores the Payment Information?

Sometimes, with all the different terms and token types, it can become confusing to understand who really has the card or payment details in their system. Use this handy table to understand where the card or payment instrument is stored, depending on your gateway solution, payment method and the checkout system you're using.

| Checkout Solution/ Use Case       | Payment Method                             | Gateway                       | Who Stores the Payment Instrument? |
| :-------------------------------- | :----------------------------------------- | :---------------------------- | :--------------------------------- |
| Recurly.js or API                 | Cards                                      | Any, except Stripe, Braintree | Recurly                            |
| Recurly.js or API                 | Cards                                      | Stripe, Braintree             | Recurly and Stripe or Braintree    |
| Recurly.js or API                 | Bank Accounts (ACH, SEPA, BACS, BECS)      | GoCardless                    | Recurly and GoCardless             |
| Imported Tokens                   | Any                                        | Token Supportive Gateways     | The Gateway                        |
| Recurly.js                        | APMs (Wallets like Cash App, PayPal, etc.) | Adyen                         | Adyen                              |
| Stripe Payment / Express Elements | Any                                        | Stripe                        | Stripe                             |
| Adyen Web Components              | Any                                        | Adyen                         | Adyen                              |