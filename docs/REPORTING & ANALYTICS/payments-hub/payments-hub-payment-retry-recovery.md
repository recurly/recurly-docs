---
title: Payment retry recovery
excerpt: >-
  Monitor retained revenue through intelligent retry strategies. Track how
  optimized retry logic helps recover initially failed payments.
deprecated: false
hidden: false
metadata:
  title: Payment Retry Recovery
  robots: index
---
<div class="rp-page">
  <div class="rp-overview">This dashboard gives you a comprehensive view of Recurly's performance for automatic and intelligent retries over the current period, tracking at-risk revenue across all retry attempts and measuring how effectively initially failed transactions are being recovered.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
  </div>
</div>

### Prerequisites

<ul class="rp-list">
  <li>You must have the Analytics user role permission.</li>
</ul>

# Definition

<div class="rp-definition">This dashboard gives you a comprehensive view of Recurly's performance for automatic and intelligent retries over the current period, tracking at-risk revenue across all retry attempts and measuring how effectively initially failed transactions are being recovered.</div>

# Key benefits

<div class="rp-benefits rp-benefits-2x2">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Protect revenue</strong>
    <span>Automatically identify and recover failed payments before they result in permanent revenue loss or customer churn.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Optimize retry strategy</strong>
    <span>Pinpoint exactly where in the retry cycle recoveries are succeeding or falling off, enabling smarter scheduling and fewer unnecessary attempts.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Monitor performance trends</strong>
    <span>Track period-over-period changes in recovery rates and transaction volumes, giving your team early warning signals when retry effectiveness declines.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Prioritize high-impact failures</strong>
    <span>See the volume and value of at-risk revenue in one place, so your team can focus on the failures that matter most to the bottom line.</span>
  </div>
</div>

# Key details

## General filters (top left corner)

<ul class="rp-list">
  <li><strong>Date range</strong> — Adjust the time interval for your data to track and analyze long-term trends. The default view is typically 30 days.</li>
  <li><strong>Country</strong> — See data specific to your country, offering relevant insights and comparisons.</li>
  <li><strong>Gateway</strong> — Segment and analyze data by available payment processors — look at all gateways together or examine one at a time to understand where issues are happening.</li>
  <li><strong>Payment method</strong> — See the breakdown of failed payments by the method your customers use, and select specific payment options to analyze.</li>
  <li><strong>Initiated by</strong> — Select between CIT (customer-initiated) or MIT (merchant-initiated) transactions. CIT transactions typically require more payment authentication.</li>
  <li><strong>Currency</strong> — Filter by the various currencies available for your site's geo-location.</li>
</ul>

## Recovered transactions

The total number of failed payment transactions successfully recovered through the retry engine in the current period, along with a comparison to the previous time period.


<Image src="https://files.readme.io/762dff03e1c061116f32a588b4774298084b83b0b84314545029cb0a18245534-image.png" align="center" width="40%" border={true} />


## Payment recovery over time

This chart tracks the daily volume of successfully recovered payment transactions in the time period.


<Image src="https://files.readme.io/17a7d85dcb59c007c91f1b156014c8c9a3c8ad0d82001136cc330d7ae04aa625-image.png" align="center" width="75%" border={true} />


## Revenue recovered

<ul class="rp-list">
  <li><strong>Retry attempts</strong> — Total number of payments retried in the time period, compared to the previous time period.</li>
  <li><strong>Revenue at risk</strong> — Total dollar value of all invoices whose first payment failed during the time period, with a comparison to the previous time period.</li>
  <li><strong>Recovered revenue</strong> — Total revenue recovered through successful retries, including intelligent retries, Account Updater, payment method updates, and third parties reporting recovery back to Recurly. A comparison to the previous time period is also provided.</li>
  <li><strong>Recovery rate</strong> — Percentage of at-risk revenue successfully recovered in the time period. Failures and recoveries are tracked as independent trends and aren't matched on a per-invoice basis, so this rate reflects overall recovery health rather than a precise cohort recovery rate.</li>
</ul>


<Image src="https://files.readme.io/9e4aa4fe409b04ae46b252e82511196da1b65434e18a9b74c855096f1b376b2c-image.png" align="center" width="75%" border={true} />


## Success rate by retry attempt

This chart shows the distribution of successful payment recoveries broken down by which retry attempt successfully processed the payment.


<Image src="https://files.readme.io/92efb04bda37a7ce96ed22c5de5937a7b60ac97654b1ea6423ca3d8dc0b536a4-image.png" align="center" width="75%" border={true} />
