---
title: Static retries
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

### Required plan

<br />

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

Recurly's intelligent retry logic uses data from billions of transactions to increase the chances of successful payments. This helps keep your customers' subscriptions active and reduces the chance of losing them due to payment issues. By upgrading your Recurly plan, you have access to an optimized retry schedule designed by machine learning for each of your declined transactions, increasing the likelihood of successful transactions.

# Simplified retry strategy

Rather than a one-size-fits-all retry attempt, Recurly applies a customized approach for each failed payment, informed by ongoing analysis and machine learning. This method adapts over time, aiming to find the best moment to re-attempt a transaction. If you are interested, please contact [Recurly Sales](https://recurly.com/demo/contact-sales/) to discuss upgrade options.

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
