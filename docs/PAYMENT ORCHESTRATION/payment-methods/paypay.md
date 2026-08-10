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
  <li>One-time transactions and CIT purchases are not supported.</li>
  <li>Creating subscriptions through the Recurly Admin UI is not supported — PayPay wallet requires a customer to be in session to confirm the subscription via authenticating to their account.</li>
  <li>Recurly Checkout and Hosted Payment Pages are not currently supported.</li>
  <li>100% coupons during signup are not supported — token creation is required. Use a free trial instead. Standard coupons are supported.</li>
  <li>Depending on your acquirer setup, you may be limited to running only Purchase requests or only Auth and Capture requests. Please request SALE Acquirer setup as Recurly renewals are processed as "sale" transactions and do not support separate Auth and Capture. If you are only running one-time transactions and are not using renewals/subscriptions, you can use an AUTH acquirer setup and use the Auth and Capture behavior in Recurly APIs.</li>
</ul>

## Customer actions in the PayPay wallet

Customers interact with their account during signup:

- **Confirm enrollment** — Required for every new subscription. Without confirmation, the subscription expires and the transaction fails.

## Required fields

Always send the following with UPI AutoPay transactions:

- VPA (if using legacy VPA method)
- Type / Authentication Mode: QR or App Intent
- Customer email address
- Customer first and last name
- Customer billing address (street address, city, region/state, country, postal/PIN code)
  - **Street address** — House/street name and number (e.g., HOUSE NO. 32, MG ROAD)
  - **City** — Locality and city (e.g., VILLAGE OF AMARPUR, NEW DELHI)
  - **State** — State or union territory (e.g., MAHARASHTRA)
  - **Postal code** — PIN code (e.g., 110019)
  - **Country** — Country code (e.g., IN)
- Customer phone number

# Integration guide

UPI AutoPay is not supported on Recurly Checkout or Hosted Payment Pages. See the <a href="https://docs.recurly.com/recurly-subscriptions/docs/upi-autopay-integration-guide#/" target="_blank">UPI AutoPay Integration Guide</a> for full implementation details.

## Creating subscriptions

Use the **subscription** or **purchase** endpoints to create UPI AutoPay subscriptions.

- **VPA** — Provide the VPA in Recurly's `payment_gateway_references` object with `upi_vpa` as the reference type.
- **QR / App Intent** — Provide `type: upi-autopay` and the `authentication_method`. See the <a href="https://docs.recurly.com/recurly-subscriptions/docs/upi-autopay-integration-guide" target="_blank">developer guide</a> for authentication method details.

## Billing information updates

UPI AutoPay doesn't support direct billing info updates in Recurly. Customers must update banking details in their UPI app. If a customer's VPA changes, cancel the existing subscription and have them re-enroll with the new VPA to create a new mandate.

## Net terms and subscription updates

- Use **Net Terms = 0** to avoid payment failures due to limited UPI charge windows.
- Avoid changing subscription prices on a fixed-price UPI mandate. If the price changes, cancel and re-create the subscription with new customer consent.

## Enrollments and charges (webhooks)

UPI AutoPay is asynchronous — transactions begin in a Scheduled state until the customer authenticates in-app. Listen for the following webhooks:

**At signup:**

- `payment.scheduled`
- `subscription.created`

**After customer authenticates in-app:**

- `payment.transaction_status_updated`
- `payment.success`
- `charge_invoice.paid`

When the invoice moves to Paid, that indicates successful customer authentication from the UPI app.

## Unconfirmed or rejected enrollments

If the customer rejects the enrollment or doesn't respond to the in-app notification, the subscription moves to Expired and the invoice/transaction fails. Listen for:

- `subscription.expired`
- `charge_invoice.failed`

## Cancellations

If a customer cancels via their UPI app, Recurly receives a webhook and automatically cancels the subscription. See <a href="https://docs.recurly.com/recurly-subscriptions/docs/expire-subscription#/auto-cancellation-of-a-subscription" target="_blank">automatic subscription cancellations</a> for details.

Listen for: `subscription.canceled`

## Paused subscriptions

If a customer pauses via their UPI app, Recurly receives a webhook and automatically pauses the subscription.

Listen for: `subscription.paused`

## Resumed subscriptions

A customer may resume a paused subscription directly in their UPI app. Recurly sends a webhook and resumes the subscription automatically. If you'd prefer not to allow resumption after a pause, cancel the subscription when you receive the pause webhook.

Listen for: `subscription.resumed`

## Retries

UPI AutoPay retries occur within UPI timeframes (12:00 AM – 7:00 AM IST) on the same day as the initial failure. See the <a href="https://docs.recurly.com/recurly-subscriptions/docs/static-retries#upi-autopay" target="_blank">Static Retries documentation</a> for UPI-specific retry strategy details.

## Testing

Refer to the <a href="https://docs.recurly.com/docs/ebanx-gateway#/" target="_blank">Ebanx gateway documentation</a> for testing procedures.

# Checkout flow

## Initial signup

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Collect authentication details</h4><p>Allow the customer to provide their VPA (if using legacy method), or present a QR code or App Intent link depending on your chosen authentication method. Pass the details to Recurly using the documented gateway token parameters. Confirm INR currency and applicable pricing are set up correctly.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Enrollment request is sent</h4><p>Recurly sends an enrollment request to the gateway. If the customer confirms in their UPI app, the subscription is created and — if the plan has no trial — the first charge is attempted per the plan's currency and amount settings.</p></div>
  </div>
</div>

## Renewals

Renewals occur per plan settings unless the customer pauses or cancels from their UPI app.

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Pre-renewal notification</h4><p>24–48 hours before the renewal date, a pre-debit notification is sent to the gateway, which pushes it to the customer's UPI app.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Payment attempt</h4><p>If the customer hasn't paused or cancelled, Recurly makes a payment attempt after the pre-notification period ends, aligned with the subscription due date.</p></div>
  </div>
</div>

## Recommended webhooks

Listen for the following Recurly webhooks to stay in sync with customer-driven changes in the UPI app:

**Mandate lifecycle:**

- <a href="https://recurly.com/developers/reference/webhooks/#canceled-subscription" target="_blank">subscription.canceled</a> — Fired when the customer cancels their UPI mandate externally.
- <a href="https://recurly.com/developers/reference/webhooks/#paused-subscription" target="_blank">subscription.paused</a> — Fired when the customer pauses their UPI mandate externally.
- <a href="https://recurly.com/developers/reference/webhooks/#resumed-subscription" target="_blank">subscription.resumed</a> — Fired when the customer unpauses their UPI mandate externally.

**Signup and enrollment:**

- `charge_invoice.created` — Sent on initial signup with no trial.
- `charge_invoice.processing` — Sent when enrollment has not yet been confirmed (no trial).
- `charge_invoice.paid` — Sent when enrollment is confirmed (no trial).
- `charge_invoice.failed` — Sent when enrollment is rejected by the customer (no trial).
- `payment.transaction_status_updated` — Sent when enrollment is confirmed (no trial).
- `payment.scheduled` — Sent when enrollment has not yet been confirmed (no trial).
- `subscription.created` — Sent when a subscription is created (with or without trial).
- `subscription.expired` — Sent when a customer does not confirm enrollment (with or without trial).

<div class="rp-callout rp-callout-note">
  <div><strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> Note</strong> For subscriptions with a trial, no invoice webhooks are sent initially. Listen for <code>payment.scheduled</code> and subsequent payment webhooks instead.</div>
</div>

# FAQs

<Accordion title="Do you support UPI QR Code or one-time transactions?">
  QR Code authentication is supported for subscription sign-ups. See the <a href="https://docs.recurly.com/recurly-subscriptions/docs/upi-autopay-integration-guide" target="_blank">UPI AutoPay Integration Guide</a> for details. One-time UPI transactions are not supported.
</Accordion>

<Accordion title="My UPI subscription is failing. How can I fix it?">
  Check the following:

  - Confirm the subscription price hasn't changed without re-engaging the customer.
  - Verify your Mandate Management settings. If set to Manual, you may have missed a webhook requiring a subscription status change.
  - Confirm your customer is responding to UPI app push notifications, especially for charges above 100,000 INR.
  - Check whether you've missed a pause or cancel webhook — your customer may have requested a change that requires action via API or the Admin UI.
</Accordion>

<Accordion title="I updated my customer's VPA on an existing subscription but the original bank account was charged. How do I fix this?">
  Billing info updates are not supported with UPI AutoPay. Cancel the current subscription and have your customer resubscribe with their new VPA to create a new mandate.
</Accordion>
