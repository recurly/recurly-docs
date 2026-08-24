---
title: Overview dashboard
excerpt: >-
  The Overview provides a high-level summary of payment performance, geographic
  distribution, payment method mix, and the health of payment recovery services.
deprecated: false
hidden: false
metadata:
  title: Overview
  robots: index
---
<div class="rp-page">
  <div class="rp-overview">The Overview dashboard provides a high-level summary of payment performance, geographic distribution, payment method mix, and the health of your payment recovery services. If you're using Account Updater or Kount, you'll also see a high-level view of your vault and fraud health metrics.</div>
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

<div class="rp-definition">The Overview dashboard provides a high-level summary of payment performance, geographic distribution, payment method mix, and the health of your payment recovery services. If you're using Account Updater or Kount, you'll also see a high-level view of your vault and fraud health metrics.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Spot issues fast</strong>
    <span>Quickly identify underperforming regions, methods, or transaction types before they impact revenue.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Make smarter decisions</strong>
    <span>Understand what's driving performance so you can prioritize where to act.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Track what matters</strong>
    <span>Keep a pulse on overall payment health without getting lost in the details.</span>
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
  <li><strong>Currency</strong> — Filter by the currencies available for your site's geo-location.</li>
</ul>

## Global payments volume distribution

This map visualizes payment distribution by volume by region — darker shades indicate higher volume, making it easy to spot your strongest markets and revenue concentration at a glance, as well as where you need to focus your expansion efforts.


<Image src="https://files.readme.io/478206576573fb1cf436cee3c2ceb9a0c919e9344a30a461a7f8906b7ede32c2-image.png" align="center" width="75%" border={true} />


## Payment method distribution

This pie chart breaks down your transactions by payment method, showing both the count and associated volume for each, giving you a clear picture of how revenue is distributed across payment types. Understanding your payment method mix helps you identify where customers prefer to pay, so you can prioritize optimization efforts and negotiate better rates where it matters most.


<Image src="https://files.readme.io/8060fa712055cc375fb7dec3a846037383e1a2362162626eabaf1edbeaca0a68-image.png" align="center" width="75%" border={true} />


## Overall success rate

This card displays your total success rate as a single, at-a-glance percentage, paired with a comparison to the previous time period, so you can immediately see whether performance is improving or declining.


<Image src="https://files.readme.io/645df300b087e16cfea9f5568243a38c3c56a1c487678f80eba690928c006b00-image.png" align="center" width="40%" border={true} />


## CIT success rate

This card displays your Customer Initiated Transaction (CIT) success rate as a single, at-a-glance percentage, paired with a comparison to the previous time period, so you can immediately see whether performance is improving or declining.


<Image src="https://files.readme.io/d8db93ab5b0155426a5c125585abed3a7e14b95f9fdfafca218077325824d2bc-image.png" align="center" width="40%" border={true} />


## MIT success rate

This card displays your Merchant Initiated Transaction (MIT) success rate — typically reflecting the health of your subscription renewals — as a single, at-a-glance percentage, paired with a comparison to the previous time period, so you can immediately see whether performance is improving or declining.


<Image src="https://files.readme.io/7cb0e476114665dd4c2f61b623a7902569334a760670dc19df75229d6532faab-image.png" align="center" width="40%" border={true} />


## Payments authorized on updated cards

This card displays the total dollar amount of revenue retained through Account Updater — reflecting payments saved as a result of an automated card update — alongside a comparison to the previous time period, so you can immediately see whether performance is improving or declining.


<Image src="https://files.readme.io/287879519b42f737a13a0e4e02ddb1ff1ceee7142b67b3cbdcdf6c2f141dce8a-image.png" align="center" width="40%" border={true} />


## Payment retry recovered revenue

This card displays the total dollar amount recovered through Payment Retries, representing renewal revenue that would have otherwise been lost to failed transactions, paired with a comparison to the previous time period, so you can immediately see whether performance is improving or declining.


<Image src="https://files.readme.io/c25bedac148aa9ad8957a19cedbd4390a4619d3f1339ff90111b96d8a33186d3-image.png" align="center" width="40%" border={true} />


## Transactions blocked (fraud)

This card displays the total count of blocked fraudulent transactions, paired with a comparison to the previous time period, so you can immediately see whether performance is improving or declining.


<Image src="https://files.readme.io/f1b082dce13f8087e44899fac4705d15147a6c7564ce4b5797d7904c0882bd84-image.png" align="center" width="40%" border={true} />
