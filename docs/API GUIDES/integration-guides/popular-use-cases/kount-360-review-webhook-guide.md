---
title: Kount 360 Review Webhook guide
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

This guide will provide guidance on what actions you can and should take after receiving a Kount Fraud Status Update webhook. 

### Prerequisites & limitations 

* A Kount 360 Account in sandbox or production mode.
* Familiarity with Recurly’s API, Webhooks, and basic REST concepts.
* Reviewed [Kount 360 Documentation](https://docs.recurly.com/recurly-subscriptions/docs/kount) on Recurly and have configured your webhook endpoint in your Kount account settings.
* Reviewed [Webhooks Overview](https://docs.recurly.com/recurly-subscriptions/docs/overview-webhooks) and are listening to the [Fraud Info Updated](https://docs.recurly.com/recurly-subscriptions/docs/payment-notifications#fraud-info-updated) event.
* Ability to use the 'Review' functions in your Kount account dashboard as well as setup 'Review' flows and rules for your Kount transactions.

# Definitions 

**Kount Review** refers to the process that you will take within the Kount 360 Dashboard when you have transactions ready for review. A 'Review' constitutes a manual review of a (hopefully) small subset of your Kount volume that will require you to make a decision to 'Approve' the transaction or mark it 'Declined'. 

# Basic Flow of Review Status

**Recurly Review Process**: When Recurly encounters a Kount 'Review' response, we will send the transaction out for authorization at the gateway itself. If the gateway approves that transaction request, you will need to make an internal business decision on what you want to do with the transaction and any associated subscriptions or accounts related to that transaction.

When you have made this decision in Kount (Approve or Decline), Recurly will receive a webhook, and then fire a webhook to your integration. Ensure you are listening to the **Fraud Info Updated** webhook. You can read more about it in our [Webhooks guide](https://docs.recurly.com/recurly-subscriptions/docs/payment-notifications#fraud-info-updated).

If you choose to 'Approve' the transaction in Kount, there is nothing you need to do in Recurly as the transaction has likely already been approved.

If you choose to 'Decline' the transaction in Kount, if the transaction in Recurly has already been approved, there are key decisions to make: 

You may choose one or several options in this list: 

* _Refund or void the Transaction_: If the transaction was approved, use Recurly's API to refund or void the transaction. You may void a pending authorization, and if your purchase has not settled yet, the purchase may be voided. If settlement has already occurred, a refund will be processed.
* Cancel or Expire the Subscription: If you do not wish to keep the customer's subscription, cancel or expire the subscription itself.
* Close the Account: If you have determined you do not wish to keep the customer at all, if -- for example -- they are fraudulent, you may close down the account entirely. 

<br />
