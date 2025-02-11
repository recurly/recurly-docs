---
title: SEPA Retries
excerpt: >-
  Streamline your SEPA Direct Debit payments with Recurly's Automatic retries!
  Our new feature supports automated retries for failed SEPA payments due to
  Insufficient Funds, exclusively on Adyen and GoCardless gateways. Say goodbye
  to manual retries and involuntary churn; let Recurly do the heavy lifting and
  help keep your customers on board.
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

* Active Recurly account with SEPA Direct Debit set up.
* Integration with Adyen or GoCardless gateways.

### Limitations

* SEPA payments can only be retried twice, in compliance with SEPA regulations.
* Retry time frame is fixed to 24 hours after a failure notification; customization is not available.
* Adyen’s Auto Rescue and GoCardless Success+ services must be disabled to avoid conflict.
* SEPA retries will not occur if your Dunning settings are set to immediately expire subscriptions upon failed payments.

# Definition

SEPA retries by Recurly enable automatic re-attempts of SEPA Direct Debit payments that fail due to insufficient funds. This feature is compatible with Adyen and GoCardless gateways, adhering to SEPA regulations that limit retries to twice for late failures. With this functionality, Recurly aims to minimize involuntary customer churn and streamline payment processes.

If you’d like to learn more about SEPA Direct Debit payments, find it in our new and improved Recurly docs [here](https://docs.recurly.com/docs/sepa-direct-debit).

# Key benefits

* **Reduced manual effort**: Merchants no longer need to manually retry failed SEPA payments, saving time and operational costs.
* **Minimized involuntary churn**: By automatically retrying failed payments, merchants can retain more customers who might otherwise be lost due to payment issues.
* **Compliance with SEPA regulations**: Recurly ensures that retry attempts are within the bounds of SEPA rules, offering peace of mind to merchants.

# Key details

## Simplifying SEPA Direct Debit payments

Recurly introduces a feature enabling automated retries for SEPA Direct Debit payments. This functionality applies exclusively to transactions processed through Adyen and GoCardless gateways, aligning with SEPA regulations that allow up to two retries for transactions declined due to insufficient funds.

## Enhanced customer retention

The new SEPA retries capability aims to reduce involuntary churn by automatically attempting to recover failed payments due to insufficient funds. This removes the burden from merchants of having to manually retry payments or lose customers over payment issues.

## Integration with existing systems

The implementation of SEPA retries seamlessly integrates with Recurly's existing mandate management and user interface components for GoCardless. It also maintains the standard invoice status behavior, where invoices are marked as Processing or Paid depending on the payment's progress, and Past Due if a payment fails due to insufficient funds.

## Automated and manual retry mechanisms

Upon a failed SEPA payment notification, Recurly automatically schedules a retry 24 hours after the failure. This process considers specific failure codes (AM04 and MS03) related to insufficient funds. Merchants can also manually attempt to collect payments, providing flexibility in managing failed transactions.

## Billing information updates

Updating billing information with a new SEPA IBAN (International Bank Account Number) resets the retry counter and process. If a customer opts for a different payment method after a failed SEPA payment, scheduled retries are canceled, and the new payment method is used for future transactions.

# Implementation Guide

## Setting up SEPA Retries

### Enabling the service

To activate SEPA retries, merchants need to navigate to their Payment Settings within the Recurly platform. Here, the SEPA Retries feature can be enabled with a simple toggle. By default, this feature is turned off to prevent conflicts with any existing retry mechanisms merchants might already have in place.

<Image align="center" className="border" border={true} src="https://files.readme.io/5cb91ed-image.png" />

## Understanding invoice details with SEPA Retries

### Invoices in Recurly Admin + User Interface details

With SEPA retries activated, invoices will present additional information to help manage and understand the retry process:

* **Next attempt:** This shows when the next retry attempt for a payment will occur, provided there are retries left. It's designed to give both merchants and customers visibility into the payment schedule.

* **Remaining attempts:** Displays the count of remaining retries out of the total allowed. This number decreases with each attempt, from 2 down to 0, indicating the number of retries left before the system stops trying.

Before a payment fails due to insufficient funds, these specific details (next scheduled attempt and attempt collection option) won't be visible. However, the remaining attempts will still be shown. 

<Image align="center" className="border" width="80% " border={true} src="https://files.readme.io/f4bccb6-image.png" />

After a failure, the next attempt's timing will be visible, scheduled 24 hours post-failure, to potentially allow customers to address their insufficient funds issue. The "Attempt Collection" option also becomes available post-failure, allowing for manual initiation of a retry.

### Manual retry

Using the 'Attempt Collection' function manually will cancel any queued collection if there's already a scheduled attempt. If it's the last attempt (out of the two retries allowed), no further automated retries will be scheduled, marking the end of the retry process for that invoice.

<Image align="center" className="border" width="80% " border={true} src="https://files.readme.io/ef6ee5a-image.png" />

### Retry completion

After exhausting the retry attempts (the initial attempt plus two retries), the invoice will indicate "Retry schedule completed," signaling that no further attempts will be made against that IBAN for the payment.

<Image align="center" className="border" width="80% " border={true} src="https://files.readme.io/f98f733-image.png" />

## Behavior when SEPA Retries are disabled

<Image align="center" className="border" width="80% " border={true} src="https://files.readme.io/83ffed4-Collection_Disabled.png" />

If the SEPA retries feature is turned off:

* **Remaining attempts:** Will not be displayed in the Collection Info section. Merchants can still manually Attempt Collection, but should not exceed the mandated 2 retries.

* **Next attempt:** Will read 'Retry schedule completed', indicating that despite the default setting allowing retries, Recurly will not automatically attempt SEPA transaction retries with this feature disabled. This setup preserves the original behavior, ensuring no automatic retries are made without explicit merchant activation of the feature.

# FAQs

### Will I get webhooks for failed SEPA payments?

Yes! Integrators using Recurly webhook events will receive failed transaction updates for SEPA payments in the same way they receive event notifications for other payment methods. See [Recurly Webhook documentation on Failed Payments](https://www.google.com/url?q=https://recurly.com/developers/reference/webhooks/%23failed-payment\&sa=D\&source=docs\&ust=1711474330170410\&usg=AOvVaw3Qz4QqiEii9x0v-MJt1Qgd) for more information.

### Will automatic retries start again if my customer updates to a new form of payment?

Yes, if the form of payment supports retries. If they update their billing information to a different SEPA IBAN, or a Credit Card, the retry process will resume.

### Will automatic retries work on my old failed invoices?

In certain cases. Automatic SEPA retries will only take effect on invoices that do not yet have a late failure due to insufficient funds. If they are already in a failed or past due state when the feature is enabled, retries will not automatically be attempted. However, if the invoice is updated to a Paid state due to billing information update or a manual attempt and then returns as Insufficient funds, then automatic retries will attempt if there are attempts left on the invoice.

### Do I need AutoRescue or Success+ to use this feature?

No. Recurly’s Automatic Retry for SEPA payments is independent of gateway features, and if enabled, will disable retry attempts by the gateways themselves.
