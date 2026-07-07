---
title: Multiple gateway configuration
excerpt: >-
  Configure multiple payment gateways in Recurly to support diverse currencies,
  card types, and payment methods — with gateway hierarchy, default settings,
  and failover.
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
  <div class="rp-overview">Multiple gateway configuration lets you connect several payment gateways to your Recurly account to support different currencies, card types, and payment methods — with control over routing hierarchy, default gateways, and failover behavior.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
    <a class="rp-toc-pill" href="#setting-up-multiple-gateways"><span class="rp-toc-num">4</span>Setup</a>
  </div>
</div>

### Prerequisites

<ul class="rp-list">
  <li>An active Recurly account.</li>
  <li>Access to the gateway providers you want to connect.</li>
  <li>An understanding of your business's transaction routing needs.</li>
</ul>

### Limitations

<ul class="rp-list">
  <li>By default, transactions route to the first gateway added that supports the transaction's currency and card type — unless custom routing or default settings are configured.</li>
  <li>The gateway hierarchy must be correctly understood and configured to ensure transactions process as intended.</li>
</ul>

# Definition

<div class="rp-definition">Multiple gateway configuration lets Recurly merchants connect several payment gateways to accept diverse payment types, process transactions in multiple currencies, and maintain a backup gateway in case a primary gateway experiences downtime.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-layer-group" aria-hidden="true"></i></div>
    <strong>Broad payment support</strong>
    <span>Support a wide range of payment methods and currencies across multiple gateway providers.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-route" aria-hidden="true"></i></div>
    <strong>Optimized transaction routing</strong>
    <span>Prioritize which gateway processes specific transactions based on card type, currency, or custom rules.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-rotate" aria-hidden="true"></i></div>
    <strong>Business continuity</strong>
    <span>Gateway Failover automatically reroutes payments to a secondary gateway if the primary becomes unavailable.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-sliders" aria-hidden="true"></i></div>
    <strong>Custom routing</strong>
    <span>Define gateway use based on your business logic using Custom Gateway Routing.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-table-columns" aria-hidden="true"></i></div>
    <strong>Centralized management</strong>
    <span>View and manage all gateway configurations from a single dashboard.</span>
  </div>
</div>

# Key details

## Gateway support

Recurly supports multiple gateway configurations to cover a range of currencies, card types, and payment methods — including credit cards, external gateway tokens, Amazon Pay, PayPal, Apple Pay, ACH, and more.

## Gateway hierarchy

When multiple gateways are configured, Recurly routes transactions to the first gateway on the list that supports the transaction's card type and currency. Beyond this default, Recurly applies the following routing hierarchy:

1. Transactions with a gateway token (e.g., Vantiv tokens, Braintree tokens)
2. Transactions referencing a `gateway_code` (Custom Gateway Routing)
3. Non-credit card transactions (PayPal, Amazon Pay, Adyen HPP, etc.)
4. The default gateway for credit card transactions
5. The non-default credit card gateway, prioritizing the one added earliest

## Custom gateway routing

For precise control over which gateway handles a transaction, use Recurly's <a href="https://docs.recurly.com/docs/custom-gateway-routing-configuration" target="_blank">Custom Gateway Routing</a>.

## Default gateway

You can set a default gateway for credit card transactions. The default gateway takes precedence when it's compatible with the transaction's card type and currency and no specific `gateway_code` has been assigned via Custom Gateway Routing.

## Gateway failover

<a href="https://docs.recurly.com/docs/gateway-failover" target="_blank">Gateway Failover</a> automatically reroutes transactions to a secondary gateway if the primary becomes unavailable. When the primary gateway recovers, Recurly resumes routing new transactions to it.

# Setting up multiple gateways

## Add a gateway

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Open Payment Gateways</h4><p>In Recurly, go to <strong>Configuration → Payment Gateways</strong>.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Add a new gateway</h4><p>Click <strong>Payment Gateway Actions → Add Payment Gateway</strong> and select your preferred provider from the table of brand icons.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Enter credentials</h4><p>Input the required credentials or API keys for the chosen provider, then confirm and save.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">4</div>
    <div><h4>Repeat for additional gateways</h4><p>To add more gateways, repeat the process with different providers as needed.</p></div>
  </div>
</div>

## Set a default gateway

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Open Default Gateways</h4><p>In the <strong>Payment Gateways</strong> section, find <strong>Default Gateways</strong> in the sidebar.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Edit defaults</h4><p>Click <strong>Edit Defaults</strong>, assign a default gateway for each payment method in the window, then confirm and save.</p></div>
  </div>
</div>

## Enable gateway failover

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Open Gateway Failover settings</h4><p>In the <strong>Payment Gateways</strong> section, find <strong>Gateway Failover</strong> in the sidebar.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Enable failover</h4><p>Toggle failover to <strong>Enabled</strong> or <strong>Disabled</strong> as needed. Note that setting specific Primary and Backup gateways via a dropdown is not available on this page.</p></div>
  </div>
</div>

<div class="rp-callout rp-callout-tip">
  <div><strong><i class="fa-solid fa-lightbulb" aria-hidden="true"></i> Tip</strong> After configuration, run a few test transactions to confirm routing works as expected based on your hierarchy and default settings. Revisit and adjust settings at any time as your needs evolve.</div>
</div>

<br />
