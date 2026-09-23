---
title: E-Commerce Purchase Guide
excerpt: >-
  Learn how to use the store_billing_info field to optionally store payment data
  for pure ecommerce processing.
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

This guide shows you how to use the V3 <Anchor target="_blank" href="https://recurly.com/developers/api/v2021-02-25/#operation/create_purchase">Purchases endpoint</Anchor> to create a transaction where Recurly \_does not store the payment details\_. This behavior is limited to specific payment methods presently, so ensure you are using the right gateway and payment method.

If you have a gateway payment method combo that is not listed below -- please submit a [feature request](https://example.com).

### Prerequisites & limitations

* Familiarity with Recurly’s API and basic REST concepts
* [Completed the Quickstart Guide](https://docs.recurly.com/recurly-subscriptions/docs/quick-start-guide#/)
* A gateway + payment method where Recurly supports ecommerce transactions
* Supported Gateways and Payment Methods&#x20;
  * GCash when using dLocal (requires non-storage)
  * Credit Cards when using Adyen
* For Credit Card payments on Adyen, all customer-initiated features are supported including Level 2 processing, Level 3 processing, dynamic descriptors, Adyen's fraud ID usage, Kount, 3DS, and more. For any specific questions, please reach out to Support.
* Purchase and separate Authorize + Capture are supported for Cards only. GCash requires usage of the Purchases endpoint only.

# Definition

**Creating Purchases** refers to the process of generating new customer accounts alongside a transaction in a single, consolidated call to the Recurly Purchase endpoint. This streamlines checkout experiences by bundling all required resources into one request.

**eCommerce** **Transaction** refers to an online-based transaction, where the customer is in session in your Checkout flow, and wants to make a one-time purchase (for physical or digital items, as an example) rather than signing up for a subscription.

**Billing Info and Payment Method Storage** refers to the ability and practice of storing a payment method instrument on file for future usage.&#x20;

## eCommerce Use Cases

If you have specific need to allow customers to process transactions without storing their billing info, this page is for you. Example use cases:&#x20;

* Guest / Checkout - a logged-in subscriber wants to buy a one-off item (merch, add-on, upsell) and pay with a different card than the one on file, without disturbing the subscription's default payment method.
* Time-based subscription models - a subscription-model where customers make one time purchases and must return to session after a period of time.&#x20;
* Single-use APMs by design - payment methods like GCash that are inherently redirect/voucher-based and have no vaulting concept — you still need a way to complete the purchase.
* Gift-Subscriptions: A customer buys a subscription or one-time item for someone else and doesn't want their card or payment method to become that recipient's stored payment method. Keep in mind, this would appear as a line item via API versus a plan code with no set payment method.
* An AP team pays down an outstanding invoice or past-due balance with a corporate card that isn't meant to become the account's recurring payment method.
* Regional data residency rules -- jurisdictions that restrict cross-border card storage, so one-time processing sidesteps the residency requirement entirely.
* Short trials -- customer wants to test a purchase flow or make a small one-off buy without risk of it silently becoming the subscription's payment method on next renewal.
* Separate Auth and Capture -- your business model matches any of the above use cases, but you wish to use separate authorization, and capture manually later.

## Requirements&#x20;

* You must be using the Purchases or Purchases/Authorize endpoints
  * Note: GCash only supports the Purchases endpoint, while Cards can use either.
* You must pass the `store_billing_info` field set to `false`&#x20;
* You must be using a supported gateway and payment method. See limitations and prerequisits.

| Parameter                         | Value                                | Description                                                                                                                                                                                                                                     |
| :-------------------------------- | ------------------------------------ | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `billing_info.store_billing_info` | **Boolean.&#x20;**&#x44;efault: true | **Boolean**. Child of billing_info. An identifier for the intent to store the provided payment method on the transaction. Certain payment methods require `true` or `false`. See your respective payment method integration guides for details. |

&#x20;

## Step 1: Generate an eCommerce Request

**Use** a supported client library or our  `store_billing_info`  field in your code. Our client libraries help you build out our APIs easily and process transactions faster. To specify an ecommerce transaction where your intent is to NOT store the billing information provided, set your `store_billing_info` boolean value to `false`. Your expectation should be that Recurly does _not_ store the payment method provided.

**Send** a request to the create`purchase` endpoint on Recurly’s API, including:

* **Customer account data** (e.g., code, name, billing info, phone number, email address, etc.)
* **Line Items** (no plan codes)
* **If applicable, the type** of payment method. This is unnecessary for Cards with Adyen, but GCash requires passing the type field as `gcash`.
* **Store Billing Info indicator** set to `false`

Below an example JSON payload:

```json
{
  "currency": "USD",
  "account": {
      "code": "account-code",
      "billing_info": {
          "first_name": "John",
          "last_name": "Doe",
          "address": {
              "street1": "123",
              "city": "Chicago",
              "region": "IL",
              "postal_code": "60601",
              "country": "US"
          },
          "number": "4111111111111111",
          "month": "03",
          "year": "2030",
          "cvv": "737",
          "store_billing_info": false
      }
  },
  "gateway_code": "gateway-code",
  "line_items": [
      {
          "unit_amount": "10.00",
          "quantity": 2,
          "description": "CIT Physical Charge + Tax",
          "type": "charge",
          "tax_code": "physical",
          "product_code": "1001"
      }
  ],
  "shipping": {
      "address": {
          "first_name": "John",
          "last_name": "Doe",
          "phone": "4567890123",
          "street1": "201 main St",
          "city": "Chicago",
          "region": "IL",
          "postal_code": "45678",
          "country": "US"
      }
  }
}
```

> **Tip:** Many more parameters are available. See the <Anchor target="_blank" href="https://developers.recurly.com/api/latest/#operation/create_purchase">Create Purchase</Anchor> reference to learn more.

***

## Step 2: Process the purchase response

A successful purchase returns an **InvoiceCollection**, which contains any charge or credit invoices generated by the request. If the purchase fails, you’ll receive an error response indicating what went wrong. **Credit Card** purchases will be in a **Approved&#x20;**&#x73;tate, and the invoice will be **Paid**. If you are processing using separate Auth and Capture, your transaction will be in a **Approved** state, and the Invoice will be **Pending**.

***

## Step 3: Verify and finish

After a successful purchase, you can confirm the details via the Recurly Admin UI or by calling Recurly’s API to list details on the purchase, invoice, and account. Please note, the account won't have billing info if there hasn't been anything stored previously.

***

## Step 4: Listen for webhooks

After a successful signup, there will be several webhooks you should listen to in order to ensure you are enabling access to features on in your environment if necessary.

***

# Recommendations and Best Practices

* Use separate auth from capture when there's a genuine fulfillment delay — don't capture until goods ship, to avoid refund churn and reduce chargeback exposure.
* Respect authorization validity windows per scheme/gateway (varies by card brand and MCC) — don't let stale auths expire before capture. The general rule is 7 to 30 days, but check with your gateway on specifics for your business.
* Use 3DS as usual where required, especially where SCA is mandated. eCommerce transactions on Recurly are customer-initiated, so all the applicable requirements including name, billing info, email, phone, etc for ensuring auth rates are still good apply.
* eComemrce transactions are not retried automatically on Recurly. Enable your checkout to allow a customer to click submit again if they mistype information.
* Keep PCI scope minimal where possible via Recurly.js rather than handling card data server-side.
* Pass full Billing Address and CVV where required by acquirer/scheme rules — incomplete data reduces auth rates.
* Ensure your Address and CVV rejection rules are properly set up in Payments Settings.
* On Adyen, or when using Kount, you can set up a custom fraud rule to route these transactions to stricter rules to avoid the typical fraud pitfalls of eCommerce. See our documentation on [Kount](https://docs.recurly.com/recurly-subscriptions/docs/kount) and Recurly support for [Adyen's Revenue Protect custom risk profiles](https://docs.recurly.com/recurly-subscriptions/docs/adyen#revenue-protect-and-protect-premium).
