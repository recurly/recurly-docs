---
title: Direct debit retries
excerpt: >-
  Streamline your Direct Debit payments with Recurly's Automatic retries! Our
  new feature supports automated retries for failed SEPA payments due to
  Insufficient Funds, exclusively on Adyen, Stripe, and GoCardless gateways. Say
  goodbye to manual retries and involuntary churn; let Recurly do the heavy
  lifting and help keep your customers on board.
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

This feature or setting is available to all customers on any Recurly subscription plan.

### Prerequisites

* Active Recurly account with one of the following payment methods enabled: SEPA Direct Debit, BACS, BECS, ACH.
  * SEPA is supported on Adyen, Stripe, and GoCardless.
  * BACS is supported on Adyen, Stripe, and GoCardless.
  * ACH is supported on Adyen, Stripe, and GoCardless.
  * BECS is supported on Stripe and GoCardless.
* Integration with [Adyen](https://docs.recurly.com/docs/adyen#/), [Stripe](https://docs.recurly.com/docs/stripe#/) (using [Third Party Checkout: Payment Elements](https://docs.recurly.com/docs/stripe-payment-elements#/)), [GoCardless](https://docs.recurly.com/docs/gocardless#/) gateways.

### Limitations

* This feature only retries qualifying transactions (declined for Insufficient Funds) on specific gateways.
* Gateway-level Retry services must be disabled to avoid overcharging the customer. This includes Adyen’s Auto Rescue and GoCardless Success+ services.
* Supported Direct Debit payments can only be retried twice, in compliance with NACHA, SEPA, and EU/AU regulations.
* Retry time frame is fixed to 24 hours after a late failure notification from the gateway; customization is not available.
* Direct Debit retries will not occur if your Dunning settings are set to immediately expire subscriptions upon failed payments.
* Check Commerce is not supported.

# Definition

Direct Debit retries by Recurly enables automatic re-attempts of ACH, BACS, BECS, and SEPA Direct Debit payments that fail due to insufficient funds. This feature is compatible with Stripe, Adyen and GoCardless gateways, adhering to the various Bank Debit regulations that limit retries to twice after initial failure. With this functionality, Recurly aims to minimize involuntary customer churn and streamline payment processes.

If you’d like to learn more about Direct Debit payments, find it in our payment method documentation pages below:

* [SEPA](https://docs.recurly.com/docs/sepa-direct-debit#/)
* [ACH](https://docs.recurly.com/docs/ach-bank-payments#/)
* [BACS](https://docs.recurly.com/docs/bacs#/)
* [BECS](https://docs.recurly.com/docs/becs#/)

# Key benefits

* **Reduced manual effort**: Merchants no longer need to manually retry failed bank account payments, saving time and operational costs.
* **Minimized involuntary churn**: By automatically retrying failed payments, merchants can retain more customers who might otherwise be lost due to payment issues.
* **Compliance with Bank Account regulations**: Recurly ensures that retry attempts are within the bounds of NACHA, SEPA, and other bank debit rules, offering peace of mind to merchants.

# Key details

## Simplifying Direct Debit payments

Recurly introduces a feature enabling automated retries for Direct Debit payments. This functionality applies exclusively to transactions processed through Adyen, Stripe, and GoCardless gateways, aligning with SEPA, EU, AU, and NACHA regulations that allow up to two retries for transactions declined due to insufficient funds.

## Enhanced customer retention

The Direct Debit retries capability aims to reduce involuntary churn by automatically attempting to recover failed payments due to insufficient funds. This removes the burden from merchants of having to manually retry payments or lose customers over payment issues.

## Integration with existing systems

The implementation of Direct Debit retries seamlessly integrates with Recurly's existing mandate management and user interface components for supported gateways. It also maintains the standard invoice status behavior, where invoices are marked as Processing or Paid depending on the payment's progress, and Past Due if a payment fails due to insufficient funds.

## Automated and manual retry mechanisms

Upon a failed payment notification, Recurly automatically schedules a retry 24 hours after the failure. This process considers specific failure codes (SEPA: AM04 and MS03, ACH: R01, etc.) related to insufficient funds. Merchants can also manually attempt to collect payments, providing flexibility in managing failed transactions.

## Billing information updates

Updating billing information with a new bank account number resets the retry counter and process. If a customer opts for a different payment method after a failed bank payment, scheduled retries are canceled, and the new payment method is used for future transactions.

# Implementation Guide

## Setting up Direct Debit Retries

### Enabling the service

To activate Direct Debit Automatic retries, merchants need to navigate to their Payment Settings within the Recurly platform.

Here, the Direct Debit Retries feature can be enabled by checking the appropriate checkbox for the gateway and payment method combination. By default, this feature is turned off to prevent conflicts with any existing retry mechanisms merchants might already have in place.

You will only see options for the gateway if the payment method / gateway combination is available.

<Image align="center" className="border" border={true} src="https://files.readme.io/75288e00f3469a1dd81db2cd3fd7565b260bd63ef94ba9c7385b26c04e1805bf-Screenshot_2025-06-26_at_1.55.21_PM.png" />

## Understanding invoice details with Direct Debit Retries

### Invoices in Recurly Admin + User Interface details

With Direct Debit retries activated, invoices will present additional information to help manage and understand the retry process:

* **Next attempt:** This shows when the next retry attempt for a payment will occur, provided there are retries left. It's designed to give both merchants and customers visibility into the payment schedule.

* **Remaining attempts:** Displays the count of remaining retries out of the total allowed. This number decreases with each attempt, from 2 down to 0, indicating the number of retries left before the system stops trying.

Before a payment fails due to insufficient funds, these specific details (next scheduled attempt and attempt collection option) won't be visible. However, the remaining attempts will still be shown.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/f4bccb6-image.png" />

After a failure, the next attempt's timing will be visible, scheduled 24 hours post-failure, to potentially allow customers to address their insufficient funds issue. The "Attempt Collection" option also becomes available post-failure, allowing for manual initiation of a retry.

### Manual retry

Using the 'Attempt Collection' function manually will cancel any queued collection if there's already a scheduled attempt. If it's the last attempt (out of the two retries allowed), no further automated retries will be scheduled, marking the end of the retry process for that invoice.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/ef6ee5a-image.png" />

### Retry completion

After exhausting the retry attempts (the initial attempt plus two retries), the invoice will indicate "Retry schedule completed," signaling that no further attempts will be made against that bank account for the payment.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/f98f733-image.png" />

## Behavior when Direct Debit Retries are disabled

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/83ffed4-Collection_Disabled.png" />

If the Direct Debit Automatic Retries feature is turned off:

* **Remaining attempts:** Will not be displayed in the Collection Info section. Merchants can still manually Attempt Collection, but should not exceed the mandated 2 retries.

* **Next attempt:** Will read 'Retry schedule completed', indicating that despite the default setting allowing retries, Recurly will not automatically attempt payment transaction retries with this feature disabled. This setup preserves the original behavior, ensuring no automatic retries are made without explicit merchant activation of the feature.

# FAQs

### Will I get webhooks for failed bank payments?

Yes! Integrators using Recurly webhook events will receive failed transaction updates for bank account payments in the same way they receive event notifications for other payment methods. See [Recurly Webhook documentation on Failed Payments](https://www.google.com/url?q=https://recurly.com/developers/reference/webhooks/%23failed-payment\&sa=D\&source=docs\&ust=1711474330170410\&usg=AOvVaw3Qz4QqiEii9x0v-MJt1Qgd) for more information.

### Will automatic retries start again if my customer updates to a new form of payment?

Yes, if the form of payment supports retries. If they update their billing information to a different bank account, payment method, or a Credit Card, the retry process will resume where supported.

### Will automatic retries work on my old failed invoices?

In certain cases. Automatic Direct Debit retries will only take effect on invoices that do not yet have a late failure due to insufficient funds. If they are already in a failed or past due state when the feature is enabled, retries will not automatically be attempted. However, if the invoice is updated to a Paid state due to billing information update or a manual attempt and then returns as Insufficient funds, then automatic retries will attempt if there are attempts left on the invoice.

### Do I need AutoRescue or Success+ to use this feature?

No. Recurly’s Automatic Retry for Direct Debit payments is independent of gateway features, and if enabled, will disable retry attempts by the gateways themselves.