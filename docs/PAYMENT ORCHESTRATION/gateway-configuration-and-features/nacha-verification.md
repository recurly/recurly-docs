---
title: NACHA Verification
excerpt: >-
  Effortlessly comply with NACHA regulations with Recurly's pre-verification
  feature, ensuring seamless ACH transactions and reduced instances of bad
  accounts or fraudulent transactions.
deprecated: false
hidden: true
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
* Stripe gateway requires use of Financial Connections.

# Definition

Recurly’s Bank Account Verification Support feature provides merchants with the ability to verify consumer bank details (ACH) in the United States before processing transactions or setting up subscriptions, specifically when a new bank account is being provided. This capability is essential for businesses that operate in the United States and are accepting ACH transactions.

> **Note:** Not all gateways support pre-verification. For ACH gateways that are not supported, external verification should be done before sending bank details to Recurly for processing.

NACHA Verification Regulations can be found on the [NACHA.org site](https://www.nacha.org/system/files/2023-04/Account-Validation-FAQs-Oct-19-2020.pdf).

## Gateways with NACHA verification support

These gateways allow you to accept payments in any currency within Recurly:

* **[Adyen](adyen)**: You must enable **Giact** with your Adyen account and ensure you have enabled the feature within your gateway configuration on Recurly.

* **[Stripe](stripe)**: You must specifically be using **Stripe Elements**, and make use of Stripe's Financial Connections platform to pre-verify bank account details using Plaid.

## Gateways requiring pre-verification externally

* **[GoCardless](https://docs.recurly.com/docs/gocardless)**

* **[Check Commerce](https://docs.recurly.com/docs/check-commerce)**