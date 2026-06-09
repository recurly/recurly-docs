---
title: Subscription dashboard
excerpt: >-
  View, organize, and manage all customer subscriptions from Recurly's
  centralized subscription dashboard — with filters, sorting, and direct access
  to create, change, postpone, or expire subscriptions.
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
  <div class="rp-overview">The subscription dashboard is your central hub for managing every customer subscription in Recurly. Sort, filter, and search across all subscriptions by account, plan, status, or billing dates — then take action directly from the dashboard to create, modify, postpone, or expire subscriptions.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">2</span>Key details</a>
  </div>
</div>

### Prerequisites

<ul class="rp-list">
  <li>Active Recurly account with administrative permissions</li>
  <li>Basic understanding of Recurly's subscription models and billing cycles</li>
</ul>

### Limitations

<ul class="rp-list">
  <li>Expired subscriptions cannot be reactivated</li>
</ul>

# Definition

<div class="rp-definition">The subscription dashboard is a centralized platform for creating, modifying, and analyzing customer subscriptions. It provides tools to manage the full subscription lifecycle — including upgrades, downgrades, postponements, and terminations — alongside filters and sorting for efficient account oversight.</div>

# Key details


<Image src="https://files.readme.io/862f5f4-image.png" align="center" width="75%" border={true} />


## Subscription statuses

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Status</td><td>Description</td></tr>
  <tr><td>Future</td><td>The subscription has a start date that hasn't arrived yet. Customers are not invoiced until the start date. Common in B2B contracts with a specified future commencement date.</td></tr>
  <tr><td>Active</td><td>The subscription is live — either paying or in a trial period.</td></tr>
  <tr><td>Canceled</td><td>The subscription is set to expire at the end of the current term. This occurs when a customer cancels their auto-renewing subscription or when the subscription is designed to end after the current term. A canceled subscription can be reactivated before its scheduled expiration date.</td></tr>
  <tr><td>Expired</td><td>The subscription has churned and cannot be reactivated. Expiry can be involuntary (failed dunning cycle) or voluntary (cancellation).</td></tr>
</table>

## Dashboard filters

The dashboard lets you filter and sort by account, plan code, subscription status, creation date, or next invoice date. Filters can overlap and are not mutually exclusive — for example, the Live filter includes both Renewing and Canceled subscriptions.

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Filter</td><td>Description</td></tr>
  <tr><td>All</td><td>Shows all subscriptions.</td></tr>
  <tr><td>Renewing</td><td>Active subscriptions set to renew, including paused subscriptions.</td></tr>
  <tr><td>Future start</td><td>Subscriptions scheduled to activate on a future date.</td></tr>
  <tr><td>Last billing period</td><td>Subscriptions in their final billing cycle, set to expire at the end of the current term.</td></tr>
  <tr><td>Paused</td><td>Active subscriptions that are currently paused and will not generate invoices.</td></tr>
  <tr><td>Canceled</td><td>Subscriptions that will end at the close of their current term.</td></tr>
  <tr><td>Expired</td><td>Subscriptions that are no longer active.</td></tr>
  <tr><td>Trial</td><td>Active subscriptions currently in a trial phase.</td></tr>
  <tr><td>Paying</td><td>Active subscriptions that have moved past the trial period.</td></tr>
</table>

## Subscription actions

<div class="rp-nav-grid">

<Cards>
  <Card title="Create a subscription" href="https://docs.recurly.com/docs/create-subscription" target="_blank">Enroll a customer in a plan — a single customer can hold multiple subscriptions to the same or different plans.</Card>
  <Card title="Change a subscription" href="https://docs.recurly.com/docs/change-subscription" target="_blank">Upgrade, downgrade, or modify invoicing method, effective immediately or at the next term renewal.</Card>
  <Card title="Postpone a subscription" href="https://docs.recurly.com/docs/postpone-subscription" target="_blank">Shorten or lengthen a customer's current billing period, useful for putting a subscription on pause.</Card>
  <Card title="Expire a subscription" href="https://docs.recurly.com/docs/expire-subscription" target="_blank">Cancel a subscription at the next billing date, or terminate it immediately mid-cycle — both result in the subscription expiring.</Card>
</Cards>

</div>

<br />
