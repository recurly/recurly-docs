---
title: Intelligent retries
excerpt: >-
  Boost payment success with Recurly's Intelligent Retries. Harness machine
  learning for optimized transaction retries.
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

This feature **may not be included** in the Starter or Pro plans. If you are interested, please contact [Recurly Sales](https://recurly.com/demo/contact-sales/) to discuss upgrade options.

### Prerequisites

* An active Recurly account in production mode.
* Recurring credit card payment setup.
* Access to the Recurly dashboard and configurations.

### Limitations

* Not applicable for hard declines unless specific conditions are met.
* Direct debit payment methods are not part of Intelligent automatic retries.
* Retries will not exceed 20 total transaction attempts, or 60 days since the invoice creation.

# Definition

Recurly's Intelligent Retries employs machine learning to determine the optimal time for retrying a declined recurring credit card payment. By analyzing vast data points and transaction attributes, it enhances the probability of payment success, ensuring consistent revenue flow and reduced involuntary subscriber churn.

# Key benefits

* **Data-driven decisions**: Utilizes machine learning to determine the best retry schedule.
* **Enhanced revenue recovery**: Increases the chances of successful payment collection.
* **Reduced subscriber churn**: Minimizes disruptions and involuntary subscriber churn.
* **Adaptable logic**: Tailors retry schedules to maximize the opportunity of success.
* **Comprehensive coverage**: Works alongside other revenue recovery strategies such as Dunning.

# Recurly's intelligent retry logic

Recurly's intelligent retry logic uses data from billions of transactions to increase the chances of successful payments. This helps keep your customers' subscriptions active and reduces the chance of losing them due to payment issues. By upgrading your Recurly plan, you have access to an optimized retry schedule designed by machine learning for each of your declined transactions, increasing the likelihood of successful transactions.

# Simplified retry strategy

Rather than a one-size-fits-all retry attempt, Recurly applies a customized approach for each failed payment, informed by ongoing analysis and machine learning. This method adapts over time, aiming to find the best moment to re-attempt a transaction. If you are interested, please contact [Recurly Sales](https://recurly.com/demo/contact-sales/) to discuss upgrade options.

# General retry guidelines

## Soft declines and machine learning

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

![Force Collection](https://files.readme.io/50e0c55-9c0e247-forcecollect.png "9c0e247-forcecollect.png")

# Direct debit payments

Recurly currently does not implement intelligent payment retries for direct debit methods such as ACH and SEPA. For situations that may require a retry, such as an invoice correction or update, static (see link below) and manual retries are possible and can be executed through the Admin Console or via Recurly’s APIs.

Recurly has implemented a static retry feature to automatically retry Direct Debit payments. Read more on the [Direct Debit Retries](https://docs.recurly.com/docs/sepa-retries) page.

# Complementary revenue recovery strategies

Intelligent Retries complement the Dunning customer communication process.. For a deeper dive into the Dunning process, visit the [Dunning Management](https://docs.recurly.com/v1.0/docs/dunning-management) page.
