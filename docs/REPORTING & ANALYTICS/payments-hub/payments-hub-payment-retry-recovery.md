---
title: Payment Retry Recovery
excerpt: >-
  Monitor retained revenue through intelligent retry strategies. Track how
  optimized retry logic helps recover initially failed payments.
deprecated: false
hidden: true
metadata:
  title: Payment Retry Recovery
  robots: index
---
# Overview

### Required plan

This feature or setting is available to all customers on any Recurly subscription plan.

### Prerequisites

* Users must have analytics user role permission.

# Definition

This dashboard provides a comprehensive view of Recurly's performance for automatic and intelligent retries over the current period, tracking at-risk revenue across all retry attempts and measuring how effectively initially-failed transactions are being recovered.

# Key benefits

* **Protect Revenue** — Automatically identifies and recovers failed payments before they result in permanent revenue loss or customer churn.
* **Optimize Retry Strategy** — Pinpoints exactly where in the retry cycle recoveries are succeeding or falling off, enabling smarter scheduling and reduced unnecessary attempts.
* **Monitor Performance Trends** — Tracks period-over-period changes in recovery rates and transaction volumes, giving teams early warning signals when retry effectiveness declines.
* **Prioritize High-Impact Failures** — Surfaces the volume and value of at-risk revenue in one place, helping teams focus attention on the failures that matter most to the bottom line.

# Key details

## General Filters (Top Left Corner)

* **Date Range:** Adjust the time interval for your data to track and analyze long-term trends. The default view is typically 30 days.

* **Country:** See data specific to your country, offering relevant insights and comparisons.

* **Gateway:** This filter allows you to segment and analyze data based on available payment processors. You can look at all payment gateways together or examine one at a time to understand where issues are happening.

* **Payment method:** If you want to see the breakdown of failed payments by the method your customers use, this filter lets you select specific payment options to analyze.

* **Initiated by:** This filter allows you to select between CIT (customer initiated) or MIT (merchant initiated) transactions. CIT transactions typically requires more payment authentication.

* **Currency:** This filter allows filtering by the various currencies for your site's geo-location

## Recovered Transactions

The total number of failed payment transactions successfully recovered through the retry engine in the current period.

<Image align="center" border={true} src="https://files.readme.io/f8215ad29a6f6208acbc2701aebaf6ba85d31887d9e031996ab172b9d21e452f-image.png" className="border" />

## Payment Recovery Over Time

This chart tracks the daily volume of successfully recovered payment transactions in the time period.

<Image align="center" border={true} src="https://files.readme.io/8df9d7fb386a90744cff3db199099ea75660e0194a7bb7692e6442799630d3a2-image.png" className="border" />

## Revenue Recovered

* **Retry Attempts** - total number of failed payment transactions that entered the retry queue in the current period.
* **Revenue at Risk** - total dollar value of transactions that failed and required a retry attempt.
* **Recovered Revenue** - total revenue successfully recaptured through the retry engine.
* **Recovery Rate** - percentage of at-risk revenue that was successfully recovered.

<br />

<Image align="center" border={true} src="https://files.readme.io/d539d5806fa974c32b42e7c7b0f0b462867711780665abb6ec5493c259247331-image.png" className="border" />

## Success Rate by Retry Attempt

This chart shows the distribution of successful payment recoveries broken down by which retry attempt successfully processed the payment.

<Image align="center" border={true} src="https://files.readme.io/112efee63ab4631db531883741571cac48da8c81e3374b0d8629f45985580c3a-image.png" className="border" />
