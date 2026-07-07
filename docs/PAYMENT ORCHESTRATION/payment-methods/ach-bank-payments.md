---
title: ACH (US only)
excerpt: >-
  Accept ACH bank account payments on Recurly for US merchants — with
  NACHA-regulated authorization requirements, dunning guidance, and support
  across Adyen, GoCardless, Stripe, Worldpay, and Check Commerce.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
<div class="rp-callout rp-callout-tip">
  <div><strong><i class="fa-solid fa-lightbulb" aria-hidden="true"></i> Tip</strong> You can try ACH in a sandbox environment before upgrading your plan.</div>
</div>

<div class="rp-page">
  <div class="rp-overview">ACH (Automated Clearing House) lets US merchants debit funds directly from a customer's bank account through Recurly. It's an alternative to credit card processing and physical checks, with support across five gateways. NACHA governs ACH authorization and bank account verification requirements.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Not included in Starter or Pro — contact <a href="https://recurly.com/demo/contact-sales/" target="_blank">Recurly Sales</a> to upgrade</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#checkout-flow-and-settings"><span class="rp-toc-num">2</span>Checkout flow and settings</a>
  </div>
</div>

### Prerequisites

<ul class="rp-list">
  <li>A supported ACH gateway: <a href="https://docs.recurly.com/docs/adyen" target="_blank">Adyen</a>, <a href="https://docs.recurly.com/docs/gocardless" target="_blank">GoCardless</a>, <a href="https://docs.recurly.com/docs/stripe#/" target="_blank">Stripe</a> (via <a href="https://recurly.com/developers/guides/3rd-party-checkout.html" target="_blank">Third Party Checkout</a>), <a href="https://docs.recurly.com/recurly-subscriptions/docs/worldpaydlocal-latam-support#/overview" target="_blank">Worldpay</a>, or <a href="https://docs.recurly.com/docs/check-commerce" target="_blank">Check Commerce</a>.</li>
</ul>

### Limitations

<ul class="rp-list">
  <li>Available to US-based merchants only.</li>
  <li>ACH has extended processing times and a multi-stage invoice lifecycle: pending → scheduled → processed. Each stage has its own implications and available actions.</li>
  <li>ACH transactions cannot be voided via API — voiding is only supported in the Recurly Admin UI.</li>
  <li>Automatic <a href="https://docs.recurly.com/recurly-subscriptions/docs/nacha-verification#/" target="_blank">NACHA bank account verification</a> is not available on all gateways. See the NACHA verification documentation for gateway-specific options.</li>
  <li>100% coupons during signup are not supported — e-mandate creation is required for this payment method. Use a free trial instead where supported. Standard coupons are supported.</li>
</ul>

# Definition

<div class="rp-definition">ACH (Automated Clearing House) is a US payment method that lets Recurly merchants debit funds directly from a customer's bank account. It's governed by <a href="https://www.nacha.org/" target="_blank">NACHA</a>, which sets authorization and bank account verification requirements for all ACH transactions.</div>

# Checkout flow and settings

## Payment authorization

ACH is regulated by <a href="https://www.nacha.org/" target="_blank">NACHA</a>, which defines the authorization merchants must obtain from customers before collecting payments. For bank account verification details, see the <a href="https://docs.recurly.com/recurly-subscriptions/docs/nacha-verification#/" target="_blank">NACHA bank verifications documentation</a>.

Merchants must collect the following from customers at the time of authorization:

<ul class="rp-list">
  <li>Date of purchase</li>
  <li>Amount of purchase</li>
  <li>Customer name</li>
  <li>Account number</li>
  <li>Routing number and bank name</li>
  <li>Authorization language for the payment and whether renewals will occur</li>
  <li>Authorization language to attempt additional collections if the first transaction fails</li>
  <li>Instructions for how and by when the customer must contact the merchant to cancel</li>
</ul>

## Email communication

Customers receive email notifications at key stages of the payment process, keeping them informed of transaction status and next steps.

## Dunning

ACH has longer processing times than card payments. Review your dunning length to confirm it's compatible with your Automatic Collection Dunning settings before going live.

## Recurly settings

### Hosted pages

Enable the **Bank Account** option in your Recurly site's Hosted Pages settings to accept ACH payments on hosted payment and invoice pages.

### Webhooks

Update your webhooks to support ACH invoice state and payment state notifications. See the <a href="https://docs.recurly.com/v1.3/docs/overview-webhooks#/" target="_blank">Webhooks documentation</a> for implementation details and code samples.

### API and Recurly.js

ACH is supported in Recurly.js v3 and API v2. See the <a href="https://dev.recurly.com/docs/lookup-an-accounts-billing-info" target="_blank">API documentation</a> and <a href="https://docs.recurly.com/js/" target="_blank">Recurly.js documentation</a> for integration details.

### Sandbox testing

Test your ACH setup on a Recurly sandbox site using the provided test credentials before going live.

### Per-check limit

Keep your ACH payment threshold in sync with your gateway settings. To modify the threshold, contact your gateway. If issues persist, reach out to <a href="https://support.recurly.com/" target="_blank">Recurly Support</a>.
