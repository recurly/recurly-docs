---
title: Authorization and capture
excerpt: >-
  An overview of Recurly's Authorization and Capture feature, including how to
  authorize, capture, and cancel transactions via the API for greater payment
  flexibility.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
<div class="rp-page">
  <div class="rp-overview">Authorization and Capture lets you separate the moment you verify a subscriber's payment method from the moment you actually collect funds — giving you a window to confirm inventory, run fraud checks, or time a charge to coincide with a trial's end. This page explains how the flow works and how to implement it using Recurly's API.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
  </div>
</div>

### Prerequisites

<ul class="rp-list">
  <li>Integration with Recurly's API or a supported client library</li>
  <li>A compatible credit card gateway — Authorization and Capture is supported on Braintree, Stripe, Adyen, PayPal Complete, Cybersource, Authorize.net, and CardConnect. Additional gateways will be added based on merchant demand</li>
</ul>

### Limitations

<ul class="rp-list">
  <li>Partial captures and multiple captures are not supported</li>
  <li>You cannot capture more than the originally authorized amount</li>
  <li>Recurly does not automatically authorize cards before recurring subscription renewals</li>
  <li>Delayed capture timing is not customizable</li>
  <li>Authorization and Capture is not fully supported with third-party integrations such as Xero or QuickBooks Online</li>
</ul>

# Definition

<div class="rp-definition">Authorization and Capture is a two-step payment flow that lets you first verify a subscriber's credit card for validity and fund availability, then collect the funds at a time that suits your business. The authorization places a hold on the funds without transferring them — the capture completes the transaction later.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-shield-halved" aria-hidden="true"></i></div>
    <strong>Stronger payment security</strong>
    <span>Authorize cards upfront to confirm legitimacy and fund availability before any money moves — giving you a chance to review before committing.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-clock" aria-hidden="true"></i></div>
    <strong>Flexible capture timing</strong>
    <span>Capture funds when it makes sense for your business — after confirming stock for physical goods, completing a fraud review, or at the end of a free trial period.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Fewer transaction failures</strong>
    <span>Catch and resolve payment issues at authorization — before fulfillment or fund movement — so you reduce failed captures and the friction that comes with them.</span>
  </div>
</div>

# Key details

## How authorization and capture works

Authorization and Capture separates payment verification from fund collection into a two-step flow. An authorization confirms the card is valid and the funds are available, placing a hold on the subscriber's account without transferring money. Once you're ready, a capture completes the transaction and moves the funds. If you decide not to proceed, a cancel releases the hold.

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Action</td><td>What it does</td></tr>
  <tr><td>Authorize</td><td>Sends a preliminary check to the subscriber's bank to confirm the card is valid and sufficient funds exist. Places a hold on the funds without transferring them.</td></tr>
  <tr><td>Capture</td><td>Collects the authorized funds from the subscriber's account, completing the transaction.</td></tr>
  <tr><td>Cancel</td><td>Releases the hold on the subscriber's account without collecting any funds. Use this when you decide not to proceed with a capture.</td></tr>
</table>

## Auth and capture flow

### Part 1: Initiate an authorization

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Access the API or a client library</h4><p>Connect to Recurly's API or your preferred supported client library.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Submit an authorize request</h4><p>Send a POST request to the authorize endpoint for your API version: <code>v3/purchases/authorize</code> or <code>v2/purchases/authorize</code>.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Confirm transaction details</h4><p>Verify that all transaction details are correctly entered before submitting.</p></div>
  </div>
</div>

<div class="rp-callout rp-callout-note">
  <div><strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> API reference</strong>See the <a href="https://recurly.com/developers/api/v2021-02-25/index.html#operation/create_authorize_purchase" target="_blank">V3 Authorize</a> or <a href="https://recurly.com/developers/api-v2/v2.29/#operation/authorizePurchase" target="_blank">V2 Authorize</a> documentation for full endpoint details.</div>
</div>

### Part 2: Capture the authorized amount

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Call the capture endpoint</h4><p>To collect an authorized transaction's funds, send a request to the capture endpoint: <code>v3/purchase/{transaction_id}/capture</code> or <code>v2/purchases/transaction-uuid-{AUTHORIZED-TXN-UUID}/capture</code>.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Include the transaction UUID</h4><p>Pass the transaction UUID from the original authorization in the request.</p></div>
  </div>
</div>

<div class="rp-callout rp-callout-note">
  <div><strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> API reference</strong>See the <a href="https://recurly.com/developers/api/v2021-02-25/index.html#operation/create_capture_purchase" target="_blank">V3 Capture</a> or <a href="https://recurly.com/developers/api-v2/v2.29/#operation/capturePurchase" target="_blank">V2 Capture</a> documentation for full endpoint details.</div>
</div>

### Part 3: Cancel an authorization

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Call the cancel endpoint</h4><p>If you decide not to capture the funds, send a request to the cancel endpoint: <code>v3/purchase/{transaction_id}/cancel</code> or <code>v2/purchases/transaction-uuid-{AUTHORIZED-TXN-UUID}/cancel</code>.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Include the transaction UUID</h4><p>Pass the transaction UUID from the original authorization to release the hold on the subscriber's account.</p></div>
  </div>
</div>

<div class="rp-callout rp-callout-note">
  <div><strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> API reference</strong>See the <a href="https://recurly.com/developers/api/v2021-02-25/index.html#operation/cancelPurchase" target="_blank">V3 Cancel</a> or <a href="https://recurly.com/developers/api-v2/v2.29/#operation/cancelPurchase" target="_blank">V2 Cancel</a> documentation for full endpoint details.</div>
</div>

<br />
