---
title: Ecommerce purchase guide
excerpt: >-
  Learn how to use Recurly's Purchases endpoint to process an eCommerce
  transaction without storing the customer's payment details on file.
deprecated: false
hidden: true
metadata:
  robots: index
---
<div class="rp-page">
  <div class="rp-overview">This guide walks you through using Recurly's Purchases endpoint to process an eCommerce transaction without storing the customer's payment details on file. You'll learn which gateways and payment methods support this behavior, how to structure the request, and what to expect in the response — so you can build guest checkout, gift-purchase, and one-off payment flows without disturbing a subscriber's saved payment method.</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-concepts"><span class="rp-toc-num">2</span>Key concepts</a>
    <a class="rp-toc-pill" href="#integration-guide"><span class="rp-toc-num">3</span>Integration guide</a>
    <a class="rp-toc-pill" href="#best-practices"><span class="rp-toc-num">4</span>Best practices</a>
    <a class="rp-toc-pill" href="#error-handling-and-troubleshooting"><span class="rp-toc-num">5</span>Error handling</a>
    <a class="rp-toc-pill" href="#webhooks"><span class="rp-toc-num">6</span>Webhooks</a>
    <a class="rp-toc-pill" href="#testing-your-integration"><span class="rp-toc-num">7</span>Testing</a>
    <a class="rp-toc-pill" href="#whats-next"><span class="rp-toc-num">8</span>What's next</a>
  </div>
</div>

### Prerequisites

<ul class="rp-list">
  <li>Familiarity with Recurly's API and basic REST concepts</li>
  <li>Completed the <a href="https://docs.recurly.com/recurly-subscriptions/docs/quick-start-guide#/" target="_blank">Quickstart Guide</a></li>
  <li>A gateway and payment method combination where Recurly supports eCommerce transactions</li>
</ul>

### Limitations

<ul class="rp-list">
  <li>This behavior is currently limited to specific gateway and payment method combinations: GCash when using dLocal (requires non-storage), and credit cards when using Adyen</li>
  <li>For credit card payments on Adyen, all customer-initiated features are supported, including Level 2 and Level 3 processing, dynamic descriptors, Adyen's fraud ID usage, Kount, and 3-D Secure. For specific questions, contact <a href="mailto:support@recurly.com">support@recurly.com</a> or your CSM</li>
  <li>Purchase and separate authorize-and-capture are supported for cards only. GCash requires the Purchases endpoint only</li>
  <li>If you have a gateway and payment method combination that isn't listed here, submit a feature request</li>
</ul>

# Definition

<div class="rp-definition">Creating a purchase means generating a new customer account alongside a transaction in a single, consolidated call to the Purchases endpoint — bundling everything a checkout needs into one request. By default, Recurly stores the billing details you provide so they're available for future transactions. Setting <code>store_billing_info</code> to <code>false</code> tells Recurly to process the transaction without keeping that payment method on file.</div>

# Key concepts

- **eCommerce transaction**: An online transaction where the customer is in session in your checkout flow, making a one-time purchase — for physical or digital items, for example — rather than signing up for a subscription.
- **Billing info and payment method storage**: The ability and practice of storing a payment method instrument on file in Recurly for future use.

## Common use cases

<ul class="rp-list">
  <li><strong>Guest checkout</strong> — a logged-in subscriber wants to buy a one-off item (merch, add-on, upsell) with a different card than the one on file, without disturbing the subscription's default payment method</li>
  <li><strong>Time-based subscription models</strong> — a subscription model where customers make one-time purchases and must return to session after a period of time</li>
  <li><strong>Single-use APMs by design</strong> — payment methods like GCash are inherently redirect- or voucher-based with no vaulting concept, so you still need a way to complete the purchase</li>
  <li><strong>Gift subscriptions</strong> — a customer buys a subscription or one-time item for someone else and doesn't want their card to become the recipient's stored payment method. This appears as a line item via the API rather than a plan code with a set payment method</li>
  <li><strong>Paying down an outstanding balance</strong> — an AP team pays down an invoice or past-due balance with a corporate card that isn't meant to become the account's recurring payment method</li>
  <li><strong>Regional data residency rules</strong> — jurisdictions that restrict cross-border card storage, where one-time processing sidesteps the residency requirement entirely</li>
  <li><strong>Short trials</strong> — a customer wants to test a purchase flow or make a small one-off buy without risking it silently becoming the subscription's payment method on the next renewal</li>
  <li><strong>Separate authorization and capture</strong> — your business model matches any of the above use cases, but you want to authorize now and capture manually later</li>
</ul>

# Integration guide

## Requirements

<ul class="rp-list">
  <li>You must have the <code>Enable store_billing_info on purchase requests</code> feature flag enabled — contact <a href="mailto:support@recurly.com">support@recurly.com</a> to have it turned on</li>
  <li>You must be using the Purchases or Purchases/Authorize endpoints. GCash only supports the Purchases endpoint, while cards can use either</li>
  <li>You must pass the <code>billing_info.store_billing_info</code> field set to <code>false</code></li>
  <li>You must be using a supported gateway and payment method — see Limitations above</li>
</ul>

<table class="rp-params">
  <tr class="rp-thead-row"><td>Parameter</td><td>Type</td><td>Description</td></tr>
  <tr><td><code>billing_info.store_billing_info</code></td><td>Boolean. Default: <code>true</code></td><td>An identifier for the intent to store the provided payment method on the transaction. Certain payment methods require <code>true</code> or <code>false</code> — see your respective payment method integration guides for details.</td></tr>
</table>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Generate an eCommerce request</h4><p>Use a supported client library, or set <code>store_billing_info</code> to <code>false</code> directly in your code, to specify an eCommerce transaction where Recurly should not store the billing information provided.</p></div>
  </div>
</div>

Send a request to the create <a href="https://recurly.com/developers/api/v2021-02-25/#operation/create_purchase" target="_blank">Purchases endpoint</a>, including:

<ul class="rp-list">
  <li>Customer account data (code, name, billing info, phone number, email address, and so on)</li>
  <li>Line items (no plan codes)</li>
  <li>If applicable, the payment method type — unnecessary for cards with Adyen, but GCash requires passing the type field as <code>gcash</code></li>
  <li>The store billing info indicator set to <code>false</code></li>
</ul>

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

<div class="rp-callout rp-callout-tip">
  <div><strong><i class="fa-solid fa-lightbulb" aria-hidden="true"></i> Tip</strong>Many more parameters are available. See the <a href="https://developers.recurly.com/api/latest/#operation/create_purchase" target="_blank">Create Purchase</a> reference to learn more.</div>
</div>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Process the purchase response</h4><p>A successful purchase returns an <code>InvoiceCollection</code>, which contains any charge or credit invoices generated by the request.</p></div>
  </div>
</div>

If the purchase fails, you'll receive an error response indicating what went wrong. Credit card purchases return an **Approved** transaction with a **Paid** invoice. If you're using separate authorization and capture, the transaction returns as **Approved** and the invoice remains **Pending**.

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Verify and finish</h4><p>After a successful purchase, confirm the details through the Recurly Admin UI or by calling Recurly's API to list details on the purchase, invoice, and account.</p></div>
  </div>
</div>

<div class="rp-callout rp-callout-note">
  <div><strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> Note</strong>The account won't have billing info if nothing was stored previously.</div>
</div>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">4</div>
    <div><h4>Listen for webhooks</h4><p>After a successful purchase, several webhooks fire so you can enable access to features in your environment as needed.</p></div>
  </div>
</div>

\[TODO: List the specific webhook events this integration should subscribe to]

# Best practices

<ul class="rp-list">
  <li>Use separate authorization and capture when there's a genuine fulfillment delay — don't capture until goods ship, to avoid refund churn and reduce chargeback exposure</li>
  <li>Respect authorization validity windows for your card scheme and gateway; don't let a stale authorization expire before capture. As a general rule this ranges from 7 to 30 days, but confirm specifics with your gateway</li>
  <li>Use 3-D Secure wherever it's required, especially where Strong Customer Authentication (SCA) is mandated. eCommerce transactions on Recurly are customer-initiated, so the usual requirements for strong authorization rates — name, billing info, email, phone, and so on — still apply</li>
  <li>eCommerce transactions aren't retried automatically on Recurly. Build your checkout so a customer can resubmit if they mistype their information</li>
  <li>Keep PCI scope minimal where possible by using Recurly.js rather than handling card data on your server</li>
  <li>Pass the full billing address and CVV wherever your acquirer or card scheme requires it — incomplete data lowers authorization rates</li>
  <li>Confirm your address and CVV rejection rules are properly configured in Payment Settings</li>
  <li>On Adyen, or when using Kount, set up a custom fraud rule to route these transactions to stricter checks and avoid common eCommerce fraud pitfalls. See <a href="https://docs.recurly.com/recurly-subscriptions/docs/kount" target="_blank">Kount</a> and contact <a href="mailto:support@recurly.com">support@recurly.com</a> about <a href="https://docs.recurly.com/recurly-subscriptions/docs/adyen#revenue-protect-and-protect-premium" target="_blank">Adyen's Revenue Protect custom risk profiles</a></li>
</ul>

# Error handling and troubleshooting

If a payment method doesn't support one time e-commerce processing, or if your use case doesn't allow non-storage, you will recieve the following error:&#x20;

**Subscription Endpoint** or attempting to set `false` on a purchase payload that contains a plan code.

```json Error on Storage State
{
    "error": {
        "type": "validation",
        "message": "Billing info: Store billing info subscriptions require billing info to be stored.",
        "params": [
            {
                "param": "billing_info.store_billing_info",
                "message": "Subscriptions require Billing Info to be stored."
            }
        ]
    }
}
```

**Unsupported Response:&#x20;**

```json Unsupported Gateway or Payment Method
{
    "error": {
        "type": "validation",
        "message": "Billing info: Store billing info unstored billing infos are not supported for this payment gateway.",
        "params": [
            {
                "param": "billing_info.store_billing_info",
                "message": "Unstored Billing Infos are not supported for this payment gateway."
            }
        ]
    }
}
```

**Feature not enabled on site:&#x20;**

- Ask support to enable the feature if you see this error.

```json Feature Not Enabled
{
    "error": {
        "type": "validation",
        "message": "The store_billing_info attribute is not enabled for this site.",
        "params": [
            {
                "param": "store_billing_info",
                "message": "The store_billing_info attribute is not enabled for this site."
            }
        ]
    }
}
```

# Webhooks

* There are no specific webhook configuration steps for this use case. Please see standard webhook configuration, testing, and best practices in our dedicated guide.
* Standard payment or authorized payment webhooks apply to these transactions.

# Testing your integration

* Depending on your payment method and gateway, refer to that gateway's integration setup, testing guides on Recurly docs, or specific testing guides for payment methods for further instructions.

# What's next

Now that you can create new  one time ecommerce payments, explore additional use cases on Recurly by visiting our [API reference](https://recurly.com/developers/api/v2021-02-25/).

***

<br />

<br />
