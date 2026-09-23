---
title: dLocal (Philippines)
excerpt: >-
  Connect dLocal to Recurly to process GCash one-time and subscription payments
  in the Philippines.
deprecated: false
hidden: true
link:
  new_tab: false
metadata:
  robots: index
---
<div class="rp-page">
  <div class="rp-overview">dLocal is a gateway platform focused on emerging markets in Asia, Africa, the Middle East, and Latin America (LATAM). Integrating it with Recurly lets you process one time and recurring subscription payments via the GCash wallet payment method used in the Philippines. An existing dLocal relationship is required to enable this integration.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">2</span>Key details</a>
    <a class="rp-toc-pill" href="#configuring-dlocal-in-recurly"><span class="rp-toc-num">3</span>Configuring dLocal in Recurly</a>
    <a class="rp-toc-pill" href="#one-time-payments-with-gcash"><span class="rp-toc-num">4</span>One-time Payments with GCash and dLocal</a>
    <a class="rp-toc-pill" href="#subscription-behavior"><span class="rp-toc-num">5</span>Subscription behavior</a>
    <a class="rp-toc-pill" href="#faqs"><span class="rp-toc-num">6</span>FAQs</a>
  </div>
</div>

### Limitations

<ul class="rp-list">
  <li><strong>GCash billing info updates not supported</strong> — If a customer needs to update their wallet funding source, they must do so in the app itself.</li>
  <li><strong>No ad-hoc or one-time purchases using stored billing info</strong> — Customer-initiated one-time purchases using stored billing info and merchant-initiated force collections are not supported.</li>
  <li><strong>Chargebacks not reflected</strong> — Chargebacks are not currently supported or reflected in Recurly.</li>
  <li><strong>GCash one time payments do not store billing info by design. Customers must reauthenticate via Recurly.js every time.</li>
</ul>

# Definition

<div class="rp-definition">dLocal is a full-service payment management platform built for emerging markets in APAC, specifically, the Philippines. It supports subscription enrollment, recurring transactions, one time payments, and refunds for GCash. You'll need an existing dLocal relationship and a valid Integration Key to connect Ebanx with Recurly.</div>

# Key details

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Feature</td><td>Details</td></tr>
  <tr><td>Services that work with Recurly</td><td>Payment processing, subscriptions, one-time / ecommerce payments with GCash</td></tr>
  <tr><td>Supported operations</td><td>Subscription signups, recurring transactions, refunds, one time purchases</td></tr>
  <tr><td>Supported payment types</td><td><a href="https://docs.recurly.com/docs/upi-autopay#/" target="_blank">GCash</a></td></tr>
  <tr><td>Supported card brands</td><td>N/A</td></tr>
  <tr><td>Gateway-specific 3DS2 supported</td><td>No</td></tr>
  <tr><td>Card on file supported</td><td>No</td></tr>
  <tr><td>Regions</td><td>GCash: Philippines</td></tr>
  <tr><td>Currencies</td><td>PHP only</td></tr>
  <tr><td>Additional feature support</td><td>None</td></tr>
</table>

## Integration guides

Refer to the individual payment method guides for implementation details:

- <a href="https://docs.recurly.com/recurly-subscriptions/docs/upi-autopay-integration-guide#/" target="_blank">GCash integration guide</a>
- <a href="https://docs.recurly.com/recurly-subscriptions/docs/pix-automatico-integration-guide#" target="_blank">One-time Payments / eCommerce integration guide</a>

## Required fields

dLocal and the [GCash method](https://docs.recurly.com/recurly-subscriptions/v1.0_dlocal-gcash/docs/gcash-wallet) requires specific fields authorize a payment successfully.

### GCash Wallet

- Customer first and last name
- Customer email address
- Customer billing address (street address, city, region/state, country, postal/PIN code)
  - **Street address** — House/street name and number&#x20;
  - **City** — Locality and city&#x20;
  - **State** — State or union territory&#x20;
  - **Postal code** — Postal / zip code&#x20;
  - **Country** — Country code (e.g., IN)
- Customer phone number
