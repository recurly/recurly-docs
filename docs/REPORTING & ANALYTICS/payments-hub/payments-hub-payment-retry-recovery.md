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
# Overview

### Required plan

This feature or setting is available to all customers on any Recurly subscription plan.

### Prerequisites

- Users must have analytics user role permission.

# Definition

This dashboard provides a comprehensive view of Recurly's performance for automatic and intelligent retries over the current period, tracking at-risk revenue across all retry attempts and measuring how effectively initially-failed transactions are being recovered.

# Key benefits

- **Protect Revenue** — Automatically identifies and recovers failed payments before they result in permanent revenue loss or customer churn.
- **Optimize Retry Strategy** — Pinpoints exactly where in the retry cycle recoveries are succeeding or falling off, enabling smarter scheduling and reduced unnecessary attempts.
- **Monitor Performance Trends** — Tracks period-over-period changes in recovery rates and transaction volumes, giving teams early warning signals when retry effectiveness declines.
- **Prioritize High-Impact Failures** — Surfaces the volume and value of at-risk revenue in one place, helping teams focus attention on the failures that matter most to the bottom line.

# Key details

## General Filters (Top Left Corner)

- **Date Range:** Adjust the time interval for your data to track and analyze long-term trends. The default view is typically 30 days.

- **Country:** See data specific to your country, offering relevant insights and comparisons.

- **Gateway:** This filter allows you to segment and analyze data based on available payment processors. You can look at all payment gateways together or examine one at a time to understand where issues are happening.

- **Payment method:** If you want to see the breakdown of failed payments by the method your customers use, this filter lets you select specific payment options to analyze.

- **Initiated by:** This filter allows you to select between CIT (customer initiated) or MIT (merchant initiated) transactions. CIT transactions typically requires more payment authentication.

- **Currency:** This filter allows filtering by the various currencies for your site's geo-location

## Recovered Transactions

The total number of failed payment transactions successfully recovered through the retry engine in the current period, along with a comparison to the previous time period.


<Image src="https://files.readme.io/762dff03e1c061116f32a588b4774298084b83b0b84314545029cb0a18245534-image.png" align="center" border={true} />


## Payment Recovery Over Time

This chart tracks the daily volume of successfully recovered payment transactions in the time period.


<Image src="https://files.readme.io/17a7d85dcb59c007c91f1b156014c8c9a3c8ad0d82001136cc330d7ae04aa625-image.png" align="center" border={true} />


## Revenue Recovered

- **Retry Attempts** - total number of payments that were retried in the time period, compared to the previous time period.
- **Revenue at Risk** - total dollar value of all invoices whose first payment failed during the time period, with a comparison to the previous time period.
- **Recovered Revenue** - total revenue recovered through successful retries — this includes intelligent retries, account updater, payment method updates, and third parties reporting recovery back to Recurly. A comparison to the previous time period is also provided.
- **Recovery Rate** - percentage of at-risk revenue that was successfully recovered in the time period. Note: failures and recoveries are tracked as independent trends and are not matched on a per-invoice basis, so this rate reflects overall recovery health rather than a precise cohort recovery rate.

<br />


<Image src="https://files.readme.io/9e4aa4fe409b04ae46b252e82511196da1b65434e18a9b74c855096f1b376b2c-image.png" align="center" border={true} />


## Success Rate by Retry Attempt

This chart shows the distribution of successful payment recoveries broken down by which retry attempt successfully processed the payment..


<Image src="https://files.readme.io/92efb04bda37a7ce96ed22c5de5937a7b60ac97654b1ea6423ca3d8dc0b536a4-image.png" align="center" border={true} />


<br />
