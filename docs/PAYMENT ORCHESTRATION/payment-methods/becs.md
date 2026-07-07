---
title: BECS
excerpt: >-
  Accept BECS Direct Debit payments on Recurly for AUD-denominated recurring
  transactions in Australia — via GoCardless or Stripe (Third Party Checkout).
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
  <div class="rp-overview">BECS (Bulk Electronic Clearing System) is Australia's bank-to-bank direct debit scheme for AUD-denominated recurring payments. Recurly supports BECS via GoCardless and Stripe (Third Party Checkout).</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">2</span>Key details</a>
    <a class="rp-toc-pill" href="#checkout-flow"><span class="rp-toc-num">3</span>Checkout flow</a>
  </div>
</div>

### Prerequisites

<ul class="rp-list">
  <li>A supported BECS gateway: <a href="https://docs.recurly.com/docs/gocardless" target="_blank">GoCardless</a> or <a href="https://docs.recurly.com/docs/stripe#/" target="_blank">Stripe</a> (via <a href="https://recurly.com/developers/guides/3rd-party-checkout.html" target="_blank">Third Party Checkout</a>).</li>
</ul>

### Limitations

<ul class="rp-list">
  <li>100% coupons during signup are not supported — billing agreement creation is required for this payment method. Use a free trial instead where supported. Standard coupons are supported.</li>
</ul>

# Definition

<div class="rp-definition">BECS (Bulk Electronic Clearing System) is Australia's direct debit scheme for processing AUD-denominated recurring payments. It allows merchants to collect payments directly from Australian bank accounts using customers' BSB code and account number. Recurly supports BECS through GoCardless and Stripe (Third Party Checkout).</div>

<div class="rp-callout rp-callout-tip">
  <div><strong><i class="fa-solid fa-lightbulb" aria-hidden="true"></i> Tip</strong> See the <a href="https://docs.recurly.com/docs/how-to-test-your-gateway" target="_blank">How to test your gateway</a> guide to verify your setup before going live.</div>
</div>

# Key details

<div class="rp-card">

### Use cases

**Recurring subscriptions** — Use BECS Direct Debit for AUD subscription billing and recurring collections for Australian customers.

**Cross-border direct debit** — GoCardless and Stripe support multiple global direct debit schemes, making it straightforward to expand direct debit collections beyond Australia from the same integration.

</div>

# Checkout flow

Collect the customer's full name, BSB code, and Australian bank account number during checkout to set up a BECS Direct Debit mandate. For address requirements specific to other payment methods on GoCardless or Stripe, consult your gateway's documentation.
