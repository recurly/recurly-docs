---
title: ACH (US only)
excerpt: >-
  Recurly's ACH payment method, a US-exclusive feature, allows for direct and
  easy transactions right from a customer's bank account, bypassing the need for
  credit card processors and physical checks, hence, revolutionizing payment
  solutions with streamlined processes.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Overview

### Required plan

This feature **may not be included** in the Starter or Pro plans. If you are interested, please contact [Recurly Sales](https://recurly.com/demo/contact-sales/) to discuss upgrade options. **You can try this in a sandbox environment before making the upgrade**.

### Prerequisites & supported gateways

Recurly currently supports ACH transactions through [Adyen](https://docs.recurly.com/docs/adyen), [GoCardless](https://docs.recurly.com/docs/gocardless), [Stripe](https://docs.recurly.com/docs/stripe#/) (via [Third Party Checkout](https://recurly.com/developers/guides/3rd-party-checkout.html)), and [Check Commerce](https://docs.recurly.com/docs/check-commerce).

### Limitations

* The ACH feature is available exclusively for merchants based in the US, thereby limiting its global outreach.
* ACH has a varying processing time and a series of invoice states, ranging from pending to scheduled to processed, with each stage holding its implications and possible actions.
* ACH transactions cannot be voided via API. This action is only supported in the UI.

# Definition

The ACH (Automated Clearing House) payment method is designed for merchants in the US, allowing Recurly users to directly debit funds from a customer's bank account. This feature provides an alternative to traditional payment methods like physical checks and credit card processing, aiming to streamline payment transactions.

# Checkout flow

#### Payment authorization

ACH is regulated by an organization called <a href="https://www.nacha.org/" target="_blank" rel="noopener noreferrer">NACHA</a>. Customers must provide authorization to Merchants for all payments and any future recurring collections. The type of information a Merchant must collect must include:

* Date of purchase
* Amount of purchase
* Customer name
* Account number
* Routing number and bank name
* Authorization language for the payment and whether there are renewals
* Authorization language to attempt additional collections if the first transaction fails
* Language letting the customer know that if they need to cancel, they must contact the merchant by a certain number of days before the payment and how they should contact the merchant.

#### Email communication

Customers receive email notifications at various stages of the payment process, informing them about the status of the transaction and what they can expect next. Refinement in email communication assures transparency in transactions.

#### Dunning

With the ACH feature on, review your dunning length due to ACH’s extended processing times to ensure compatibility with the Automatic Collection Dunning settings.

### Recurly settings

#### Hosted pages

Enable the Bank Account option on your hosted pages settings in your Recurly site to facilitate ACH transactions through the hosted payment and invoice pages. The guidelines for the settings can be referred to in the detailed overview above.

#### Webhooks

Ensure to update the relevant webhooks to support ACH, covering aspects like invoice state and payment state notifications. Details on code samples can be found in the [Webhooks documentation](https://recurly.readme.io/v2.0/page/webhooks).

#### API and Recurly.js

Leverage the functionalities added to Recurly.js v3 and API v2 to support ACH payments. Reference the respective documentations for [API](https://dev.recurly.com/docs/lookup-an-accounts-billing-info) and [Recurly.js](https://docs.recurly.com/js/) for further details.

#### Sandbox testing

Before going live, test the ACH setup on a Recurly sandbox site using the provided test credentials to ensure that everything is functioning correctly.

#### Updating your per-check limit

Ensure to have your ACH payment threshold in sync with your gateway settings. To modify the threshold, reach out to your gateway and follow up with [Recurly Support](https://support.recurly.com/) if issues persist.