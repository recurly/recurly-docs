---
title: Subscriber churn analysis
excerpt: >-
  Learn how to use Recurly's Subscriber Churn Analysis dashboard to understand
  why subscribers leave and reduce churn.
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
  <div class="rp-overview">The Subscriber Churn Analysis dashboard tracks subscription losses over time, broken down by voluntary and involuntary reasons. Use it to understand why your subscribers are leaving and identify strategies to reduce churn and improve retention.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
  </div>
</div>

### Prerequisites

<ul class="rp-list">
  <li>Users must have Analytics user role permission.</li>
</ul>

# Definition

<div class="rp-definition">The Subscriber Churn Analysis dashboard tracks subscription losses over a specified timeframe, broken down by voluntary and involuntary reasons. Use it to uncover why your subscribers are leaving and identify strategies to reduce churn and increase retention.</div>

Throughout our analytics, **churn** and **acquisition** are calculated by comparing active subscribers at the beginning of a time period with active subscribers at the end of that period. A subscriber is considered churned if they aren't expired at the beginning of the period but are expired by the end of it. For example, using a weekly timeframe, a subscriber who is active at the start of the week and expired by the end of it counts as churn.

# Key benefits

<div class="rp-benefits rp-benefits-2x2">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Industry comparison</strong>
    <span>Compare key subscription metrics with industry benchmarks to see how you stack up against peers, and spot your strengths and weaknesses.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Competitive insights</strong>
    <span>See how competitors are performing on the same subscription metrics, and find areas where you can differentiate and improve.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Informed decision-making</strong>
    <span>Make decisions based on real-world data to set realistic goals for subscription growth and customer retention.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Forecasting and planning</strong>
    <span>Enable more accurate forecasting and long-term planning, so you can set reachable growth targets and allocate resources effectively.</span>
  </div>
</div>

# Key details

<div class="rp-callout rp-callout-note">
  <div><strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> Note</strong>It's important to understand the difference between a subscriber and a subscription. A single subscriber might hold multiple active subscriptions, but this dashboard focuses on counting each subscriber as one entity, rather than tallying the total subscriptions they hold.</div>
</div>

<div class="rp-callout rp-callout-tip">
  <div><strong><i class="fa-solid fa-lightbulb" aria-hidden="true"></i> Tip</strong>For more on navigating and using the filter tools, see our <a href="https://docs.recurly.com/docs/recurly-analytics-overview#navigation-features" target="_blank">analytics overview documentation</a>.</div>
</div>

## Filters (top left corner)

<ul class="rp-list">
  <li><strong>Date range</strong>: Use the dropdown menus to select a specific timeframe and date range for the data shown on the dashboard.</li>
  <li><strong>Timeframe</strong>: Adjust this to view data over different periods for a more detailed or broader overview.</li>
  <li><strong>Subscriber type</strong>: Categorize the data by subscriber type — paying, non-paying, or trial.</li>
</ul>

## Churn rates

The Subscriber Churn Analysis dashboard is a powerful tool for evaluating the success of your customer retention strategies. By presenting your churn rates clearly, it helps you identify both the strengths and weaknesses of your current approach — understanding these metrics is essential for refining your tactics and improving retention.

Churn rate is calculated by dividing the number of subscribers you lost during a period by the total number of subscribers you had at the start of that period. There are three key churn rates to consider:

<ul class="rp-list">
  <li><strong>Overall churn</strong>: Combines involuntary and voluntary churn for a complete picture of total subscriber loss.</li>
  <li><strong>Involuntary churn</strong>: Subscribers lost due to payment issues, showing how effective your payment recovery efforts are.</li>
  <li><strong>Voluntary churn</strong>: The rate at which subscribers choose to leave on their own, reflecting subscriber satisfaction and perceived value.</li>
</ul>

## Involuntary churn reasons

<ul class="rp-list">
  <li><strong>Non-payment</strong>: The subscription churned due to a failed transaction and an unrecovered invoice.</li>
  <li><strong>Invalid tax location</strong>: The subscription churned because it failed a tax validation check.</li>
  <li><strong>Non-payment (gift)</strong>: The subscription churned because a gift subscription ended without converting to a paid subscription.</li>
  <li><strong>Non-payment (trial)</strong>: The subscription churned because a trial ended without converting to a paid subscription.</li>
</ul>

## Voluntary churn reasons

<ul class="rp-list">
  <li><strong>Non-renewing</strong>: The subscription expired after a fixed number of billing cycles and wasn't renewed.</li>
  <li><strong>Account closed</strong>: The subscription churned because its linked account was manually closed.</li>
  <li><strong>Canceled</strong>: The customer initiated the cancellation.</li>
  <li><strong>Trial ended</strong>: A cardless free trial ended without billing information added.</li>
  <li><strong>Gift ended</strong>: The gift card amount was exhausted without billing info added before the next renewal.</li>
</ul>

## Churn trends

See your performance across all churn rates — overall, involuntary, and voluntary — at a glance, and how that breakdown changes over time. This helps you spot important shifts in how well your retention tactics are working. You can also compare your overall churn rate to the previous year.


<Image src="https://files.readme.io/7d1d5bfc37a1cda8fcde23ee46eee47674ac1326e4925bb64c766e42da182aa9-image.png" align="center" width="75%" border={true} />


### Involuntary churn trend

See the rate of involuntary churn from non-payment, compare specific involuntary churn reasons, and track the year-over-year trend.


<Image src="https://files.readme.io/8fd2b701ab1433d9d5318f68dbda66d3339fce8d881774c40a3437a1e6d2d450-image.png" align="center" width="75%" border={true} />


### Voluntary churn trend

See the rate of voluntary churn, compare specific voluntary churn reasons, and track the year-over-year trend.


<Image src="https://files.readme.io/b15eb9f8e9a0f024006bf37cd7fe63d4e82491337e00732cd0607880df3e5cd5-image.png" align="center" width="75%" border={true} />


### Churn reasons breakdown

Dig into the data to see the specifics across all churn reasons.


<Image src="https://files.readme.io/4b0201dc9c54e36970cca73931bdb90544d887c174a4bae604ac80820e48263c-image.png" align="center" width="75%" border={true} />
