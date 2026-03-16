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

# Integration Guide

### Webhook Example

You will receive a Fraud Info updated webhook that looks like below. These are only in XML presently.

```xml XML Example
<?xml version="1.0" encoding="UTF-8"?>
<fraud_info_updated_notification>
  <account>
    <account_code>1</account_code>
    <username nil="true">verena</username>
    <email>verena@example.com</email>
    <first_name>Verena</first_name>
    <last_name>Example</last_name>
    <company_name nil="true">Company, Inc.</company_name>
  </account>
  <transaction>
    <id>a5143c1d3a6f4a8287d0e2cc1d4c0427</id>
    <invoice_id>8fjk3sd7j90s0789dsf099798jkliy65</invoice_id>
    <invoice_number type="integer">2059</invoice_number>
    <subscription_id>41e4e03e10be199252613d424290c5c6</subscription_id>
    <subscription_ids type="array">
      <subscription_id>41e4e03e10be199252613d424290c5c6</subscription_id>
    </subscription_ids>
    <action>purchase</action>
    <date type="datetime">2017-10-20T22:39:35Z</date>
    <gateway>authorize</gateway>
    <payment_method>credit_card</payment_method>
    <amount_in_cents type="integer">1000</amount_in_cents>
    <status>success</status>
    <message>This transaction has been approved.</message>
    <gateway_error_codes>1</gateway_error_codes>
    <failure_type nil="true"></failure_type>
    <reference></reference>
    <source>subscription</source>
    <cvv_result code=""></cvv_result>
    <avs_result code=""></avs_result>
    <avs_result_street></avs_result_street>
    <avs_result_postal></avs_result_postal>
    <billing_phone nil="true"></billing_phone>
    <billing_postal></billing_postal>
    <billing_country></billing_country>
    <test type="boolean">true</test>
    <voidable type="boolean">true</voidable>
    <refundable type="boolean">true</refundable>
  </transaction>
</fraud_info_updated_notification>
```

### Refunding or Voiding a Transaction

To refund a transaction, you can call the Invoice Refund endpoint:

* [Refund an invoice](https://recurly.com/developers/api/v2021-02-25/index.html#operation/refund_invoice) by hitting the `https://v3.recurly.com/invoices/{invoice_id}/refund` endpoint where the `invoice-id` is the invoice related to the above webhook.  You may submit the invoice ID or invoice number.

```text POST Request
POST https://v3.recurly.com/invoices/1234/refund
```

[Void (Cancel) an Authorization](https://recurly.com/developers/api/v2021-02-25/index.html#operation/cancelPurchase) by hitting the `https://v3.recurly.com/purchases/{transaction_id}/cancel/` endpoint with the authorization transaction ID. This is only available when you are running separate auth and capture.

```Text POST Request
POST https://v3.recurly.com/purchases/e28zov4fw0v2/cancel/
```

### Canceling or expiring a Subscription

If you choose to cancel or expire the subscription, you may do so by following the cancel or expire.

* [Cancel a subscription](https://recurly.com/developers/api/v2021-02-25/index.html#operation/cancel_subscription): you will need the subscription ID from the webhook to populate the subscription ID in this payload for the `https://v3.recurly.com/subscriptions/{subscription_id}/cancel`

```Text PUT Request
POST https://v3.recurly.com/subscriptions/e28zov4fw0v2/cancel
```

* [Expire / Terminate the Subscription](https://recurly.com/developers/api/v2021-02-25/index.html#operation/terminate_subscription): you will need the subscription ID from the webhook to populate the subscription ID in this payload for the `https://v3.recurly.com/subscriptions/{subscription_id}`DELETE request.

```Text DELETE Request
DELETE https://v3.recurly.com/subscriptions/e28zov4fw0v2
```

### Deactivating an Account

If you also wish to deactivate the account entirely after your Kount review, you may do so.

* [Deactivate an account](https://recurly.com/developers/api/v2021-02-25/index.html#operation/deactivate_account): This will delete any billing info and cancel active subscription (if you did not already cancel them). If you prefer to expire the subscriptions, do that prior to deactivation.

```Text DELETE Request
DELETE https://v3.recurly.com/accounts/e28zov4fw0v2
```

<br />

<br />
