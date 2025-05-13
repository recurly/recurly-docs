---
title: Commerce Hub by Fiserv
excerpt: >-
  Seamless and secure payment processing with Commerce Hub integration for
  Recurly.
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

### Required plan

This feature or setting is available to all customers on any Recurly subscription plan.

# Definition

Commerce Hub is a full-service payment management platform, developed by Fiserv / First Data. When configured with Recurly, it allows you to securely manage your transactions. You will need your Commerce Hub credentials to enable this integration.

> **Note**: Visit our guide on testing your gateway configurations in Recurly to ensure your payment processes are set up correctly.

# Key details

| Feature                         | Description                                                                                                                                                                                         |
| ------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Services that work with Recurly | Payment Processing, Recurring Billing                                                                                                                                                               |
| Supported Operations            | Verify, Purchase, Authorize and Capture, Void, Refund (Full and Partial)                                                                                                                            |
| Supported Payment Types         | Credit/Debit Card, Apple Pay, Google Pay, Network Tokens                                                                                                                                            |
| Supported Card Brands           | Visa, MasterCard, American Express, Discover, Diners Club, JCB, Union Pay                                                                                                                           |
| Gateway Specific 3DS2 Supported | No                                                                                                                                                                                                  |
| Card On File Supported          | Yes                                                                                                                                                                                                 |
| Regions                         | Global                                                                                                                                                                                              |
| Currencies                      | All ISO Standard                                                                                                                                                                                    |
| Transaction Categories          | Ecommerce, Recurring, MOTO                                                                                                                                                                          |
| Additional Feature Support      | Billing and Shipping Information, Level 2 Data, Visa Trial Descriptors,  AVS / CVV Checks, Fiserv Transarmor Gateway Tokens, Omnichannel Point of Sale Subscriptions, VAT and Line Item Passthrough |

## Migrating from First Data and Payeezy Gateways

> 🚧 Important
>
> First Data and Payeezy gateways will be deprecated at the end of Q3 2025. This date is mandated by Fiserv directly. Ensure you are onboarding Commerce Hub and testing your integration in a timely manner to avoid payment interruptions.

1. Onboard Commerce Hub in your Recurly Site.
2. If you have an integration to Recurly that uses the `gateway_code` value, ensure you modify it in your code to avoid sending transactions to the wrong gateway.
3. You may migrate away from Payeezy and First Data gradually if you desire. Simply change the `gateway_code` for new transactions and existing subscriptions over a period of time at your discretion.

## Parity with First Data and Payeezy

In building Commerce Hub, Recurly has taken great care in reaching parity with previous functionality, and certified our platform with Fiserv to ensure a smooth transition. Rest assured, transactions that functioned on First Data and Payeezy will seamlessly transition to Commerce Hub.

## Existing subscriptions

Since First Data and Payeezy merchants have already been migrated to Commerce Hub behind the scenes, all current subscription transactions have been processing on Commerce Hub behind the scenes due to an emulation rule at Fiserv. Existing subscriptions should continue to process as usual by changing the gateway code the subscription is pointed at within Recurly.

For new subscribers, ensure you change the `gateway_code`value you are sending API transactions to in order to avoid interruptions or errors once you disable your Fiserv or Payeezy gateway instances in your Recurly site.

# Address Verification System (AVS) settings

Unlike previous First Data and Payeezy gateway implementations, Merchants using Commerce Hub have the option to tailor their Address Verification System (AVS) and CVV (Card Verification Value) checks via the Payment Settings page. Learn more about our gateway agnostic AVS / CVV rules here.