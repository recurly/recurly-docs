---
title: Involuntary churn
excerpt: >-
  Minimize revenue leakage by effectively managing involuntary churn. Implement
  strategies and tools designed to retain customers and ensure consistent
  revenue streams.
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

Churn Management  is available to all customers on any Recurly subscription plan.

### Prerequisites

* Familiarity with your customer's payment methods and patterns.
* Integration with payment gateways, processors and relationships with card brands.
* Access to customer communication channels for timely notifications.

### Limitations

* Not all involuntary churn can be prevented, as some factors are beyond control.
* Requires regular monitoring and updates to ensure effectiveness.
* Some strategies might not be applicable to all customer segments or payment methods.

# Definition

Involuntary churn refers to the loss of customers due to reasons beyond their direct intent, such as expired credit cards, bank changes, or failed payment attempts. Effective management of involuntary churn involves proactive measures to address these issues before they result in customer attrition.

# Key benefits

* **Revenue protection**: Reduce revenue loss from failed transactions and expiring cards.
* **Enhanced customer experience**: Proactively address issues, reducing friction for customers.
* **Operational efficiency**: Automate processes like card updates and payment retries.
* **Improved retention**: Decrease involuntary churn rates, leading to higher customer lifetime value.
* **Data insights**: Gain a better understanding of churn reasons and patterns to inform future strategies.

# Key details

## Account updater & Amex cardrefresher

Automate the update of customer payment information with the [Account Updater](https://docs.recurly.com/docs/account-updater) service to maintain seamless transactions and service continuity. Utilize the Amex Cardrefresher to ensure American Express card details are current, thus preventing payment interruptions and bolstering customer retention.

## Intelligent retries

The [Intelligent Retries](https://docs.recurly.com/docs/retry-logic) feature, available to Pro and Elite merchants, employs machine learning to determine the best times to reattempt failed transactions, increasing the likelihood of successful payments and reducing involuntary churn. Starter merchants have access to a basic static retry system, with the option to upgrade for more advanced payment recovery solutions.

## Dunning campaigns

Deploy [Dunning Campaigns](https://docs.recurly.com/docs/dunning-management) to alert customers about payment issues, providing them the chance to rectify their payment methods or resolve other issues, thereby averting potential churn.

## Expired card management

Recurly's [Expired Card Management](https://docs.recurly.com/docs/expired-card-management) proactively refreshes expired credit card data, facilitating uninterrupted subscription renewals and significantly diminishing the rate of transaction failures due to expired cards. This feature supplements the traditional method of sending automated emails for expired cards, offering a more robust solution for maintaining customer service continuity.

## Backup payment method

Promote the adoption of a [backup payment method](https://docs.recurly.com/docs/backup-payment-method) among customers to guarantee service continuity. Should the primary payment method fail, the backup will ensure that services remain undisrupted, thus minimizing churn.
