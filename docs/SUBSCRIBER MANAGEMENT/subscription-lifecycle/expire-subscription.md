---
title: Expire/cancel subscription
excerpt: >-
  Ensure flexibility and customer satisfaction with our intuitive cancelation
  and expiration options.
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

# Definition

The "Expire/Cancel Subscription" feature in Recurly offers businesses the ability to manage the termination or conclusion of their customer's subscriptions. Whether it's an immediate cancellation, end-of-term expiration, or a customer-initiated change, our solution is crafted to provide flexibility without complexity.

# Definition

When a customer elects to end their subscription at the next bill date or term end, this is called **canceling** the subscription. If you decide to end the subscription early, mid-cycle, this is called **terminating** the subscription. Both result in the subscription **expiring**. Once a subscription is expired, it cannot be reactivated. Only a canceled subscription can be reactivated, which just means the customer changed their mind and decided to continue the subscription before the bill date where the subscription was set to expire. Subscriptions configured to expire at end of their term, will naturally expire at the end of their last billing period.

# Key benefits

* **Empowered customer experience**: Offer cancellation choice, fostering trust and a positive brand interaction.
* **Customizable subscription expiry**: Flexibility in setting subscription end dates—immediate, next bill, or term end.
* **Automated revenue recovery**: Streamline expiration actions based on payment outcomes for efficient dunning management.

# Key details

In the digital age, providing autonomy to users about their subscription choices is essential. Recurly's "Expire/Cancel Subscription" tool enables businesses to strike the right balance between flexibility and effective subscription management.

Subscriptions often run through various states during their lifecycle. They can be active, canceled, or expired based on various factors, including customer decisions, business needs, or externalities like payment failures.

When a subscription is **cancelled**, it remains active for the duration of the subscription period in a 'pre-expiry' state, which means the customer still has the liberty to reactivate it before it moves to the **expired** state and access to the service is terminated. Once a subscription is in the expired state, it cannot be reactivated; a new subscription has to be initiated. Here, the differentiation between 'canceling' and 'terminating' becomes crucial. While cancellation leads to an eventual expiration at a pre-set future date, termination results in an immediate expiration.

<Image align="center" alt={866} caption="Subscriptions can be cancelled at three different timeframes: immediately, next bill date, or term renewal." title="2019-09-04_0922.png" src="https://files.readme.io/9ebba7b-2019-09-04_0922.png" />

# Cancel a Subscription

**a. Admin console:**

* Navigate to the desired account.
* Click on the subscription name.
* From the **Subscription Actions** dropdown, choose **Cancel Subscription**.
* Decide the cancellation type: immediate, at the next billing cycle, or at the end of the term.

**b. Hosted account management:**

* Navigate to the **Hosted Page Settings** under Configuration in the Admin Console.
* Enable the **Cancel subscriptions** option under Customer Options.
* The customer, upon accessing their Hosted Account, will have the option to cancel.

# Auto cancellation of a subscription

In certain cases, Recurly can receive an indicator (usually via webhook) from a gateway indicating a payment method  or mandate is no longer valid, which will result in the cancellation of the related subscription where the tokens or mandates are in use.

**Supported Gatways:**

* [Paypal Complete](https://docs.recurly.com/recurly-subscriptions/docs/paypal-complete)
* [Ebanx](https://docs.recurly.com/recurly-subscriptions/docs/ebanx-gateway#/) (using [UPI AutoPay](https://docs.recurly.com/recurly-subscriptions/docs/upi-autopay#/))

# Reactivate a subscription

> **Note**: The subscription can only be reactivated if it isn't expired or permanently canceled. If you are subject to SCA / PSD2 Compliance mandates, your customer must reauthenticate their stored billing information prior to reactivation. See [3D secure with stored Billing Information](https://docs.recurly.com/v1.1/docs/using-3d-secure-with-stored-billing-information#/) for more details.

**a. Admin console:**

* Go to the desired account.
* Select the canceled subscription's name.
* Use the **Subscription Actions** dropdown and opt for **Reactivate Subscription**.

**b. Hosted account management:**

* If the cancellation option was provided to the customer, they'll see a reactivation option until the subscription expires.

# Terminate a subscription

**a. Admin console:**

* Access the desired account.
* Click on the subscription name.
* From the **Subscription Actions** dropdown, opt for **Cancel Subscription**.
* On the following page, select **Terminate Subscription**.

**b. API:**

Termination can also be initiated through API calls. Specific API documentation will provide the required parameters and endpoints.

# Dunning

Within <a href="https://docs.recurly.com/docs/dunning-management">Dunning Management</a> you can choose to automatically expire a subscription when an invoice for the subscription reaches the end of the dunning cycle without successful payment.

It is important to note that if a subscription expires outside of dunning, via canceling, terminating, or naturally expiring, any past due invoices on the account currently in dunning will not automatically be failed. Those past due invoices will stay open and in dunning until they are either paid or reach the end of their dunning cycle. If you have selected to leave invoices past due at the end of dunning, then the invoices will never automatically fail. If you would like to stop collection on the past due invoices, you will need to manually mark them as failed.
