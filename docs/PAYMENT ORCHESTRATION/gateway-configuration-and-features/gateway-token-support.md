---
title: Gateways and token support
excerpt: >-
  Understand how Recurly supports gateway tokens, network tokens, and where
  payment data is stored.
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

Recurly supports multiple token types to help you accept payments securely, migrate subscriptions, and scale across gateways. This page explains what each token type means, how token behaviour affects features like failover and Account Updater, and when Recurly tokenises versus securely stores payment instruments.

### Required plan

This feature or setting is available to all customers on any Recurly subscription plan.

### Prerequisites

To use gateway tokens from a supported provider — or to import existing tokens — confirm that Recurly supports the logic required to handle that token type. For cards and certain direct debit methods, Recurly stores payment details securely (encrypted) rather than tokenising the method itself. This design also lets you [configure multiple gateways](https://docs.recurly.com/docs/gateway-configuration#/)  for a scalable and flexible payments setup.

### Limitations

> 📘 **Imported token behaviour**
>
> If you have a specific payment or functionality requirement and intend to bypass Recurly.js or otherwise not provide raw payment details by sending gateway tokens, **contact Recurly Support** or your **Customer Success Manager** to discuss your options.

* If only a **gateway token** is present, **gateway failover** to other providers isn’t possible
* **Imported tokens** typically don’t display full payment method details and are treated as generic tokens
  * Imported tokens include tokens brought in through Professional Services, or tokens you send through the API without using Recurly.js or Recurly’s standard API flows
  * Generic and imported tokens may not support some behaviours available to non-imported payment methods
* If only a **gateway token** is present for cards (common with imports), Recurly **Account Updater** can’t be used
  * Check with your gateway provider about Account Updater availability

## Definitions

A **gateway token** is a value that references a payment instrument stored with a gateway partner. Gateway tokens are not transferable between gateways. For example, an Adyen token can’t be used to process a transaction on Stripe.

Recurly supports other token types to cover more payment scenarios:

* **Network tokens**: Card tokens issued by a card network (for example, Visa) that can be used across multiple gateways and aren’t bound to one gateway
* **Gateway tokens**: Tokens issued by a specific gateway that represent a payment instrument (card, bank account, wallet handle, and more) and can be used only with the issuing provider
  * **Example:** Adyen gateway tokens can be used only through Adyen — not Stripe or Braintree
* **One-time tokens**: Short-lived tokens used once, typically to move sensitive data from your website to Recurly during checkout flows
  * These tokens can’t be stored for renewals
  * **Examples:** Recurly.js tokens, Stripe confirmation tokens (Payment Elements), Braintree nonces, Adyen State Data (Web Components)

## Key benefits

### Network tokens

* Enable failover across gateways when you use more than one provider
* Support migrating existing subscriptions to a different gateway that supports network tokens

### Gateway tokens

* Keep the payment instrument under your gateway’s control, and let the gateway’s Account Updater keep details current (when available)
* **Trade-off:** Portability is limited, and some Recurly features that require full instrument details may be unavailable (see **Limitations**)
* Support payment methods that must be tokenised for acceptance
* Enable certain gateway-specific behaviours that depend on tokenised flows

### One-time tokens

* Reduce PCI scope by ensuring sensitive data doesn’t touch your servers
* **Caveat:** One-time tokens expire quickly and can’t be reused, so pass them to Recurly promptly

## Gateway token interoperability

* Gateway tokens can be used only on the gateway they originate from
  * **Example:** Stripe tokens work only on Stripe, and won’t work on Adyen
  * Even related platforms (for example, Braintree and PayPal) aren’t always compatible
  * If you’re unsure, contact Recurly Support before you attempt to use a token on a gateway
* Gateway tokens are usually limited to the specific gateway account that created them
  * **Example:** An Adyen token created on one Adyen account typically can’t be used on a different Adyen account, even if it’s the same provider
  * When using gateway tokens across different `gateway_code` values in Recurly, confirm your tokens can be used on that gateway account
* If you have multiple instances of the same gateway in Recurly, and they map to the same gateway account, tokens can typically be used across those instances
  * **Example:** If you add the same Stripe account twice in Recurly, Stripe tokens can be used across both gateway instances
  * If you have two different Stripe accounts, their tokens aren’t transferable and payments may fail
* If you send a gateway token without a `gateway_code` on an existing Account or Billing Info ID, Recurly uses the `gateway_code` the token was first created or added with
  * If you need to use a different `gateway_code`, include it in your API payload

# When does Recurly tokenise?

Recurly may tokenise payment methods in some flows, and securely store payment instruments in others. The behaviour depends on the gateway and the checkout flow.

## Stripe

All payment methods are tokenised. Recurly also retains card data. With Stripe Payment Elements, Stripe retains the raw card data and Recurly doesn’t have access to the primary account number (PAN).

Recurly supports Stripe confirmation tokens (`ctoken_xxxxx`) and exchanges them for reusable Payment Method IDs (Stripe gateway tokens). Recurly receives gateway tokens from Stripe only on approved payments.

If you import Stripe tokens, the payment methods are generic and may have degraded performance. For card renewals with imported Stripe tokens, make sure you pass the cardholder-initiated transaction (CIT) network transaction ID (NTID) when creating future-dated subscriptions. See [Using gateway tokens and external NTIDs with Recurly APIs](https://docs.recurly.com/recurly-subscriptions/docs/using-gateway-tokens-and-external-ntids-with-recurly-apis#/) .

> **Support note**
>
> **Reusable tokens:** Stripe Customer and Payment Method tokens are supported (for example, `cus_xxxxx` and `pm_xxxxx`). Stripe card tokens (`card_xxxx`) aren’t supported.
>
> **One-time tokens:** Stripe confirmation tokens from Elements are supported (`ctoken_xxxxx`). Stripe Tokens (`tok_xxxx`) aren’t supported
>
> **Stripe Token types**: Stripe has other token types such as Token (`tok_xxxxx`) and Card (`card_xxxxx`), which we do not support.

## Braintree

Depending on your gateway configuration, Recurly can create Braintree tokens for future use, but doesn’t do so by default unless the payment method requires it (for example, PayPal or Venmo).

With Recurly.js or hosted pages (for example, Checkout), Recurly creates a Braintree nonce (a one-time token). That nonce can be exchanged for a reusable Braintree token for renewals when required.

If you want to vault tokens in Braintree automatically, see [Configuration steps for Braintree](https://docs.recurly.com/recurly-subscriptions/docs/braintree-rd#/step-2-configure-braintree-in-recurly) .

Braintree doesn’t support PayPal Billing Agreement IDs and won’t process them. If you are importing tokens or migrating from a PayPal direct integration, you must first vault these Billing Agreements with Braintree. You can speak to our Professional Services team about this process.

If you import Braintree tokens, the payment methods are generic and may have degraded performance. For card renewals with imported Braintree tokens, make sure you pass the CIT NTID when creating future-dated subscriptions. See [Using gateway tokens and external NTIDs with Recurly APIs](https://docs.recurly.com/recurly-subscriptions/docs/using-gateway-tokens-and-external-ntids-with-recurly-apis#/) .

Recurly supports Braintree's "legacy" tokens, and do not consume or create Global IDs.

> **Note:** When you send Braintree tokens through the API or import them during a migration, Recurly can query Braintree to retrieve token metadata and backfill payment method details. This feature currently requires a feature flag. Contact Recurly Support to discuss enabling it.

## Adyen

With native Recurly checkout flows (API with raw data, Recurly.js, hosted pages), only non-card methods are tokenised by default. With Adyen Web Components through Recurly.js, all supported methods are tokenised.

If you need an Adyen feature that requires tokenisation (for example, network tokens), use [Third-party checkout for Adyen Web Components](https://docs.recurly.com/recurly-subscriptions/docs/third-party-checkout-guide-adyen-components#/) .

If you import Adyen tokens, payment methods are generic and may have degraded performance. For card renewals with imported Adyen tokens, make sure you pass the CIT NTID when creating future-dated subscriptions. See [Using gateway tokens and external NTIDs with Recurly APIs](https://docs.recurly.com/recurly-subscriptions/docs/using-gateway-tokens-and-external-ntids-with-recurly-apis#/) .

> **Note:** Recurly supports Adyen ShopperReference IDs and Recurring Detail References. No other Adyen tokens are supported.

## CommerceHub / Fiserv

Imported Fiserv TransArmor tokens can be used, but may have degraded performance. If you run renewals with CommerceHub tokens, make sure you pass the CIT NTID when creating future-dated subscriptions. See [Using gateway tokens and external NTIDs with Recurly APIs](https://docs.recurly.com/recurly-subscriptions/docs/using-gateway-tokens-and-external-ntids-with-recurly-apis#/) .

> **Note:** Only TransArmor tokens are supported. Recurly doesn’t create these tokens, but you can send them through the API for migrations or point-of-sale (card-present) use cases.

## FreedomPay

Imported FreedomPay tokens can be imported or sent in via API. If you run renewals with FreedomPay tokens, make sure you pass the CIT NTID when creating future-dated subscriptions. See [Using gateway tokens and external NTIDs with Recurly APIs](https://docs.recurly.com/recurly-subscriptions/docs/using-gateway-tokens-and-external-ntids-with-recurly-apis#/) .

> **Note:** Only certain type of FreedomPay tokens are supported. Recurly doesn’t create these tokens, but you can send them through the API for migrations or point-of-sale (card-present) use cases.

## Amazon Pay

Payment instruments are stored with Amazon Pay. Recurly stores a Billing Agreement or Charge Permission ID for renewals and one-time payments (Amazon Pay V1 and V2). These can be imported if you use Amazon Pay V1 or V2. Charge Permission IDs are supported only on Amazon Pay V2.

## PayPal

Payment instruments are stored with PayPal and aren’t accessible to Recurly. Recurly stores a token or billing agreement for renewals and one-time payments.

PayPal Complete is a special case: Recurly retains raw card details (PAN) and creates a PayPal token for renewals. Legacy PayPal and PayPal Complete gateways can use Billing Agreement IDs. Only PayPal Complete supports the newer PayPal token.

# Where is the payment data stored?

Use this matrix to understand which system stores the payment instrument based on gateway and checkout flow.

| Checkout solution or use case                     | Payment method                                                             | Gateway                              | Where the payment instrument is stored |
| ------------------------------------------------- | -------------------------------------------------------------------------- | ------------------------------------ | -------------------------------------- |
| Recurly.js or API                                 | Cards                                                                      | Any, except Stripe and Braintree     | Recurly                                |
| Recurly.js or API                                 | Cards                                                                      | Stripe or Braintree                  | Recurly and Stripe or Braintree        |
| Recurly.js or API                                 | Bank accounts (ACH, SEPA, Bacs, BECS)                                      | GoCardless                           | Recurly and GoCardless                 |
| Recurly.js                                        | Alternative payment methods (wallets such as Cash App, PayPal, Amazon Pay) | Adyen, PayPal, Braintree, Amazon Pay | Adyen, PayPal, Braintree, Amazon Pay   |
| Stripe Payment Elements or Express Elements       | Any supported                                                              | Stripe                               | Stripe                                 |
| Adyen Web Components                              | Any supported                                                              | Adyen                                | Adyen                                  |
| Imported gateway tokens                           | Any supported                                                              | Token-supporting gateways            | The gateway                            |
| Imported cards or bank accounts (where supported) | Cards, bank details                                                        | Any                                  | Recurly                                |
| Network tokens                                    | Cards                                                                      | Any                                  | Recurly and Visa                       |

> **Note:** Alternative payment methods (APMs) refers to non-card payment methods such as wallets and direct debit.
