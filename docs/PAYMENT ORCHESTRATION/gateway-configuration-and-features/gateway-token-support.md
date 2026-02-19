---
title: Gateways and Token support
excerpt: >-
  What network tokens, gateway tokens, and one‑time tokens are; how Recurly uses
  them; where payment data is stored; and feature considerations.
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

### Required plan

This feature or setting is available to all customers on any Recurly subscription plan.

### Prerequisites

To use gateway tokens from a supported provider—or to import existing tokens—confirm that Recurly supports the logic required to handle that token type. For cards and certain Direct Debit methods, Recurly stores payment details securely (encrypted) rather than tokenizing the method itself. This design lets you [configure multiple gateways](https://docs.recurly.com/docs/gateway-configuration#/) for a scalable and flexible payments setup.

### Limitations

<Callout icon="📘" theme="info">
  **Imported Token Behavior**

  If you have a specific payment or functionality requirement and intend to bypass Recurly.js or otherwise not provide raw payment details by sending in gateway tokens, please reach out to support or your customer success manager to discuss your options.
</Callout>

* If only a **gateway token** is present, **gateway failover** to other providers is not possible.
* **Imported tokens** typically do **not** display full payment‑method details and are treated as generic tokens. Imported tokens are defined as tokens imported via our Professional Services team, or if you are providing gateway tokens via API and are not. utilizing our built in Recurly.js or API features. This may preclude generic and imported tokens from certain behaviors that non-imported tokens enjoy.
* If _only_ a **gateway token** is present for cards, typical with imports, **Account Updater** facilitated by Recurly cannot used. You will want to speak to your gateway provider about Account Updater availability.

## Definitions

A **gateway token** is a value that _references_ a payment instrument (card, bank account, wallet handle, etc.) stored with a gateway partner. Gateway tokens are **not** transferable between gateways. For example, an Adyen token cannot be used to process a transaction on Stripe.

Recurly also works with other token types in order to support complex payments scenarios:

* **Network tokens**: Card tokens issued by a card network (e.g., Visa) that can be used across multiple gateways. They are not bound to a single gateway.
* **Gateway tokens**: Tokens issued by a specific gateway. They can represent many payment instruments (cards, bank details, wallets) but are usable only with the issuing provider. **Example:** Adyen gateway tokens can only be used via Adyen—not Stripe or Braintree.
* **One‑time tokens**: Ephemeral tokens used once, typically to move sensitive data from your site to Recurly via API during checkout flows. They cannot be stored for renewals. **Examples:** Recurly.js tokens, Stripe confirmation tokens (Payment Elements), Braintree nonces, Adyen State Data (from Web Components), etc.

## Key benefits

**Network tokens**

* Enable failover across gateways when you use more than one provider.
* Allow failover and migrating existing subscriptions to a different gateway that supports network tokens.

**Gateway tokens**

* Keep the actual payment instrument under your gateway’s control; if you use the gateway’s Account Updater, details remain current.
* Trade‑off: portability is very limited. Some Recurly features that require the full instrument may be unavailable. See **Limitations** above.
* Certain payment methods must be tokenized, thus enabling greater payment method acceptance.
* Certain gateways tie behind-the-scenes behavior to the use of gateway tokens, encouraging usage.

**One‑time tokens**

* Reduce PCI scope by ensuring sensitive data never touches your servers.
* **Caveat:** these tokens are short‑lived and cannot be reused. Pass them to Recurly promptly to avoid token expirations and payment failures.

## Gateway Token Interoperability

* Gateway tokens are only useful on the gateway they originate from, for example: Stripe tokens can only be used on Stripe gateways, and will not function on Adyen. Even platforms that share ownership, such as Braintree and PayPal are not always compatible. Prior to using a token with a given gateway, reach out to Recurly Support for assistance.
* Additionally, gateway tokens are typically limited to the specific gateway account they were created with, and generally cannot be used on other gateway accounts, even in the same family unless the gateway has a 'sharing' feature, such as Braintree. For example: The same Adyen token cannot be used on a different Adyen gateway account despite being from the same provider. **When using gateway tokens across different `gateway_code` values on Recurly, please ensure your tokens can be used on that gateway account.**
* If you have multiples of the same gateway onboarded, as long as your gateway tokens can be referenced by that gateway you can use a gateway token across "gateway_code" instances. For example, if you have the same Stripe Gateway account added to your Recurly site **twice**, you can use Stripe tokens across both instances with Recurly. However, if you have two **different** Stripe accounts boarded, their gateway tokens are not transferrable and your payments may encounter errors.
* Gateway tokens sent without a gateway_code on an existing Account or Billing ID will default to the `gateway_code` they were added or first created with. For example, if you create a Stripe token on `gateway_code` '123456', and then use the Account ID to process a follow up payment, we will use that gateway code. If you want to use the token on a different `gateway_code`, please include it in your payload.

## When does Recurly tokenize?

In some integrations Recurly will create and/or use tokens; in others, Recurly securely stores the payment instrument. Behavior varies by gateway and flow:

### Stripe

All payment methods are tokenized; Recurly also retains card data. With **Payment Elements**, Stripe retains the raw card data; Recurly does not have access to PAN.

Recurly supports Stripe **confirmation tokens (c_tokens)** and exchanges them for reusable **Payment Method IDs** (Stripe gateway tokens). Recurly receives gateway tokens from Stripe only on approved payments.

If you are importing Stripe tokens, these methods are generic and may experience a degraded performance. If you are running card renewals with Stripe tokens, you will need to ensure you are passing us the [CIT NTID using our APIs when creating future dated subscriptions](https://docs.recurly.com/recurly-subscriptions/docs/using-gateway-tokens-and-external-ntids-with-recurly-apis#/).

**Support Note**: 

* **Reusable Tokens:** We only support Stripe Customer and Payment Method reusable tokens. Example: cus_xxxxx and pm_xxxxx values. We do not support Stripe Cards (card_xxxx).
* **One Time Use Tokens**: We only support Stripe Confirmation Tokens, obtained via Elements (ctoken_xxxxx). We do not support Stripe "Tokens" (tok_xxxx) on our platform.

### Braintree

Depending on your gateway configuration, Recurly can create Braintree tokens for future use, but does not do so by default unless required by the payment method (PayPal, Venmo).

With Recurly.js or hosted pages (e.g., Checkout), Recurly creates a **nonce** (one‑time token) that can be exchanged for a reusable Braintree token for renewals where desired or required.

If you wish to automatically vault tokens in Braintree with Recurly, see [Configuration Steps for Braintree](https://docs.recurly.com/recurly-subscriptions/docs/braintree-rd#/step-2-configure-braintree-in-recurly).

Braintree does not support PayPal Billing Agreement IDs and will not process them.

If you are importing Braintree tokens, these methods are generic and may experience a degraded performance. If you are running card renewals with Braintree tokens, you will need to ensure you are passing us the [CIT NTID using our APIs when creating future dated subscriptions](https://docs.recurly.com/recurly-subscriptions/docs/using-gateway-tokens-and-external-ntids-with-recurly-apis#/).

**Note**: When passing in Braintree Tokens via API, or Importing Braintree Tokens if you are migrating from another platform, our platform will query the gateway to retrieve token meta-data to backfill payment method information and ensure our platform operates at its best performance. There is a required feature flag for this feature presently. Please reach out to Recurly Support to discuss enabling this prior to GA release.

### Adyen

With native Recurly checkout flows (API with raw data, Recurly.js, Hosted pages), only **non‑card** methods are tokenized by default. However, with **Adyen Components** + Recurly.js, **all** supported methods are tokenized. If you are looking to use an Adyen feature that requires tokenization, such as Network Tokens, using our [Third Party Checkout for Web Components](https://docs.recurly.com/recurly-subscriptions/docs/third-party-checkout-guide-adyen-components#/) support is recommended.

If you are importing Adyen tokens, these methods are generic and may experience a degraded performance. If you are running card renewals with Adyen tokens, you will need to ensure you are passing us the [CIT NTID using our APIs when creating future dated subscriptions](https://docs.recurly.com/recurly-subscriptions/docs/using-gateway-tokens-and-external-ntids-with-recurly-apis#/).

**Note**: We support Adyen ShopperReference IDs and Recurring Detail References in our platform. No other Adyen tokens are supported.

### Vantiv

Imported **card tokens** can be used, but can experience a degraded performance as they remain generic in our system; Recurly does **not** tokenize cards with Vantiv automatically. For imported tokens, Recurly does not have raw PAN, so failover/orchestration to other gateways is unavailable. In these cases, the definition and limitations for **imported tokens** applies here. If you are running renewals with Vantiv tokens, you will need to ensure you are passing us the [CIT NTID using our APIs when creating future dated subscriptions](https://docs.recurly.com/recurly-subscriptions/docs/using-gateway-tokens-and-external-ntids-with-recurly-apis#/).

### CommerceHub / Fiserv

Imported Fiserv Transarmour tokens can be used, but can also experience a degraded performance. If you are running renewals with CommerceHub tokens, you will need to ensure you are passing us the [CIT NTID using our APIs when creating future dated subscriptions](https://docs.recurly.com/recurly-subscriptions/docs/using-gateway-tokens-and-external-ntids-with-recurly-apis#/).

**Notes**: We only support TransArmor tokens in our platform. We do not create these tokens, but can be sent to us via API if you are migrating or using a POS card-present system.

### Amazon

By design, payment instruments are stored with Amazon. Recurly stores a **Billing Agreement** or **Charge Permission ID** for both renewals and one‑time payments (Amazon V1 and V2). These can be imported if you are using AmazonPay V1 or V2. Keep in mind that Charge Permission IDs are only supported on Amazon Pay V2.

### PayPal

By design, payment instruments are stored with PayPal and are not accessible by Recurly systems. Recurly stores a token or billing agreement for renewals and one‑time payments.

**PayPal Complete** is a special case: Recurly retains raw card details (PAN) **and** creates a PayPal token for renewals. Legacy PayPal and PayPal Complete gateways can use **Billing Agreement IDs**. Only PayPal Complete can use the newer PayPal "token".

## Where is the payment data stored?

Use this matrix to understand which system stores the payment instrument, based on gateway and checkout flow.

| Checkout solution / use case                      | Payment method                                  | Gateway                           | Where the payment instrument is stored |
| ------------------------------------------------- | ----------------------------------------------- | --------------------------------- | -------------------------------------- |
| Recurly.js or API                                 | Cards                                           | Any, **except** Stripe, Braintree | Recurly                                |
| Recurly.js or API                                 | Cards                                           | Stripe, Braintree                 | Recurly and Stripe or Braintree        |
| Recurly.js or API                                 | Bank accounts (ACH, SEPA, BACS, BECS)           | GoCardless                        | Recurly and GoCardless                 |
| Recurly.js                                        | APMs (wallets such as Cash App, PayPal, Amazon) | Adyen, PayPal, Braintree, Amazon  | Adyen, PayPal, Braintree, Amazon       |
| Stripe Payment / Express Elements                 | Any supported                                   | Stripe                            | Stripe                                 |
| Adyen Web Components                              | Any supported                                   | Adyen                             | Adyen                                  |
| Imported gateway tokens                           | Any supported                                   | Token‑supporting gateways         | The gateway                            |
| Imported cards or bank accounts (where supported) | Cards, bank details                             | Any                               | Recurly                                |
| Network tokens                                    | Cards                                           | Any                               | Recurly and Visa                       |

> **Note:** “APMs” refers to alternative payment methods.
