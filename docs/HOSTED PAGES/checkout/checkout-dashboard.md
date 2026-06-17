---
title: Checkout analytics dashboard
excerpt: >-
  Dive deep into Recurly Checkout data to analyze performance at driving cart
  conversion to acquire subscribers and sell products.
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
  <div class="rp-overview">The Checkout analytics dashboard gives you a clear view of how your checkout configurations are performing — from how many visitors are entering the flow to how many are completing a purchase. Use it to identify which configurations are driving revenue, which need attention, and where customers are hitting friction.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
  </div>
</div>

### Prerequisites

<ul class="rp-list">
  <li>Users must have the Analytics user role permission</li>
  <li>At least one Checkout configuration must be created before data appears in the dashboard</li>
</ul>

### Limitations

<ul class="rp-list">
  <li>When no Checkout configurations exist, the dashboard displays a prompt to create one rather than any chart data. The dashboard becomes visible once at least one configuration has been created and checkout sessions have occurred</li>
</ul>


<Image src="https://files.readme.io/ddd08d8bf1f006c36d863cbe381557e0d4cdc2d20de08fe8c386bf11637cef0c-No_Checkout_Configurations.png" align="center" width="75%" border={true} />


# Definition

<div class="rp-definition">The Checkout analytics dashboard shows how your Checkout configurations are performing across the full checkout funnel. Track conversion rates by configuration, monitor which products customers are purchasing, and identify patterns in order value, session duration, and errors — so you can make informed decisions about which experiences to prioritize and which to improve.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-chart-line" aria-hidden="true"></i></div>
    <strong>Checkout flow insights</strong>
    <span>See how many visitors are entering your checkout process and track conversion rates across configurations to identify where your funnel is working — and where it isn't.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-user-check" aria-hidden="true"></i></div>
    <strong>Subscriber conversion analysis</strong>
    <span>Identify which product configurations are converting best, so you can focus on the experiences that are driving the most subscriber and revenue growth.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-magnifying-glass-chart" aria-hidden="true"></i></div>
    <strong>User behavior tracking</strong>
    <span>Understand how long customers spend in the checkout flow and what errors they encounter, so you can reduce friction and improve the overall experience.</span>
  </div>
</div>

# Key details

## Filters

Two filters at the top left of the dashboard control the data shown across all charts:

- **Date range** — Select a specific start and end date for the data displayed.
- **Timeframe** — Adjust the granularity of the view for a more detailed or broader overview.

## Checkout visits

The Checkout visits chart shows how many customers are visiting your checkout pages during the selected period, with a month-over-month comparison.


<Image src="https://files.readme.io/a477494601cfcf5540bc0df1dd4c07239c0d38a46c641af8486e027b5432a142-Checkout_Visits.png" align="center" width="75%" border={true} />


The bar chart breaks visits into three groups: customers who landed on the page without interacting, customers who engaged with at least one element (such as entering payment information or modifying the cart), and customers who completed a purchase.

## Checkout conversion

The Checkout conversion chart answers the core question: of all the customers visiting your checkout pages, how many are completing a purchase?


<Image src="https://files.readme.io/508b34a44b072fa1d2e125501b30bc49afcffa2e8f431107b0a8bf84a3bd2f4d-Checkout_Conversion.png" align="center" width="75%" border={true} />


View overall conversion across all configurations, or drill down into individual configurations to compare performance. The chart also shows which products customers purchased per configuration — useful for understanding which offerings resonate most with your audience. Use this data to prioritize high-performing configurations and deprioritize underperforming ones.

## Checkout average order size

The average order size chart shows how much customers are spending per order, trended over time with a prior-month comparison.


<Image src="https://files.readme.io/b70dc5ff1a35d6eeb40ac125b65187ed227729edde3529cba18c43123542320b-Checkout_Average_Order_Size.png" align="center" width="75%" border={true} />


Monitoring this metric alongside conversion rates helps you identify which configurations are generating the most revenue — not just the most purchases.

## Time to checkout

The time to checkout chart shows how long customers are spending in the checkout flow for each configuration.


<Image src="https://files.readme.io/af035fc22c009c949631e9c2105f6fd1400a0cd46df3018b421ce254bcca51a1-Time_to_Checkout.png" align="center" width="75%" border={true} />


Configurations with shorter completion times may indicate a simpler, more optimized flow. Compare time to checkout against conversion rates and average order value to understand the trade-offs each configuration is making.

## Checkout errors

The Checkout errors chart shows what errors customers are encountering during the checkout process.


<Image src="https://files.readme.io/5fd946bf08723c8b1e1fbe1ca680504ff3ac9b998021b5baf3243816f16d9125-Checkout_Errors.png" align="center" width="75%" border={true} />


Review this chart regularly to surface recurring issues. Spikes in errors may point to gateway configuration problems that can be adjusted to reduce failed transactions and checkout abandonment.
