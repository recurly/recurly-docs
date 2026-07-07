---
title: BACS (UK Only)
excerpt: >-
  Accept BACS Direct Debit payments on Recurly for GBP-denominated recurring
  transactions in the United Kingdom — via GoCardless, Stripe, or Adyen.
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
  <div class="rp-overview">BACS (Bankers' Automated Clearing Services) is a UK direct debit scheme that lets merchants collect GBP-denominated recurring payments directly from customers' bank accounts. Recurly supports BACS via GoCardless, Stripe, and Adyen.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">2</span>Key details</a>
    <a class="rp-toc-pill" href="#checkout-flow"><span class="rp-toc-num">3</span>Checkout flow</a>
  </div>
</div>

### Prerequisites

<ul class="rp-list">
  <li>A supported BACS gateway: <a href="https://docs.recurly.com/docs/gocardless" target="_blank">GoCardless</a>, <a href="https://docs.recurly.com/docs/stripe#/" target="_blank">Stripe</a> (via <a href="https://recurly.com/developers/guides/3rd-party-checkout.html" target="_blank">Third Party Checkout</a>), or <a href="https://docs.recurly.com/docs/adyen" target="_blank">Adyen</a>.</li>
</ul>

### Limitations

<ul class="rp-list">
  <li>100% coupons during signup are not supported — billing agreement creation is required for this payment method. Use a free trial instead where supported. Standard coupons are supported.</li>
</ul>

# Definition

<div class="rp-definition">BACS Direct Debit is the UK's bank-to-bank payment scheme for collecting recurring payments in GBP. It allows merchants to debit customers' bank accounts directly, making it well-suited for subscription billing. Recurly integrates BACS through GoCardless, Stripe (Third Party Checkout), and Adyen.</div>

<div class="rp-callout rp-callout-tip">
  <div><strong><i class="fa-solid fa-lightbulb" aria-hidden="true"></i> Tip</strong> See the <a href="https://docs.recurly.com/docs/how-to-test-your-gateway" target="_blank">How to test your gateway</a> guide to verify your setup before going live.</div>
</div>

# Key details

<div class="rp-card">

### Use cases

**Recurring subscriptions** — Use BACS Direct Debit for subscription billing and recurring collections in GBP across the UK.

**International direct debit** — GoCardless supports multiple global direct debit schemes beyond BACS, making it straightforward to expand direct debit collections internationally from the same integration.

</div>

# Checkout flow

Collect the customer's full name and UK bank account details (sort code and account number) during checkout to set up a BACS Direct Debit mandate. For specific address requirements per payment method, consult your gateway's documentation.
