---
title: Accounts
excerpt: >-
  Manage all subscriber-related details in Recurly, including account
  hierarchies, billing and shipping addresses, and payment methods via the
  Subscriber Wallet.
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
  <div class="rp-overview">The Accounts section in Recurly is your centralized hub for managing all subscriber-related details — from hierarchical structures to billing addresses, shipping, and payment methods. It's designed to keep your subscriber operations organized and efficient at every scale.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
  </div>
</div>

# Definition

<div class="rp-definition">Accounts in Recurly represent individual subscribers and serve as the single source of truth for all their associated data — subscriptions, invoices, transactions, billing addresses, shipping addresses, and payment methods. Every interaction a subscriber has with your business flows through their account record.</div>

### Dates and times

Recurly records all transactions in **UTC** as the underlying billing timezone. Any dates or times shown on Accounts are automatically converted from UTC to the local time specified in your site settings.

# Key benefits

<div class="rp-benefits rp-benefits-2x2">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Centralized subscriber management</strong>
    <span>One location for all subscriber-related data and actions — no hunting across multiple screens.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Flexible billing structures</strong>
    <span>Invoice rollups within account hierarchies consolidate billing for enterprise clients with multiple subdivisions.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Geographic customization</strong>
    <span>Manage country-, province-, and state-specific details to keep billing and shipping accurate across every region.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Multiple payment methods</strong>
    <span>The Subscriber Wallet lets subscribers store and choose from multiple payment methods, reducing friction at renewal.</span>
  </div>
</div>

# Key details

<div class="rp-nav-grid">
<Cards>
  <Card title="Account hierarchy" href="https://docs.recurly.com/docs/account-hierarchy-1" target="_blank">
    Model parent-child account relationships for enterprise clients with multiple subdivisions.
  </Card>
  <Card title="Account hierarchy — invoice rollup" href="https://docs.recurly.com/docs/ah-invoice-rollup" target="_blank">
    Aggregate invoices from child accounts up to the parent account to consolidate billing.
  </Card>
  <Card title="Countries, provinces, and states" href="https://docs.recurly.com/docs/countries-provinces-and-states" target="_blank">
    Customize subscriber details by geographic location to ensure accuracy in billing and shipping records.
  </Card>
  <Card title="Shipping addresses" href="https://docs.recurly.com/docs/shipping-addresses" target="_blank">
    Manage and allocate shipping addresses for each subscriber to support timely, accurate deliveries.
  </Card>
  <Card title="Shipping addresses per purchase" href="https://docs.recurly.com/docs/shipping-address-per-line-item" target="_blank">
    Assign a specific shipping address to individual line items within a purchase.
  </Card>
  <Card title="Subscriber Wallet" href="https://docs.recurly.com/docs/wallet" target="_blank">
    Store multiple payment methods on a subscriber's account so they can choose how they pay.
  </Card>
  <Card title="Subscriber Wallet implementation guide" href="https://docs.recurly.com/docs/wallet-implementation-guide" target="_blank">
    Step-by-step setup and operational guidance for integrating the Subscriber Wallet into your workflow.
  </Card>
</Cards>
</div>