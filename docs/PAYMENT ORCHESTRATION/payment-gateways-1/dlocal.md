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
  <li><strong>UPI mandate migration not supported</strong> — Customer mandates on another platform cannot be migrated to Recurly. Customers must cancel existing mandates and resubscribe. Enrollments are tightly coupled with the acquiring partner, merchant, and consumer — when the acquiring partner changes during a migration, re-enrollment is required per RBI and NPCI rules.</li>
  <li><strong>UPI transaction limit</strong> — RBI mandates limit individual transactions to 15,000 INR without a consumer two-factor flow. This 2FA is handled by the customer's bank UPI app and is not customizable. Plans, or the combined amount of plans sent in the same purchase signup request, should be at or below 15,000 INR to avoid renewal rejections. See <a href="https://docs.recurly.com/recurly-subscriptions/docs/upi-autopay#/" target="_blank">UPI AutoPay</a> documentation for details.</li>
  <li><strong>UPI billing info updates not supported</strong> — If a customer needs to update their VPA or bank account, they must cancel their existing mandate/subscription and re-subscribe.</li>
  <li><strong>No ad-hoc or one-time purchases</strong> — Customer-initiated one-time purchases and merchant-initiated force collections are not supported.</li>
  <li><strong>Recurly.js not supported</strong> — UPI AutoPay and Pix Automatico require direct API integration. Recurly.js is not supported for these payment methods.</li>
  <li><strong>Refunds must be full amount</strong> — Partial refunds are not supported through Ebanx.</li>
  <li><strong>Chargebacks not reflected</strong> — Chargebacks are not currently supported or reflected in Recurly.</li>
  <li><strong>UPI App deep links do not support free trials</strong> — Free trial subscriptions are not available when using UPI App deep links.</li>
  <li>See individual payment method pages for additional limitations.</li>
</ul>

# Definition

<div class="rp-definition">dLocal is a full-service payment management platform built for emerging markets in APAC and LATAM. It supports subscription enrollment, recurring transactions, one time payments, and refunds for GCash. You'll need an existing dLocal relationship and a valid Integration Key to connect Ebanx with Recurly.</div>

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
