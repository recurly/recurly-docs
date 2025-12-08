---
title: Static retries
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

### Required plan

This feature or setting is available to all customers on any Recurly subscription plan.

### Prerequisites

* An active Recurly account in production mode.
* Recurring credit card payment setup.
* Access to the Recurly dashboard and configurations.

### Limitations

* Not applicable for hard declines.
* Retries will cease after 7 transaction declines, 20 total transaction attempts, or 60 days since the invoice creation.

# Definition

Recurly's Static Retries does not use machine learning, but rather a specific set of criteria given signals from our gateway partners.

# Key benefits

* **Reduced subscriber churn**: Minimizes disruptions and involuntary subscriber churn.
* **Compliant logic**: Tailors retry schedules to maximize the opportunity of success.
* **Comprehensive coverage**: Works alongside other revenue recovery strategies such as Dunning.

# Recurly's static retry logic

Recurly's static retry logic uses gateway signals and regulatory compliance signals from the transaction to increase the chances of successful payments. This helps keep your customers' subscriptions active and reduces the chance of losing them due to payment issues. Our status retry logic does not use machine learning while also increasing the likelihood of successful transactions. If you are interested in further optimizations, see our documentation on [Intelligent Retries](https://docs.recurly.com/recurly-subscriptions/docs/retry-logic#/).

# General retry guidelines

## Soft declines

Soft declines, which occur for reasons like insufficient funds or temporary holds, are not final. Recurly's machine learning technology plays a crucial role here, as it determines the most effective timing for retries using the same payment method. By analyzing patterns in transaction data, the system adapts the retry schedule to enhance the likelihood of a successful charge, tailoring the process to suit various scenarios and maximize efficiency for your business.

## Hard declines

While hard declines typically aren't retried, there are exceptions:

* **Exception A:** Immediate retry if Account Updater or the customer updates billing information.
* **Exception B:** Change from hard to soft decline during dunning after billing information update.
* **Exception C:** Forced collection outside the typical recurring schedule.

## Handling gateway payment declines

Different gateway errors have specific retry schedules:

* **Try Again/Gateway Error:** Every 2 days.
* **Issuer or Processor Unavailable:** Every 3 days.
* **Communication/Configuration Error:** Initial retries up to 2 times, 4 hours apart, followed by 6 retries, 1 day apart, and finally retries through the end of the dunning cycle, 3 days apart.

# Manual retry and forced collection

For more control, you can initiate a forced collection attempt by clicking the **Attempt Collection Now** button on a pending or past due invoice's details page. However, excessive manual retries might exhaust the allowed transaction count for automated retries. This function is also available via API.

<Image alt="Force Collection" border={false} src="https://files.readme.io/50e0c55-9c0e247-forcecollect.png" title="9c0e247-forcecollect.png" />

# Direct debit payments

Recurly currently supports automatic payment retries for most direct debit methods such as ACH and SEPA, when the response from the bank is due to insufficient funds, or an applicable response code. For situations that may require a retry, such as an invoice correction or update, manual retries are possible and can be executed through the Admin Console or via Recurly’s APIs.

Recurly has implemented a feature to automatically retry Direct Debit payments. Read more on the [Direct Debit Retries](https://docs.recurly.com/docs/sepa-retries) page.

# Specialized Retry strategies

Recurly supports specialized payment retries for certain APMs where necessary, including UPI AutoPay, Pix Automatico, and Mercado Pago. There is no configuration for these payment methods to initiate retries, and are available automatically.

## UPI AutoPay 

UPI AutoPay retries must be completed on the same day as the initial failure, and will reattempt up to **2 times** in the hours after the initial failure. After 2 attempts, the invoice will be marked failed and the subscription will be handled based on the dunning settings in your configuration.

## Pix Automatico 

Pix Automatico retries must be completed within the same billing period as the initial failure, and will reattempt up to **1-3 times** in the days after the initial failure. Since Pix Automatico retries must complete within the same billing period as the initial renewal transaction, for **shorter billing periods** such as weekly, only one retry may attempt. For billing periods longer than one week, the full retry schedule should complete properly.

## Mercado Pago 

Mercado Pago retries will reattempt up to **3 times**after the initial failure. 

##
