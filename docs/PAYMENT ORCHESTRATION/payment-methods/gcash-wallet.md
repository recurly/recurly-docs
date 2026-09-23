---
title: GCash Wallet
excerpt: >-
  Accept GCash wallet on Recurly via dLocal — letting Filipino customers pay
  using their GCash wallet with app-based authentication.
deprecated: false
hidden: true
metadata:
  robots: index
---
<div class="rp-page">
  <div class="rp-overview">GCash wallet enables recurring subscription payments in the Philippines. Customers authorize their payment after redirecting to a modal, and Recurly manages transaction and token status updates through webhooks from the gateway.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">2</span>Key details</a>
    <a class="rp-toc-pill" href="#integration-guide"><span class="rp-toc-num">3</span>Integration guide</a>
    <a class="rp-toc-pill" href="#checkout-flow"><span class="rp-toc-num">4</span>Checkout flow</a>
    <a class="rp-toc-pill" href="#faqs"><span class="rp-toc-num">5</span>FAQs</a>
  </div>
</div>

### Supported gateways

<ul class="rp-list">
  <li><a href="https://docs.recurly.com/recurly-subscriptions/v1.0_dlocal-gcash/docs/dlocal" target="_blank">dLocal</a></li>
</ul>

# Definition

<div class="rp-definition">GCash is a digital wallet in the Philippines, an extremely popular option in the region. Launched in 2018 as a joint venture between SoftBank and Yahoo Japan, the app lets users pay at restaurants, convenience stores, taxis, and online shops by scanning a QR code or showing a barcode. It has over 70 million users nationwide.

With Recurly, customers can sign up for subscriptions using their GCash wallet, authorizing and authenticating directly through a modal. Recurly integrates GCash through dLocal. See the <a href="gcash-integration-guide" target="_blank">GCash integration guide</a> to get started.</div>

# Key details

<div class="rp-card">

### Use cases

**Subscription plans** — Combine Recurly's subscription management with dLocal to offer GCash for recurring and one time payments in the Philippines.

</div>

## GCash limitations

GCash is designed specifically for ecommerce and recurring subscriptions and doesn't support many standard Recurly features available with other methods.

<ul class="rp-list">
  <li>Creating subscriptions through the Recurly admin UI isn't supported — the GCash wallet requires the customer to be in session to confirm the subscription by authenticating to their account.</li>
  <li>Recurly Checkout and Hosted Payment Pages aren't currently supported.</li>
  <li>100% coupons at signup aren't supported, since token creation is required — use a free trial instead. Standard coupons are supported.</li>
</ul>

# Checkout flow

Customers will select GCash at checkout, and they are redirected to the GCash app (on mobile) or redirected to authenticate (on desktop) to authorize the payment. Payment is completed after customer approval and the final status is confirmed immediately. You will also receive Recurly webhooks in order to handle transaction, invoice, and subscription status in your environment.

## Customer actions in the GCash wallet

Customers interact with their account during signup:

- **Customer wallet authentication** — Required for every new subscription.

<div class="rp-callout rp-callout-warning">
  <div><strong><i class="fa-solid fa-triangle-exclamation" aria-hidden="true"></i> Warning</strong>If the customer doesn't authenticate their wallet credentials, the token isn't set up correctly for subscriptions and the subscription signup or purchase fails.</div>
</div>

## Required fields

Always send the following with GCash transactions:

- **Currency** — PHP
- **Locale** — Philippines, unless the consumer's device locale dictates otherwise
- **Customer name and billing address** — as with any standard transaction
- **Email and Phone --&#x20;**&#x70;rovide for approval

# Integration guide

GCash isn't supported on Recurly Checkout or Hosted Payment Pages. See the <a href="gcash-integration-guide" target="_blank">GCash integration guide</a> for full implementation details.

## Billing information updates

GCash doesn't support direct billing info updates in Recurly. Customers must update payment details in their GCash wallet. If a customer's wallet account changes, they'll need to resubscribe.

## Testing

Set up a test account with dLocal and follow their sandbox instructions. You don't need to download the GCash app to test — dLocal provides a sandbox simulator for the redirect flow.

# FAQs

<Accordion title="Do you support Auth and Capture with GCash?">
  No, this is not a supported flow.
</Accordion>

***
