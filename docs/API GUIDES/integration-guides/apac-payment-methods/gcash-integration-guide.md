---
title: GCash Integration guide
excerpt: >-
  Learn how to accept subscriptions and ecommerce payments with the GCash wallet
  through dLocal, using Recurly's Purchase endpoint and Recurly.js.
deprecated: false
hidden: true
metadata:
  robots: index
---
<div class="rp-page">
  <div class="rp-overview">This guide shows you how to use Recurly's <a href="https://developers.recurly.com/api/latest/#tag/purchase" target="_blank">Purchase endpoint</a> to create new subscriptions with the GCash wallet payment method through dLocal. It also covers how to use GCash for one-time ecommerce transactions.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#integration-guide"><span class="rp-toc-num">2</span>Integration guide</a>
  </div>
</div>

### Prerequisites

<ul class="rp-list">
  <li>Familiarity with Recurly's API v3, webhooks, and basic REST concepts</li>
  <li>Completed the <a href="https://docs.recurly.com/recurly-subscriptions/docs/quick-start-guide#/" target="_blank">Quickstart guide</a></li>
  <li>Familiarity with Recurly.js</li>
  <li>A dLocal sandbox and/or production gateway account with GCash enabled</li>
  <li>If you're planning on implementing ecommerce-style (customer-in-session, one-time transactions) flows, contact <a href="mailto:support@recurly.com">support@recurly.com</a> or your CSM to enable the associated feature flag that allows use of the <code>store_billing_info</code> field</li>
</ul>

### Limitations

<ul class="rp-list">
  <li>GCash one-time payments don't store payment method data for one-time transactions — you must allow customers to select GCash as a payment method in your checkout flow every time, rather than offering a stored account option</li>
</ul>

# Definition

<div class="rp-definition">Creating a purchase means generating a new customer account and its subscription or respective line items in a single call to Recurly's Purchase endpoint. This bundles everything a checkout needs — account, billing info, and subscription or line items — into one request instead of several.</div>

# Integration guide

With GCash, the initial payment request differs slightly depending on whether you're creating a subscription or an ecommerce transaction — response handling is the same either way. See below for the specific request for each flow.

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Generate a GCash wallet payment request</h4><p>Use a supported client library along with Recurly.js to configure your checkout. GCash uses Recurly.js to display the customer authentication window during checkout.</p></div>
  </div>
</div>

## Creating a subscription signup

Send a request to the `create_purchase` method on Recurly's API, including:

<ul class="rp-list">
  <li>Customer account data — code, name, billing info, phone number, and email address</li>
  <li>Tax ID — the customer's tax ID</li>
  <li>Subscriptions — with plan codes</li>
  <li>The `type` field set to `gcash`</li>
  <li>If you're processing an ecommerce transaction instead, the `store_billing_info` field set to `false`</li>
</ul>

\[TODO: Dev/PO review — possible issue: this JSON includes `//` comments (the commented-out `three_d_secure_action_result_token_id` line and the note on `tax_identifier`). JSON doesn't support comments — this will throw a parse error if copied verbatim. Consider moving these notes to prose instead.]

```json Signup Request
{
  "currency": "PHP",
  "account": {
      "code": "account-code",
      "email":"customer-email@example.com",
      "billing_info": {
          "first_name": "First",
          "last_name": "Last",
          //"three_d_secure_action_result_token_id": "BSFIYrYdEbdfcnI982gr9Q",
          "address": {
              "street1": "14 Laurel Road, Florentino Subd.",
              "city": "Brgy. San Antonio",
              "region": "Metro Manila",
              "postal_code": "1234",
              "country": "PH"
          },
          "tax_identifier":"123456789012", // Valid PH tax id
          "store_billing_info": true,
          "type":"gcash"
      }
  },
  "gateway_code": "gateway-code", 
  "subscriptions": [
  {
    "plan_code": "plan-code"
  }
]
}
```

## Creating an ecommerce transaction

Send a request to the `create_purchase` method on Recurly's API, including:

<ul class="rp-list">
  <li>Customer account data — code, name, billing info, phone number, and email address</li>
  <li>Line items with specific values or IDs if you're using the line item catalog</li>
  <li>The `type` field set to `gcash`</li>
  <li>The `store_billing_info` field set to `false`</li>
</ul>

\[TODO: Dev/PO review — possible issue: this JSON includes `//` comments (invalid in JSON, same as the block above), and is missing its closing `}` for the root object while also having an extra trailing `]` — the bracket structure needs to be corrected before this goes live.]

```json Purchase Request
{
  "currency": "PHP",
  "account": {
      "code": "account-code",
      "email":"customer-email@example.com",
      "billing_info": {
          "first_name": "First",
          "last_name": "Last",
          //"three_d_secure_action_result_token_id": "BSFIYrYdEbdfcnI982gr9Q",
          "address": {
              "street1": "14 Laurel Road, Florentino Subd.",
              "city": "Brgy. San Antonio",
              "region": "Metro Manila",
              "postal_code": "1234",
              "country": "PH"
          },
          "tax_identifier":"123456789012", // Valid PH tax id
          "store_billing_info": false,
          "type":"gcash"
      }
  },
  "gateway_code": "gateway-code", 
  "line_items": [
        {
            "unit_amount": "10.00",
            "quantity": 1,
            "description": "Item Description",
            "type": "charge",
            "tax_code": "physical", // or digital
            "product_code": "product-code"
        }
    ]
]
```

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Process the response</h4><p>Whether you're signing up for a subscription or creating an ecommerce transaction, response handling is the same. The initial response includes an action token in the <code>three_d_secure_action_token_id</code> param. Feed that through Recurly.js to render the customer authentication modal. Once the customer completes authentication, you'll receive an action result token from Recurly.js — provide it in <code>three_d_secure_action_result_token_id</code> on the follow-up request. Resubmit the original payload with the new value, and the payment will process.</p></div>
  </div>
</div>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Verify and finish</h4><p>After a successful purchase, confirm the details through the Recurly Admin Dashboard or by calling Recurly's API to list your new account, subscription, or invoice. For GCash ecommerce transactions, there won't be a billing info ID associated with the transaction, invoice, or account if no subscription is on file.</p></div>
  </div>
</div>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">4</div>
    <div><h4>Listen for webhooks</h4><p>You should listen for several webhooks to ensure you enable access to features in your environment, and disable access if a customer cancels their subscription. See <a href="/docs/webhooks" target="_blank">Recurly webhooks</a> for more details.</p></div>
  </div>
</div>

***

📋 TODO before publishing:

- [ ] Fix the malformed second JSON payload (missing closing `}`, extra trailing `]`) — flagged inline above the code block
- [ ] Both JSON payloads contain `//` comments, which aren't valid JSON — flagged inline above each code block
- [ ] Confirm `/docs/webhooks` is the correct link for "Recurly webhooks" — the source named this reference without a URL
- [ ] Add a Testing your integration section (sandbox/test details for GCash via dLocal)
- [ ] Add an Error handling and troubleshooting section
- [ ] Add a What's next section
