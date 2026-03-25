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

...

# Key benefits

<br />

# Key details

## General Filters (Top Left Corner)

* **Date Range:** Adjust the time interval for your data to track and analyze long-term trends. The default view is typically 30 days.

* **Country:** See data specific to your country, offering relevant insights and comparisons.

* **Gateway:** This filter allows you to segment and analyze data based on available payment processors. You can look at all payment gateways together or examine one at a time to understand where issues are happening.

* **Payment method:** If you want to see the breakdown of failed payments by the method your customers use, this filter lets you select specific payment options to analyze.

* **Initiated by:** This filter allows you to select between CIT (customer initiated) or MIT (merchant initiated) transactions. CIT transactions typically requires more payment authentication.

* **Currency:** This filter allows filtering by the various currencies for your site's geo-location

## Recovered Transactions

The total number of failed payment transactions successfully recovered through the retry engine in the current period, standing at 2,380 — down 18% from 2,913 in the prior period. While the decline indicates fewer transactions are being recovered overall, this should be read in context alongside Retry Attempts, which fell by the same 18%, suggesting the drop is volume-driven rather than a deterioration in retry effectiveness.

<Image align="center" border={true} src="https://files.readme.io/f8215ad29a6f6208acbc2701aebaf6ba85d31887d9e031996ab172b9d21e452f-image.png" className="border" />

## Payment Recovery Over Time

This chart tracks the daily volume of successfully recovered payment transactions over the past month. The high volatility may reflect batch retry cycles, dunning schedule patterns, or underlying payment processor behavior worth investigating.

<Image align="center" border={true} src="https://files.readme.io/8df9d7fb386a90744cff3db199099ea75660e0194a7bb7692e6442799630d3a2-image.png" className="border" />

## Revenue Recovered

* **Retry Attempts** - total number of failed payment transactions that entered the retry queue in the current period. 
* **Revenue at Risk** - total dollar value of transactions that failed and required a retry attempt. The significant drop aligns with the reduction in retry attempts and may indicate fewer high-value transactions are failing.
* **Recovered Revenue** - total revenue successfully recaptured through the retry engine. 
* **Recovery Rate** - percentage of at-risk revenue that was successfully recovered. This is the most critical metric to monitor, as the dip indicates the retry strategy is recovering a smaller share of at-risk revenue and may warrant a review of retry logic, timing, or payment method fallback rules.

<br />

<Image align="center" border={true} src="https://files.readme.io/d539d5806fa974c32b42e7c7b0f0b462867711780665abb6ec5493c259247331-image.png" className="border" />

## Success Rate by Retry Attempt

This chart shows the distribution of successful payment recoveries broken down by which retry attempt closed the transaction. The pattern follows a steep power-law curve, with the vast majority of recoveries happening early in the retry cycle:

Attempt 2 dominates overwhelmingly at 2,100 successful transactions, accounting for the lion's share of all recovered payments — confirming that a single retry resolves most failures.
Recovery success drops sharply from there, with 127 successes on attempt 3, 49 on attempt 4, and quickly tapering to double and single digits by attempts 5 through 7.
Beyond attempt 7, recoveries become minimal (8 or fewer per attempt), with the retry engine continuing out to 14 attempts but yielding diminishing returns.

The steep drop-off after attempt 2 suggests that most failed payments are due to transient issues (e.g., temporary insufficient funds or network errors) that resolve quickly. The long tail of attempts 8–14 recovers very few transactions and may warrant a cost-benefit review — the marginal revenue recovered in later attempts should be weighed against customer experience impact and processing costs.

<Image align="center" border={true} src="https://files.readme.io/112efee63ab4631db531883741571cac48da8c81e3374b0d8629f45985580c3a-image.png" className="border" />

<br />
