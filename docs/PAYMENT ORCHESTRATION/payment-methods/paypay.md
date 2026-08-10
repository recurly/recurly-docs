---
title: PayPay
excerpt: >-
  Accept PayPay in Japan on Recurly via Adyen (Recurly.js) — supporting JPY
  subscriptions 
deprecated: false
hidden: true
icon: fad fa-alicorn
metadata:
  robots: index
---
<div class="rp-page">
  <div class="rp-overview">PayPay wallet enables recurring subscription payments in Japan. Customers authorize their payment after redirecting to a modal. Recurly manages status updates for transactions and tokens via Webhooks from the gateway.</div>
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
  <li><a href="https://docs.recurly.com/recurly-subscriptions/docs/adyen" target="_blank">Adyen</a></li>
</ul>

# Definition

<div class="rp-definition">PayPay is a digital wallet in Japan, where approximately half of the population are registered users. Launched in 2018 as a joint venture between SoftBank and Yahoo Japan, the app lets users pay at restaurants, convenience stores, taxis, and online shops by scanning a QR code or showing a barcode. It has over 70 million users nationwide.

With Recurly, users will be able to sign up for subscriptions using their PayPay wallet and authorizing via modal / pop-up and authenticating to their account directly. Recurly integrates PayPay through Adyen. See the <a href="#" target="_blank">PayPay integration guide</a> to get started.</div>

# Key details

<div class="rp-card">

### Use cases

**Subscription plans** — Combine Recurly's subscription management with Adyen to offer PayPay for recurring billing in Japan.

</div>

## PayPay limitations

PayPay is designed specifically for subscriptions and does not support many standard Recurly features available with credit cards.

<ul class="rp-list">
  <li>Creating subscriptions through the Recurly Admin UI is not supported — PayPay wallet requires a customer to be in session to confirm the subscription via authenticating to their account.</li>
  <li>Recurly Checkout and Hosted Payment Pages are not currently supported.</li>
  <li>100% coupons during signup are not supported — token creation is required. Use a free trial instead. Standard coupons are supported.</li>
  <li>Depending on your acquirer setup, you may be limited to running only Purchase requests or only Auth and Capture requests. Please request SALE Acquirer setup as Recurly renewals are processed as "sale" transactions and do not support separate Auth and Capture. If you are only running one-time transactions and are not using renewals/subscriptions, you can use an AUTH acquirer setup and use the Auth and Capture behavior in Recurly APIs.</li>
</ul>

## Customer actions in the PayPay wallet

Customers interact with their account during signup:

- **Customer Wallet Authentication&#x20;**&#x20;— Required for every new subscription. Without the customer authenticating their wallet credentials, the token is not set up properly and the subscription will fail.

## Required fields

Always send the following with UPI AutoPay transactions:

# Integration guide

PayPay is not supported on Recurly Checkout or Hosted Payment Pages. See the <a href="https://docs.recurly.com/recurly-subscriptions/docs/e#/" target="_blank">PayPay Integration Guide</a> for full implementation details.

## Billing information updates

PayPay doesn't support direct billing info updates in Recurly. Customers must update banking details in their PayPay app. If a customer's wallet account changes, they will need to resubscribe.

## Enrollments and charges (webhooks)

PayPay is asynchronous — transactions begin in a Scheduled state until the customer authenticates in-app. Listen for the following webhooks:

**At signup:**

- `payment.scheduled`
- `subscription.created`

**After customer authenticates in-app:**

- `payment.transaction_status_updated`
- `payment.success`
- `charge_invoice.paid`

## Testing

You will need to acquire a test gateway account with a supported gateway and follow their instructions. You do not need to download the PayPay app to test with Adyen.

# FAQs

<Accordion title="Do you support Auth and Capture with PayPay?">
  Yes, but only if your business use case does not include subscriptions. Recurly's subscription model does not offer automated Auth and Capture on renewals. Only merchants using SALE acquirer setups can use Subscriptions on Recurly when using PayPay.
</Accordion>
