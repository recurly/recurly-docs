---
title: APAC Payment Methods
excerpt: >-
  Learn how to implement APAC payment methods with Recurly to accept payments
  across the APAC (Asia Pacific) regions.
deprecated: false
hidden: false
metadata:
  robots: index
---
<div class="rp-page">
  <div class="rp-overview">This page provides an overview of the payment methods Recurly supports across the APAC region: card processing in India on Stripe, UPI AutoPay in India on Ebanx, GCash in the Philippines on dLocal, and BECS in Australia on supported gateways.</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">1</span>Key details</a>
    <a class="rp-toc-pill" href="#webhooks"><span class="rp-toc-num">2</span>Webhooks</a>
  </div>
</div>

# Key details

Recurly supports the following payment methods and gateways across the APAC region:

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Payment method</td><td>Region</td><td>Supported gateway(s)</td></tr>
  <tr><td>Cards</td><td>India</td><td>Stripe</td></tr>
  <tr><td>BECS</td><td>Australia</td><td>Stripe (third-party checkout only), GoCardless</td></tr>
  <tr><td>UPI AutoPay</td><td>India</td><td>Ebanx</td></tr>
  <tr><td>GCash</td><td>Philippines</td><td>dLocal</td></tr>
</table>

<div class="rp-callout rp-callout-note">
  <div><strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> Note</strong>Card acceptance in India on Stripe requires 3-D Secure (3DS). See our Recurly.js guides for 3DS documentation. [TODO: add link to the relevant Recurly.js guide]</div>
</div>

# Webhooks

Most APAC payment methods are asynchronous — transactions and invoices stay in a pending or scheduled state, often for days, until the customer's bank or gateway sends a final status update. Because of this, we recommend subscribing to all relevant webhooks so your integration reflects the correct status as soon as it's available.

<a class="rp-btn-secondary" href="https://docs.recurly.com/recurly-subscriptions/docs/best-practices#/" target="_blank">Webhooks best practices →</a>

***

📋 TODO before publishing:

- [ ] Add the URL for "our dedicated Recurly.js guides" (3DS documentation) — the source named this reference but didn't provide a link
- [ ] Confirm this page should have no plan-availability pill — treated it as a cross-gateway reference page rather than a single gated feature; let me know if that's wrong
