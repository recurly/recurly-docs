---
title: Hourly activation & churn
excerpt: >-
  Learn how Recurly's Hourly Activation and Churn dashboard tracks subscriber
  activity, data freshness, and churn trends in near real time.
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
  <div class="rp-overview">The Hourly Activation and Churn dashboard gives you an operational, hour-by-hour view of subscriber activity, updated throughout the day. Track signups and churn as they happen, review the widgets and charts that make up the dashboard, and understand exactly how fresh the data is at any given moment.</div>
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

<div class="rp-definition">The Hourly Activation and Churn section of Recurly's Reporting & Analytics gives you an operational overview of subscriber activity and trends, updated hourly. It surfaces subscription signups and churn rates so you can make informed decisions faster.</div>

<div class="rp-callout rp-callout-note">
  <div><strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> Note</strong>Subscriber counts focus on individual subscribers, not the number of subscriptions they hold. For guidance on filter tools, see our <a href="https://docs.recurly.com/docs/recurly-analytics-overview#navigation-features" target="_blank">analytics overview documentation</a>.</div>
</div>

# Key benefits

<div class="rp-benefits rp-benefits-2x2">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Near real-time visibility</strong>
    <span>Get up-to-date insight into subscriber activations, churn, and net growth.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Trend analysis</strong>
    <span>Monitor subscriber behavior on an hourly basis and spot emerging patterns.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Performance tracking</strong>
    <span>Compare daily data against past periods for actionable insights.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Decision-making support</strong>
    <span>Use detailed metrics to optimize subscriptions and retention strategies.</span>
  </div>
</div>

# Key details

## General filters

<ul class="rp-list">
  <li><strong>Date</strong>: Select specific timeframes for deeper insights.</li>
  <li><strong>Plan name</strong>: Analyze data by specific subscription plans.</li>
  <li><strong>Combine Subscriptions</strong>: Combines consecutive subscriptions for more accurate metrics.</li>
  <li><strong>Subscriber type</strong>: Filter by all subscribers, paying subscribers (with or without refunds), non-paying subscribers, or trial users.</li>
</ul>

## Hourly activation and churn

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Review the four key widgets</h4><p>These sit at the top of the dashboard and give you an at-a-glance summary of subscriber movement.</p></div>
  </div>
</div>

<ul class="rp-list">
  <li>Subscribers activated</li>
  <li>Subscribers churned</li>
  <li>Net subscribers</li>
  <li>Total subscribers</li>
</ul>


<Image src="https://files.readme.io/c9ac3660913f039be73673a554d5628e3516581bf5a209e3c9891a0bdce37e3f-image.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Analyze the activation and churn charts</h4><p>Both bar charts are interactive — select any bar for granular account-level detail.</p></div>
  </div>
</div>

#### Activations


<Image src="https://files.readme.io/e299713c63c0164ed435ad7fd70c10738f5b9dbe265425bf0aacd6e99f001435-image.png" align="center" width="75%" border={true} />


#### Churn


<Image src="https://files.readme.io/d78ed12c2d6cdb04f1ae5808b2df77bdf5aedc458255e39b6f23177cc0474cbe-image.png" align="center" width="75%" border={true} />


Pay attention to **Plan Rankings** for insight into plan-level performance.

## Key updates on data freshness

<ul class="rp-list">
  <li>Dashboards update hourly, and data can lag up to <strong>two hours</strong>.</li>
  <li><strong>Monthly Recurring Revenue (MRR) updates every two hours</strong> due to computational complexity.</li>
  <li>Dashboards include a timestamp at the bottom indicating the data's last refresh time.</li>
</ul>

#### Exceptions and insights

<ol>
  <li>Some reports can reflect data as recent as <strong>20–25 minutes</strong> old, thanks to faster data lake refreshes (10–15 minutes). Analytics mart processes then add up to <strong>1–1.5 hours of staleness</strong> before the next run.</li>
  <li>Dashboards use a <strong>four-hour cache</strong>. Merchants can clear the cache manually for more recent updates.</li>
</ol>

## Recommendations for real-time updates

If you need updates faster than hourly, using **webhooks** to build a custom solution gives you more control over data freshness — though it requires significant development effort. For high-volume days or executive reporting, the existing hourly updates are usually enough on their own.

Use these tools and insights to manage your subscribers more effectively and align your strategies with data-driven outcomes.
