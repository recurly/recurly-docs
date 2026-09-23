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
  <div class="rp-overview">This guide shows you how to use Recurly's <a href="https://developers.recurly.com/api/latest/#tag/purchase" target="_blank">Purchase endpoint</a> to create new subscriptions with the GCash wallet payment method through dLocal. It also covers how to use GCash for one time ecommerce transactions.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#creating-purchases"><span class="rp-toc-num">2</span>Creating purchases</a>
  </div>
</div>

### Prerequisites

<ul class="rp-list">
  <li>Familiarity with Recurly's API v3, webhooks, and basic REST concepts</li>
  <li>Completed the <a href="https://docs.recurly.com/recurly-subscriptions/docs/quick-start-guide#/" target="_blank">Quickstart guide</a></li>
  <li>Familiarity with Recurly.js</li>
  <li>A dLocal sandbox and/or production gateway account with GCash enabled</li>
</ul>

### Limitations

<ul class="rp-list">
  <li>GCash one time payments do not store payment method data -- you must allow cusotmers to select GCash as a payment method in your Checkout flow</li>
</ul>

# Definition

<div class="rp-definition">Creating a purchase means generating a new customer account and its subscription or respective line items in a single call to Recurly's Purchase endpoint. This bundles everything a checkout needs — account, billing info, and subscription or line items — into one request instead of several.</div>

# Creating a Subscription Signup

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Generate a GCash wallet payment request</h4><p>Use a supported client library along with Recurly.js to configure your checkout. GCash uses Recurly.js to display the consumer authentication window during checkout.</p></div>
  </div>
</div>

Send a request to the `create_purchase` method on Recurly's API, including:

<ul class="rp-list">
  <li>Customer account data — code, name, billing info, phone number, and email address</li>
  <li>Subscriptions — with plan codes</li>
  <li>The `create_purchase` field set to `gcash`</li>
  <li>If you are processing an ecommerce transaction, the `store_billing_info` field set to `false`</li>
</ul>

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

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Obtain the action result value from the response</h4><p>The response includes an action token in the <code>three_d_secure_action_token_id</code> param. You will feed that through Recurly.js to render the customer authentication modal. Once they have completed, you will receive an action result token from Recurly.js and provide it in <code>three_d_secure_action_result_token_id</code> on the follow-up steps. Simply resubmit the original payload with the new value, and the payment will process.</p></div>
  </div>
</div>

```json Recurly.js Native
```

<br />

<br />
