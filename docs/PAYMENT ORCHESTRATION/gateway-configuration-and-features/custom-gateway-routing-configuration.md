---
title: 'Custom gateway routing '
excerpt: >-
  Use Recurly's Custom Gateway Routing to direct transactions to a specific
  payment gateway by passing a gateway_code and optionally a backup_gateway_code
  — for failover customization, fund segregation, acceptance rate optimization,
  and subscription routing control.
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
  <div class="rp-overview">Custom Gateway Routing lets you direct transactions to a specific payment gateway by passing a <code>gateway_code</code> in your API requests. Use it to segregate funds, optimize acceptance rates through local processors, and control exactly which gateway handles each transaction or subscription renewal.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Not included in Starter or Pro — contact <a href="https://recurly.com/demo/contact-sales/" target="_blank">Recurly Sales</a> to upgrade</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
    <a class="rp-toc-pill" href="#setup-for-custom-gateway-routing"><span class="rp-toc-num">4</span>Setup</a>
  </div>
</div>

### Prerequisites

<ul class="rp-list">
  <li>Multiple gateways configured in Recurly for the payment type you want to route (e.g., credit cards).</li>
</ul>

### Limitations

<ul class="rp-list">
  <li><strong>Card on File Mandates</strong> — Depending on the gateway, Card on File mandate data is packaged in different formats. In most cases the raw network transaction ID is accepted and recurring transactions process normally. In rare cases, the data is incompatible and failover will not occur.</li>
  <li><strong>Multiple subscriptions in a single request</strong> — When passing <code>gateway_code</code> for multiple subscriptions within a single request, routing to different gateways per subscription is not honoured.</li>
  <li><strong>Custom failover routing</strong> — When using a <code>backup_gateway_code</code>, this applies only to the signup transaction. Backup gateways cannot be applied directly to a subscription.
  <li><strong>Stripe card brand awareness</strong> — Card brands for Stripe gateways are configured in the Stripe dashboard, not in Recurly. Recurly is not aware of which card brands your Stripe account supports. If certain card brands aren't supported by Stripe but are by other gateways, specify a <code>gateway_code</code> to route those transactions to the correct gateway. Review your Stripe configuration in the merchant portal to confirm your routing setup.</li>
</ul>

# Definition

<div class="rp-definition">Custom Gateway Routing is a Recurly feature that lets merchants direct transactions to a specific payment gateway by passing a <code>gateway_code</code> parameter in API requests. It supports fund segregation, acceptance rate optimization, and granular routing control across subscriptions and one-time transactions. This has additionally been improved to include targeting a failover gateway via API by passing <code>backup_gateway_code</code>.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-chart-bar" aria-hidden="true"></i></div>
    <strong>Financial reporting efficiency</strong>
    <span>Separate funds across specific gateway accounts to simplify financial reporting.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-route" aria-hidden="true"></i></div>
    <strong>Business-centric routing</strong>
    <span>Direct transactions based on your specific business logic, giving you control over which gateway handles each payment.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-arrow-trend-up" aria-hidden="true"></i></div>
    <strong>Enhanced acceptance rates</strong>
    <span>Route transactions through local processors to reduce cross-border failures and improve approval rates.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-arrows-rotate" aria-hidden="true"></i></div>
    <strong>Recurring transaction management</strong>
    <span>Update gateway routes for recurring subscriptions at any time to align with renewals and changing business needs.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-arrows-rotate" aria-hidden="true"></i></div>
    <strong>Keep signups flowing when your primary gateway is having an outage</strong>
    <span>By using a backup_gateway_code, you can target which gateway to use if your primary gateway choice is having an temporary outage so that your customer can sign up regardless of downstream issues.</span>
  </div>
</div>

# Key details

## Supported transactions and payment methods

**Supported transaction types:**

- One-time transactions
- Initial subscription transactions
- Recurring subscription renewals `gateway_code` only)

**Supported payment methods:**

- <a href="/docs/credit-cards" target="_blank">Credit cards</a>
- <a href="/docs/paypal-payments" target="_blank">PayPal</a> (excluding PayPal through Braintree)
- Amazon Pay

## Gateway Code behaviour

- Passing `gateway_code` in an API request routes the transaction to the associated gateway. If the code is absent or doesn't match a configured gateway, the transaction routes to the default gateway — with certain mismatches causing a transaction failure.
- The `gateway_code` persists for recurring transactions, routing all subsequent subscription renewals to the specified gateway unless updated.
- Update the `gateway_code` via a PUT request to `v2/subscriptions/:uuid/notes` or `v3 /subscriptions/{subscription_id}`. Clear it with an empty tag to revert to standard routing logic.
- Retrieve the `gateway_code` for a subscription via GET requests to `/subscriptions`.
- Modify the `gateway_code` at the invoice level using `v2/invoices/<uuid>` or `v3 /invoices/<invoice_id>`.
- Unique Recurly gateway instances are required to route to different gateways — either via a unique Merchant Account ID / MID or by using a different gateway provider entirely.
- If the `gateway_code` is incompatible with the payment method on a transaction, the transaction defaults to the original gateway for that method.
- Applying gateway codes to all subscriptions within a single API request is supported.
- For aggregate invoices: if all subscriptions share the same `gateway_code`, that gateway is used. If codes differ or are unspecified, the default gateway is used.
- The `gateway_code` is visible on the transaction detail page, included in the Transaction Export, and appears in webhooks.

## Backup Gateway Code behaviour

- If the `backup_gateway_code` is incompatible with the payment method on a transaction, the transaction will fail.
- Passing `backup_gateway_code` in an API request routes the transaction to the associated gateway if the gateway specified in `gateway_code` is in failover. If the code is absent or doesn't match a configured gateway, the transaction will fail.
- Applying backup gateway codes to subscription(s) via API request is not supported.
- The `backup_gateway_code` does not persist for recurring transactions, routing all subsequent subscription renewals to the default gateway unless updated using the `gateway_code` parameter in a separate call (see "Update the `gateway_code` via a PUT request" for details.)

## Standard gateway routing

If no `gateway_code` is passed, Recurly routes the transaction to the Default Gateway if it supports the combination of payment method, card type, and currency. If the Default Gateway doesn't support the transaction, Recurly looks for another configured gateway that matches. You may specify a `backup_gateway_code` to target failover, even if you don't specify a targeted `gateway_code` in your request.

# Setup for custom gateway routing

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Obtain the gateway code</h4><p>In your Recurly account, go to the gateway configuration page. Each configured gateway has a unique <code>gateway_code</code> generated by Recurly. Note the code for the gateway you want to route transactions to for both primary gateway codes and backup gateway codes.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Identify your API endpoint</h4><p>Custom Gateway Routing is available via the <code>v2/purchases</code> and <code>v3/purchases</code> endpoints. Use the appropriate version for your integration.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Pass the gateway_code in your API request</h4><p>Include the <code>gateway_code</code> parameter at the root level of your request to the purchases endpoint. This directs the transaction to the specified gateway.</p></div>
  </div>
<div class="rp-step">
    <div class="rp-step-num">4</div>
    <div><h4>Pass the backup_gateway_code in your API request</h4><p>Include the <code>backup_gateway_code</code> parameter at the billing info level of your request to the purchases endpoint. This directs the transaction to the specified gateway if your primary gateway selection is in failover (typically when the gateway is experiencing a temporary outage).</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">5</div>
    <div><h4>Use a supported client library</h4><p>Custom Gateway Routing is supported across all Recurly-provided client libraries. Confirm you're using a current supported library.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">6</div>
    <div><h4>Review your configuration</h4><p>Visit the gateway configuration page in Recurly to confirm your gateways and their associated <code>gateway_code</code> values.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">7</div>
    <div><h4>Test the setup</h4><p>Run a few test transactions and monitor their routing to confirm they're directed to the specified gateway per the <code>gateway_code</code> in your requests.</p></div>
  </div>
</div>
