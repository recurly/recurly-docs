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

Available on all plans.

### Prerequisites

To use gateway tokens from a supported provider—or to import existing tokens—confirm that Recurly supports the logic required to handle that token type. For cards and certain Direct Debit methods, Recurly stores payment details securely (encrypted) rather than tokenizing the method itself. This design lets you [configure multiple gateways](https://docs.recurly.com/docs/gateway-configuration#/) for a scalable and flexible payments setup.

### Limitations

* If only a **gateway token** is present, **gateway failover** to other providers is not possible.
* **Imported tokens** typically do **not** display full payment‑method details.
* If only a **gateway token** is present for cards, **Account Updater** cannot run.

## Definitions

A **gateway token** is a value that references a payment instrument (card, bank account, wallet handle, etc.) stored with a gateway partner. Gateway tokens are **not** transferable between gateways. For example, an Adyen token cannot be used to process on Stripe.

Recurly also works with other token types in order to support complex payments scenarios:

* **Network tokens**: Card tokens issued by a card network (e.g., Visa) that can be used across multiple gateways. They are not bound to a single gateway.
* **Gateway tokens**: Tokens issued by a specific gateway. They can represent many payment instruments (cards, bank details, wallets) but are usable only with the issuing provider. **Example:** Adyen gateway tokens can only be used via Adyen—not Stripe or Braintree.
* **One‑time tokens**: Ephemeral tokens used once, typically to move sensitive data from your site to Recurly via API during checkout flows. They cannot be stored for renewals. **Examples:** Recurly.js tokens, Stripe c_tokens (Payment Elements), Braintree nonces.

## Key benefits

**Network tokens**

* Enable failover across gateways when you use more than one provider.
* Allow moving existing subscriptions to a different gateway that supports network tokens.

**Gateway tokens**

* Keep the payment instrument under your gateway’s control; if you use the gateway’s Account Updater, details remain current.
* Trade‑off: portability is limited. Some Recurly features that require the full instrument may be unavailable. See **Limitations** above.

**One‑time tokens**

* Reduce PCI scope by ensuring sensitive data never touches your servers.
* **Caveat:** these tokens are short‑lived and cannot be reused. Pass them to Recurly promptly to avoid expirations or failures.

## When does Recurly tokenize?

In some integrations Recurly will create and/or use tokens; in others, Recurly securely stores the payment instrument. Behavior varies by gateway and flow:

### Stripe

All payment methods are tokenized; Recurly also retains card data. With **Payment Elements**, Stripe retains the raw card data; Recurly does not have access to PAN.

Recurly supports Stripe **confirmation tokens (c_tokens)** and exchanges them for reusable **Payment Method IDs** (Stripe gateway tokens). Recurly receives gateway tokens from Stripe only on approved payments.

### Braintree

Depending on your gateway configuration, Recurly can create Braintree tokens for future use.

With Recurly.js or hosted pages (e.g., Checkout), Recurly creates a **nonce** (one‑time token) that can be exchanged for a reusable Braintree token for renewals.

### Adyen

With native Recurly checkout flows, only **non‑card** methods are tokenized.

With **Adyen Components** + Recurly.js, **all** supported methods are tokenized.

### Vantiv

Imported **card tokens** are supported; Recurly does **not** tokenize cards with Vantiv. For imported tokens, Recurly does not have raw PAN, so failover/orchestration to other gateways is unavailable.

### Amazon

By design, instruments are stored with Amazon. Recurly stores a **Billing Agreement** or **Charge Permission ID** for both renewals and one‑time payments (Amazon V1 and V2).

### PayPal

By design, instruments are stored with PayPal. Recurly stores a token or billing agreement for renewals and one‑time payments.

**PayPal Complete** is a special case: Recurly retains raw card details (PAN) **and** creates a PayPal token for renewals. Legacy PayPal gateways use **Billing Agreement IDs**.

## Supported gateway tokens

* **Stripe**: Creation and use of **Payment Method IDs**. (Stripe single‑use “Tokens” are not supported.)
* **Adyen**: Creation and use where required (varies by method).
* **Braintree**: Creation and use based on merchant settings.
* **PayPal Complete**: Creation and use of PayPal tokens.
* **Legacy PayPal gateways**: Creation and use of Billing Agreement IDs.
* **Amazon**: Creation and use of Billing Agreement / Charge Permission IDs.
* **Vantiv**: Use after import (no token creation by Recurly).
* **Payeezy**: Use after import of **TransArmor** tokens (no token creation by Recurly).

## Where is the payment data stored?

Use this matrix to understand which system stores the payment instrument, based on gateway and checkout flow.

| Checkout solution / use case                      | Payment method                                  | Gateway                          | Where the payment instrument is stored |
| ------------------------------------------------- | ----------------------------------------------- | -------------------------------- | -------------------------------------- |
| Recurly.js or API                                 | Cards                                           | Any, except Stripe, Braintree    | Recurly                                |
| Recurly.js or API                                 | Cards                                           | Stripe, Braintree                | Recurly and Stripe or Braintree        |
| Recurly.js or API                                 | Bank accounts (ACH, SEPA, BACS, BECS)           | GoCardless                       | Recurly and GoCardless                 |
| Recurly.js                                        | APMs (wallets such as Cash App, PayPal, Amazon) | Adyen, PayPal, Braintree, Amazon | Adyen, PayPal, Braintree, Amazon       |
| Stripe Payment / Express Elements                 | Any supported                                   | Stripe                           | Stripe                                 |
| Adyen Web Components                              | Any supported                                   | Adyen                            | Adyen                                  |
| Imported gateway tokens                           | Any supported                                   | Token‑supporting gateways        | The gateway                            |
| Imported cards or bank accounts (where supported) | Cards, bank details                             | Any                              | Recurly                                |
| Network tokens                                    | Cards                                           | Any                              | Recurly and Visa                       |

> **Note:** “APMs” refers to alternative payment methods.
