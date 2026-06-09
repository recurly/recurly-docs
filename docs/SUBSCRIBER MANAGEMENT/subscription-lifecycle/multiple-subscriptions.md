---
title: Multiple subscription support
excerpt: >-
  Learn how to create and manage multiple subscriptions per account in Recurly
  using the purchase endpoint, Admin Console, or the create subscription
  endpoint.
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
  <div class="rp-overview">Recurly lets you assign multiple active subscriptions to a single account — different plans, different billing cycles, all under one roof. Whether you're building a hybrid billing model or simply giving customers more choice, this feature makes it straightforward to create, invoice, and communicate around multiple subscriptions at once.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
    <a class="rp-toc-pill" href="#communication-and-notifications"><span class="rp-toc-num">4</span>Communication and notifications</a>
  </div>
</div>

# Definition

<div class="rp-definition">Multiple subscription support allows a single account to hold several active subscriptions simultaneously. Businesses can combine those subscriptions into a single consolidated invoice or keep billing separate for each — and Recurly handles the invoicing, notifications, and data exports across all of them automatically.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-layer-group" aria-hidden="true"></i></div>
    <strong>Streamlined management</strong>
    <span>Manage all subscriptions for an account in one place, keeping administration and customer management organized and efficient.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-user-check" aria-hidden="true"></i></div>
    <strong>Greater customer choice</strong>
    <span>Offer subscribers the ability to hold multiple plans at once, giving them more ways to engage with your services.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-file-invoice-dollar" aria-hidden="true"></i></div>
    <strong>Flexible billing</strong>
    <span>Combine multiple subscriptions into a single invoice or bill each one separately — whichever approach fits your business model.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-envelope" aria-hidden="true"></i></div>
    <strong>Consolidated notifications</strong>
    <span>When multiple subscriptions are created in a single purchase, Recurly sends one consolidated New Subscription email covering all of them.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-chart-bar" aria-hidden="true"></i></div>
    <strong>Richer data insights</strong>
    <span>Track and analyze subscription data across multiple plans per account for more complete reporting and business decisions.</span>
  </div>
</div>

# Key details

## Purchase endpoint

The <a href="https://developers.recurly.com/api/latest.html#operation/create_purchase" target="_blank">purchase endpoint</a> is the primary way to create multiple subscriptions in a single request. It works for both new and existing accounts and supports combining subscriptions with one-time charges as part of a <a href="https://docs.recurly.com/docs/billing-models#section-hybrid" target="_blank">hybrid billing model</a>.

Two requirements apply to all subscriptions within a single purchase:

- **Shared payment method** — all subscriptions in the purchase must use the same payment method.
- **Consistent collection method** — all subscriptions must share the same collection method.

### Purchase invoices

A purchase containing more than one subscription produces a single invoice that lists each subscription and charge individually. This keeps billing clear for customers while reducing invoice volume for your team.

<div class="rp-callout rp-callout-note">
  <div><strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> Consolidating multiple subscriptions into a single invoice</strong>Subscriptions must meet certain eligibility criteria to be grouped onto one invoice. Use the Aggregate Invoice or Alignment features to consolidate billing, or explore <a href="https://docs.recurly.com/v1.0/docs/calendar-billing" target="_blank">Calendar Billing</a> as an efficient way to merge multiple subscription charges into a single bill.</div>
</div>


<Image src="https://files.readme.io/17cdebe-Screenshot_2.png" align="center" width="75%" border={true} />


## Admin Console

You can add multiple subscriptions to an account directly in the Admin Console by increasing the quantity in the **Quantity** field for a plan. Each subscription is invoiced and billed separately upon payment.

<div class="rp-callout rp-callout-note">
  <div><strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> Note</strong>Multiple subscriptions cannot be created when a subscription start date in the past is provided.</div>
</div>

## Create subscription endpoint

The <a href="https://developers.recurly.com/api/latest.html#operation/create_subscription" target="_blank">create subscription</a> endpoint lets you add individual subscriptions to an account one at a time. Each is invoiced and billed separately upon successful payment. If you have New Subscription or New Invoice email notifications enabled, a separate email is sent for each subscription added through this method.

# Communication and notifications

## Emails

The following email templates support multiple subscription purchases:

- <a href="https://docs.recurly.com/v1.0/docs/email-templates#section-new-subscription" target="_blank">New Subscription</a>
- <a href="https://docs.recurly.com/v1.0/docs/email-templates#section-new-invoice" target="_blank">New Invoice</a>
- <a href="https://docs.recurly.com/v1.0/docs/email-templates#section-payment-confirmation" target="_blank">Payment Confirmation</a>

When multiple subscriptions are created in a single purchase, one New Subscription email is sent containing all subscriptions in the purchase. To update your email templates to support this, see the <a href="https://docs.recurly.com/v1.0/docs/email-templates#section-subscriptions" target="_blank">Subscription fields</a> reference.

## Webhooks

When the multiple subscriptions feature is enabled on your site, the following webhooks include a `subscriptions` XML tag containing a list of all subscriptions on the invoice:

- `new_invoice`
- `closed_invoice`
- `successful_payment`
- `failed_payment`
- `past_due_invoice`
- `new_dunning_event`
- `successful_refund`

If multiple subscriptions is not enabled, these webhooks continue to use the original `subscription` XML tag.

## Exports

When the multiple subscriptions feature is active, any export containing a `subscription_id` column will include an additional `subscription_ids` column listing all subscription IDs in comma-separated format.

## Coupon redemption

For details on how coupons are applied in multiple subscription purchases, see <a href="https://docs.recurly.com/docs/multiple-coupons-per-account#section-multiple-coupons-in-a-multiple-subscription-purchase" target="_blank">Multiple coupons in a multiple subscription purchase</a>.

## Custom notes

Recurly supports customizable invoice notes including Terms & Conditions, Customer Notes, and VAT Reverse Charge Notes (see <a href="https://docs.recurly.com/docs/invoice-settings" target="_blank">Invoice Settings</a>). When using custom notes with multiple subscriptions:

- Each invoice includes one set of each note type, defaulting to site-level settings.
- To customize notes for a specific invoice, specify them in the purchase API request.
- It isn't possible to assign different custom notes to individual subscriptions within a single invoice.

For <a href="https://docs.recurly.com/docs/invoice-settings#section-vat-reverse-charge-notes" target="_blank">VAT Reverse Charge Notes</a> to appear on an invoice, all three conditions must be met:

- Your Recurly site has EU VAT enabled or uses an Avalara AvaTax account.
- The customer is in the EU, has a VAT number, and is based in a different country than your company.
- No custom VAT notes are specified for the invoice (in which case, those override the site-level notes).

<br />
