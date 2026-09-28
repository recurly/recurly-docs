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
  <div class="rp-overview">GCash wallet enables recurring subscription payments in the Philippines. Customers authorize their payment after being redirected to a modal, and Recurly manages transaction and token status updates through webhooks from the gateway.</div>
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

### Limitations

GCash is designed specifically for ecommerce and recurring subscriptions and doesn't support many standard Recurly features available with other methods.

<ul class="rp-list">
  <li>Creating subscriptions through the Recurly Admin Dashboard isn't supported — the GCash wallet requires the customer to be in session to confirm the subscription by authenticating to their account.</li>
  <li>Recurly Checkout and Hosted Payment Pages aren't currently supported.</li>
  <li>100% coupons at signup aren't supported, since token creation is required — use a free trial instead. Standard coupons are supported.</li>
</ul>

# Definition

<div class="rp-definition"><p>GCash is a digital wallet in the Philippines and one of the most widely used mobile payment services in the region. Launched in 2004 under Globe Telecom's fintech arm, Mynt — a joint venture between Globe Telecom, Ayala Corporation, and Ant Group — the app lets users pay at restaurants, convenience stores, taxis, and online shops by scanning a QR code or showing a barcode.</p><p>With Recurly, customers can sign up for subscriptions using their GCash wallet, authorizing and authenticating directly through a modal. Recurly integrates GCash through dLocal. See the <a href="/docs/gcash-integration-guide" target="_blank">GCash integration guide</a> to get started.</p></div>

# Key details

<div class="rp-card">

### Use cases

**Subscription plans** — Combine Recurly's subscription management with dLocal to offer GCash for recurring and one-time payments in the Philippines.

**One-time purchases** — Use GCash to accept single, non-recurring payments from customers in the Philippines.

</div>

# Checkout flow

Customers will select GCash at checkout, and they are redirected to the GCash app (on mobile) or redirected to authenticate (on desktop) to authorize the payment. Payment is completed after customer approval and the final status is confirmed immediately. You will also receive Recurly webhooks in order to handle transaction, invoice, and subscription status in your environment.

## Customer actions in the GCash wallet

The customer must authenticate their wallet credentials for every new subscription.

<div class="rp-callout rp-callout-warning">
  <div><strong><i class="fa-solid fa-triangle-exclamation" aria-hidden="true"></i> Warning</strong>If the customer doesn't authenticate their wallet credentials, the token isn't set up correctly for subscriptions and the subscription signup or purchase fails.</div>
</div>

## Required fields

Always send the following with GCash transactions:

<ul class="rp-list">
  <li><strong>Currency</strong> — PHP</li>
  <li><strong>Locale</strong> — Philippines, unless the consumer's device locale dictates otherwise</li>
  <li><strong>Customer name and billing address</strong> — as with any standard transaction</li>
  <li><strong>Customer Tax ID</strong> — provide for approval</li>
  <li><strong>Email and phone</strong> — provide for approval</li>
</ul>

# Integration guide

GCash isn't supported on Recurly Checkout or Hosted Payment Pages. See the <a href="/docs/gcash-integration-guide" target="_blank">GCash integration guide</a> for full implementation details.

## Billing information updates

GCash doesn't support direct billing info updates in Recurly. Customers must update payment details in their GCash wallet. If a customer's wallet account changes, they'll need to resubscribe.

## Testing

Set up a test account with dLocal and follow their sandbox instructions. You don't need to download the GCash app to test — dLocal provides a sandbox simulator for the redirect flow.

# FAQs

<Accordion title="Do you support Auth and Capture with GCash?">
  No, this is not a supported flow.
</Accordion>

***

📋 TODO before publishing:

- [ ] Confirm the correct URL/slug for the "GCash integration guide" — the source used inconsistent paths (`gcash-integration-guide` vs `/docs/gcash-integration-guide`) and I can't verify this page actually exists at either
- [ ] The Definition previously stated GCash was "launched in 2018 as a joint venture between SoftBank and Yahoo Japan" — that's PayPay's history, not GCash's. Replaced with the verified facts (launched 2004 under Globe Telecom/Mynt, a JV with Ayala Corporation and Ant Group) — please confirm this is the framing you want, and supply a current user count if you'd like a specific figure back in
