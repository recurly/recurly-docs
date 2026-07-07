---
title: SEPA
excerpt: >-
  Accept SEPA Direct Debit payments on Recurly for EUR-denominated one-time and
  recurring transactions across the European Union — via Adyen, Stripe,
  GoCardless, or Worldpay.
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
  <div class="rp-overview">SEPA Direct Debit lets merchants process EUR-denominated payments across the European Union using customers' IBAN bank account details. It supports both one-time and recurring payments, and Recurly automatically handles the mandatory customer debit notification requirement.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">2</span>Key details</a>
    <a class="rp-toc-pill" href="#checkout-flow"><span class="rp-toc-num">3</span>Checkout flow</a>
  </div>
</div>

### Prerequisites

<ul class="rp-list">
  <li>A supported SEPA gateway: <a href="https://docs.recurly.com/docs/adyen" target="_blank">Adyen</a>, <a href="https://docs.recurly.com/docs/stripe#/" target="_blank">Stripe</a> (via <a href="https://recurly.com/developers/guides/3rd-party-checkout.html" target="_blank">Third Party Checkout</a>), <a href="https://docs.recurly.com/docs/gocardless" target="_blank">GoCardless</a>, or <a href="https://docs.recurly.com/recurly-subscriptions/docs/worldpaydlocal-latam-support#/overview" target="_blank">Worldpay</a>.</li>
</ul>

### Limitations

<ul class="rp-list">
  <li><strong>EUR only</strong> — SEPA processes transactions in Euros exclusively.</li>
  <li><strong>Mandatory customer notification</strong> — The SEPA Direct Debit rulebook requires merchants to notify customers before every account debit. Recurly handles this automatically via email. See <a href="https://docs.recurly.com/docs/renewal-reminder#sepa-payment-method" target="_blank">SEPA renewal reminders</a> for details.</li>
  <li>100% coupons during signup are not supported — e-mandate creation is required for this payment method. Use a free trial instead where supported (Worldpay). Standard coupons are supported.</li>
</ul>

# Definition

<div class="rp-definition">SEPA (Single Euro Payments Area) Direct Debit is a payment method for processing EUR-denominated one-time and recurring payments across the European Union. It requires customers' names and bank account details in IBAN (International Bank Account Number) format. Per the SEPA Direct Debit rulebook, merchants must notify customers before every account debit — Recurly handles this automatically through email notifications.</div>

# Key details

<div class="rp-card">

### Use cases

**Recurring subscriptions** — Process subscription renewals in EUR for customers across the SEPA zone.

**One-off payments** — Accept single payments via the SEPA Direct Debit scheme in addition to or independently of recurring billing.

</div>

# Checkout flow

Collect the customer's name and IBAN bank account number during checkout to initiate a SEPA Direct Debit transaction.

Recurring SEPA payments can be set up even when the initial transaction is completed through a different payment method that doesn't support recurring billing, such as iDEAL or Sofort.
