---
title: MOTO transactions
excerpt: >-
  Unlock the potential of Mail Order / Telephone Order transactions with
  Recurly, facilitating seamless telephone or mail order transactions for your
  back office operations.
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

MOTO (Mail Order / Telephone Order) transactions allow businesses or agents to accept billing information and process payments by request of customers in a card-not-present manner. This is used in scenarios where you or your agents may be accepting and inputting billing information on behalf of your customers. For example, MOTO will be passed when inputting billing information through the Recurly Admin UI or when specified via the API (such as for transactions processed by you or your agents via a custom-built, internal checkout page) once enabled.

# Key details

* **Improved customer experience:** Facilitate smooth transactions for customers who prefer phone or mail orders, enhancing their overall experience.
* **Flexible payment options:** Diversify your payment channels, catering to a broader segment of customers and enhancing accessibility.
* **Enhanced gateway support:** MOTO transactions are supported by a plethora of prominent gateways, ensuring versatility and ease of integration.

# Key details

MOTO indicators are exclusively reserved for certain use cases. These are one-time customer-initiated transactions using fresh billing details that are entered by the Merchant into a billing system that the customer typically does not have access to, like a back office system or Virtual Terminal.

Recurly's MOTO transactions play a crucial role in expanding merchant offerings and revenue channels. However, it's pivotal to note that MOTO indicators should not be used improperly for merchants in regions where PSD2 and SCA are compliance requirements. Recurring transactions remain untouched, continuing their regular course and are not considered MOTO.

Many gateways support MOTO transactions including Adyen, Braintree, Chase Orbital, Cybersource, Stripe, and WorldPay. However, before enabling MOTO transactions, it's important to enable the support for this specific transaction classification in your account if your use case qualifies.

In cases with gateways like Adyen, while MOTO transactions are supported, they often require the completion of additional documentation. As a precaution, it's always wise to speak with your gateway to clarify any concerns.

# How to process MOTO Transactions

## Gateway configuration

To begin, follow these steps:

1. **Contact your Gateway:** Ensure you have MOTO transactions enabled.
2. **Documentation (if necessary):** Complete any paperwork your gateway requires. Certain gateways require additional documentation – please complete this step to avoid errors in processing.

## Recurly Configuration

Optional enablement of MOTO can be completed on _certain_ gateways via the following steps:

1. From the Recurly Admin UI, **select** Configuration → Payment Gateways from the menu on the left.

<Image align="center" border={true} width="30% " src="https://files.readme.io/0b6cbe34ac7aaaee3048d867c74456c6c6162a4bd6efdb00fd1347efb553b623-image.png" className="border" />

2. **Select** Options → **Edit** for the appropriate gateway instance.

<Image align="center" border={true} width="80% " src="https://files.readme.io/33858d709dd0f82c536ee5b337a748c89cc1c4ba647cafcea836af4cb25798f9-image.png" className="border" />

<Image align="center" border={true} width="30% " src="https://files.readme.io/497c95fbf3ced74891ad0f4f1f93ba5266278d0b530fb8e5d6e8fa8bba4dca2e-image.png" className="border" />

3. **Select** the **Enable MOTO transaction** button and save changes.

<Image align="center" border={true} width="80% " src="https://files.readme.io/0f1d08f410b8731accd11f5d9e7b7e324674fdf6be2d4518c59cc1cfad8b5999-image.png" className="border" />

If you are using Gateway Routing, ensure you are routing to the proper gateways to avoid errors in processing.

### Can I use MOTO transactions if my customer is in session on my website?

**No**. When a customer is in session on your website, this is considered a Customer Initiated transaction and is subject to PSD2 and SCA compliance mandates where applicable. To avoid regulatory fines from the card brands, do not classify these transactions as MOTO.

### How can I process a MOTO transaction through Recurly?

If you are integrating to Recurly via API from your back office, ensure you are classifying your transactions through the `/purchase` endpoint as MOTO (`transaction_type` parameter).

You may also add Billing Information and create Invoices directly within your Recurly control panel. Ensure when you do this, you are creating an Invoice and charging immediately and are not creating Subscriptions or Invoices that are collected later on. Immediate Invoice charge is what you're after.

Transactions processed from your website directly by customers, and your recurring subscriptions will not (and should not) be classified as MOTO.

### What’s the difference between MOTO and Unscheduled Card on File MIT Transactions?

MIT (Merchant Initiated Transactions) generally occur without any direct interaction with your customer, such as processing a transaction on a pre-approved schedule outside of a subscription environment, such as a Top Up or Resubmission scenario.

MOTO, on the other hand, it typically driven by direct consumer interaction, such as phone or email, but the actual transaction is driven by the business.
