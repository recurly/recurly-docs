---
title: NACHA verification
excerpt: >-
  Effortlessly comply with NACHA regulations with Recurly's pre-verification
  feature, ensuring seamless ACH transactions and reduced instances of bad
  accounts or fraudulent transactions.
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

### Prerequisites

* Access to one or more supported payment gateways or;
* A direct integration with an ACH verification provider, such as Plaid or Giact.

### Limitations

* Only new bank accounts will be verified. Bank accounts on file are not subject to preverification rules.
* Adyen gateway requires use of Giact.
* Stripe gateway requires use of Financial Connections and cannot support externally verified bank accounts.

# Definition

Recurly’s Bank Account Verification Support feature provides merchants with the ability to verify consumer bank details (ACH) in the United States before processing transactions or setting up subscriptions, specifically when a new bank account is being provided. This capability is essential for businesses that operate in the United States and are accepting ACH transactions.

> **Note:** Not all gateways support pre-verification. For ACH gateways that are not supported, external verification should be done before sending bank details to Recurly for processing.

NACHA Verification Regulations can be found on the [NACHA.org site](https://www.nacha.org/system/files/2023-04/Account-Validation-FAQs-Oct-19-2020.pdf) and by reading their [Account Validation best practices guide](https://www.nacha.org/content/account-validation-resource-center).

## Gateways with NACHA verification support

These gateways allow you to accept payments in any currency within Recurly:

* **[Adyen](adyen)**: You must enable **Giact** with your Adyen account and ensure you have enabled the feature within your gateway configuration on Recurly.

<Image align="center" border={false} src="https://files.readme.io/6fb1bfb995b6d992d1869d03bc8d0de195bf3b3e64418cc208a097abb5b0fafb-Screenshot_2025-07-29_at_4.11.19_PM.png" />

* **[Stripe](stripe)**: You must specifically be using **Stripe Elements**, and make use of Stripe's Financial Connections platform to pre-verify bank account details using Plaid.
* **[WorldPay](https://docs.recurly.com/recurly-subscriptions/docs/worldpaydlocal-latam-support#/)**: You can use Recurly.js, our APIs, or other ACH supported mechanism. WorldPay's integration automatically supports pre-verification when a bank account is provided to Recurly. Bank accounts that are already stored will not be subject to verification again on the same Recurly site.

## Gateways requiring pre-verification externally

* **[GoCardless](https://docs.recurly.com/docs/gocardless)**

* **[Check Commerce](https://docs.recurly.com/docs/check-commerce)**

### Suggested flow for external verifications

You may use an external provider for any of our ACH supported gateways (excluding Stripe) to verify bank accounts prior to adding billing information to the Recurly platform. General best practices including verifying any _new_ bank account information provided to you by a consumer, so that you can verify it is usable for a WEB (online) transaction.

The direct language from the mandate, effective March 2021, is as follows:

* Validate first-use consumer account information for consumer debit payments authorized or initiated over an online channel (often called WEB Debits).

You may require users to authenticate via Plaid, or even via micro-transactions and verify the debits/credits, prior to adding their billing info to Recurly. If the external integration verifies that a consumer's bank account is valid for online processing, and can be debited, you may follow your existing flow with Recurly today.
