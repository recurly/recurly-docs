---
title: Payment descriptors
excerpt: >-
  Configure dynamic payment descriptors in Recurly to display your business name
  and charge details on customer bank statements — reducing friendly chargebacks
  and improving transparency.
deprecated: false
hidden: false
metadata:
  robots: index
---
<div class="rp-page">
  <div class="rp-overview">Dynamic descriptors let merchants control the text that appears on a customer's bank statement alongside a charge — showing your business name and a recognizable description of what was purchased. Recurly builds descriptors automatically from your DBA and plan or invoice data.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
  </div>
</div>

### Prerequisites

<ul class="rp-list">
  <li><strong>Visa trial descriptors</strong> — Supported on all card-supporting gateways. Recurly adds the word "Trial" to any Visa transaction converting after a trial period.</li>
  <li><strong>Descriptors beyond Visa trial (feature flag required)</strong> — Contact Recurly Support or your account manager to enable: <a href="https://docs.recurly.com/recurly-subscriptions/docs/stripe#/" target="_blank">Stripe</a>, <a href="https://docs.recurly.com/recurly-subscriptions/docs/braintree-rd#/" target="_blank">Braintree</a>.</li>
  <li><strong>Dynamic descriptors (no gateway-specific flag required)</strong> — Supported automatically on: <a href="https://docs.recurly.com/recurly-subscriptions/docs/commerce-hub" target="_blank">Commerce Hub</a>, <a href="https://docs.recurly.com/recurly-subscriptions/docs/freedompay" target="_blank">FreedomPay</a>, <a href="https://docs.recurly.com/recurly-subscriptions/docs/checkoutcom" target="_blank">Checkout.com</a>, <a href="https://docs.recurly.com/recurly-subscriptions/docs/nuvei" target="_blank">Nuvei</a>.</li>
 <li><strong>Dynamic descriptors Suffix-Customization Flag</strong> — Required for customizing your descriptor suffix instead of using plan or line item/invoice description data.</li>
</ul>

### Limitations

<ul class="rp-list">
  <li>Descriptors cannot be modified via the API — the only exception is sending a unique invoice description.</li>
  <li>The descriptor prefix cannot be modified for <strong>Stripe</strong> from within Recurly — it must be set at the gateway level. Only the suffix (plan name or invoice description) is sent to Stripe.</li>
  <li><strong>Braintree</strong> prefixes must be 3, 7, or 12 characters. If your DBA doesn't meet these limits, it will be padded with spaces where possible.</li>
  <li><strong>Braintree</strong> descriptor support is limited to cards and PayPal.</li>
  <li><strong>Stripe</strong> descriptor support is limited to cards, Apple Pay, Google Pay, and network tokens.</li>
  <li>While Recurly sends dynamic descriptors to gateways, gateways may not pass them on to card networks, and issuers have final say on descriptor display. Contact your gateway to confirm descriptor support for your merchant account.</li>
  <li>The Default Business Entity is used for prefix information when not using custom suffix behavior. Dynamic Business Entity support is available when using custom suffix API  parameters.</li>
</ul>

# Definition

<div class="rp-definition">A dynamic descriptor (also called a soft descriptor) is customizable text included with a card transaction that appears on the customer's bank statement. It helps customers recognize charges from your business and reduces friendly chargebacks caused by unrecognizable transactions.

Descriptors are typically limited to 22 characters and follow the format:

**DBA\*Description of Charge (Suffix)**

More specifically, a descriptor is two parts joined by a separator (usually an asterisk):

**Prefix\*Suffix** — where the prefix is the DBA from your business entity, and the suffix is either a custom field sent via API or derived from your plan name or invoice description.

Recurly builds descriptors as follows:

- **Subscriptions** — Uses your company name or DBA as the prefix and the plan name as the suffix. For Visa transactions converting from a trial, "Trial" is added. Example: `AcmeInc*Trial Gold Plan`
- **One-time transactions and invoices without plans** — Uses your company name or DBA as the prefix and the invoice description as the suffix. Examples: `AcmeInc*Charge` or `AcmeInc*One-Time Payment`</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-shield-halved" aria-hidden="true"></i></div>
    <strong>Chargeback reduction</strong>
    <span>Clear, recognizable descriptor text reduces friendly-fraud chargebacks caused by customers not recognizing a charge on their statement.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-eye" aria-hidden="true"></i></div>
    <strong>Transparency</strong>
    <span>Customers see accurate, meaningful information on their bank statement, building trust in your billing process.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-repeat" aria-hidden="true"></i></div>
    <strong>Consistency</strong>
    <span>Customers see the same prefix and recognizable plan or charge details every billing cycle. If your business name changes, notify existing customers to expect the update on their statements.</span>
  </div>
</div>

# Key details

<div class="rp-card">

### Supported transactions and payment methods

**Supported transaction types:**

- One-time transactions
- Initial subscription transactions and subsequent recurring transactions
- Recurring subscription renewals
- Recovery invoices

**Supported payment methods:**

- <a href="https://docs.recurly.com/docs/credit-cards" target="_blank">Credit cards</a> and network tokens
- <a href="https://docs.recurly.com/recurly-subscriptions/docs/apple-pay" target="_blank">Apple Pay</a> and <a href="https://docs.recurly.com/recurly-subscriptions/docs/google-pay-tm" target="_blank">Google Pay</a>
- <a href="https://docs.recurly.com/recurly-subscriptions/docs/paypal" target="_blank">PayPal</a> (Braintree only)

</div>

## Best practices

<ul class="rp-list">
  <li>Keep your <strong>Company Name</strong> and <strong>DBA</strong> current in Site Settings and your Business Entity. Recurly uses DBA over Company Name for descriptor prefixes when both are present. Update these fields whenever your business name changes.</li>
  <li>Name plans something customers will recognize on their bank statement. The first ~22 characters of the plan name are most important — make them immediately identifiable.</li>
  <li>Always add an <strong>Invoice Description</strong> to one-time charges. Use something recognizable to the customer — order numbers work well. If no description is provided, Recurly fills in "Charge" as the suffix.</li>
  <li>Confirm that dynamic descriptors are enabled at your gateway. Some gateways require a setting or feature flag to pass descriptor data.</li>
</ul>

<br />
