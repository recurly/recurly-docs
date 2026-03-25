---
title: Fraud Prevention
excerpt: >-
  Monitor blocked transaction count, blocked volume, and risk scores. Track
  fraud protection effectiveness while balancing security with customer
  experience.
deprecated: false
hidden: true
metadata:
  title: Fraud Prevention
  robots: index
---
# Overview

### Required plan

This feature or setting is available to all customers on any Recurly subscription plan.

### Prerequisites

* Users must have analytics user role permission.

# Definition

The Fraud Prevention dashboard provides a comprehensive view of your Kount integration's performance, tracking key metrics such as blocked transactions, risk scores, and fraud patterns across payment methods and gateways. Together, these charts enable fraud and operations teams to monitor threats in real time, identify emerging risk trends early, and focus prevention efforts where they will have the greatest impact.

# Key benefits

* **Quantify Fraud Prevention at a Glance** - The Transactions Blocked KPI immediately communicates how actively the system is protecting the business. The period-over-period comparison lets stakeholders quickly assess whether fraud pressure is increasing or decreasing without needing a deep data dive.
* **Detect and Respond to Fraud Attacks in Real Time** - The Blocked Transactions Over Time chart makes sudden fraud spikes immediately visible. This allows fraud and ops teams to investigate and respond quickly, rather than discovering an attack after significant damage has already occurred.
* **Understand Escalating Risk Before It Becomes a Problem** - The Average Risk Score and its Over Time chart work together to provide an early warning system. A rising risk score trend often precedes a spike in blocked transactions, giving teams a window to tighten rules or thresholds proactively rather than reactively.
* **Target Fraud Prevention Efforts Where They Matter Most** -The Fraud by Payment Method breakdown shows that card-based payments (credit and debit combined) account for nearly 80% of fraud attempts. This helps teams prioritize where to add friction, strengthen authentication, or adjust risk rules for maximum impact.

# Key details

## General Filters (Top Left Corner)

* **Date Range:** Adjust the time interval for your data to track and analyze long-term trends. The default view is typically 30 days.

* **Country:** See data specific to your country, offering relevant insights and comparisons.

* **Gateway:** This filter allows you to segment and analyze data based on available payment processors. You can look at all payment gateways together or examine one at a time to understand where issues are happening.

* **Payment method:** If you want to see the breakdown of failed payments by the method your customers use, this filter lets you select specific payment options to analyze.

* **Initiated by:** This filter allows you to select between CIT (customer initiated) or MIT (merchant initiated) transactions. CIT transactions typically requires more payment authentication.

* **Currency:** This filter allows filtering by the various currencies for your site's geo-location

## Transactions Blocked (Fraud)

The total number of transactions flagged and blocked as fraudulent in the selected period. The current value of 4,381 represents a 7% decrease compared to the previous period (4,691), suggesting either a reduction in fraud attempts or a shift in risk threshold settings. Monitor this alongside your Average Risk Score to distinguish between the two.

If this number is higher than you think it should be, or has spiked, there are a few options to consider: 

* Your site may be under attack from a fraudster and Kount is working properly. Takes steps to protect your site if necessary. You may also set up a Kount rule, or a rule within your own infrastructure to block the fraudster directly.
* You have updated a fraud rule in Kount recently that may be misbehaving. Speak to your Kount representative to review rules on blocked transactions that you believe to be false positives.

<Image align="center" border={true} width="200px" src="https://files.readme.io/12e171c5ea1c29c58340c9a23068168a81c46867ccad9b130e4cc29eedd91199-image.png" className="border" />

## Blocked Transactions Over Time

This line chart tracks the daily count of fraud-blocked transactions. Volume remains relatively steady between 100–250 blocks per day for most of the period, before a dramatic spike around March 19–20, peaking near 750 blocked transactions in a single day. This sharp surge likely indicates a coordinated fraud attack or bot activity, followed by a quick return toward normal levels. Use this chart to detect and investigate fraud events in real time.

<Image align="center" border={true} width="-100% " src="https://files.readme.io/4b022444681539b49aad0fb8e5e256344bb5f7988b47cab7398ee68d8d5b981c-image.png" className="border" />

## Average Risk Score

The mean Kount risk score assigned to transactions in the selected period. The current score of 73.395 represents a 24% increase compared to the previous period (59.215), signaling that transactions are being evaluated as meaningfully less risky on average. A dropping risk score — especially paired with the spike seen in the blocked transactions chart — may indicate an ongoing or escalating fraud pattern that warrants closer review of your risk thresholds and blocking rules.

<Image align="center" border={true} width="150px" src="https://files.readme.io/ce38e193b698996c3abb9501d90b465ebcf63d5747dbb3ac4bb1ecd816eb4195-image.png" className="border" />

## Average Risk Score Over Time

This line chart tracks the daily average Kount risk score from March 2 through March 25. Scores fluctuate in a generally stable range early in the period, with a notable dip around March 6–7, before trending steadily downward through March 20–25. The consistent decrease toward the end of the period aligns with the increase in blocked transactions seen in the previous chart, reinforcing that fraud pressure was intensifying during that window. Use this chart to identify when risk levels begin dropping so action can be taken before blocked transaction volume surges.

<Image align="center" border={true} src="https://files.readme.io/b36b5bd58d7c5e53689b3e4498d4669e9f07a77db679195bd12ae6916fedaa39-image.png" className="border" />

## Fraud by Payment Method

This pie chart breaks down blocked fraud transactions by payment method. Credit Card dominates at 40.4%, followed by Debit Card at 38.8%, making card-based payments responsible for nearly 80% of all fraud attempts. Apple Pay accounts for 13.5%, with Prepaid Card and Google Pay making up the remaining small shares at roughly 1–2% each. This distribution highlights where fraud prevention efforts and friction controls should be most heavily focused.

<Image align="center" border={true} width="500px" src="https://files.readme.io/7eb8447753999a4abb5246b966990ff9bb34ef70e0588d29b340a867fcafa20e-image.png" className="border" />

## Blocked Transactions by Gateway

This bar chart shows the volume of fraud-blocked transactions by payment gateway. Ayym accounts for the overwhelming majority with approximately 5,000 blocked transactions, dwarfing the other gateways. Unknown Gateway and First Data each account for a small fraction at roughly 260–280 blocks apiece. This concentration suggests that either the bulk of transaction volume flows through Ayym, or that it may warrant a closer review of its fraud exposure relative to the other gateways.

<Image align="center" border={true} width="00px" src="https://files.readme.io/e3edc529acadd48b9440084b0a9be5bc6b6167c4b89428766ba3c7e4766cbbbd-image.png" className="border" />

<Image align="center" border={true} width="500px" src="https://files.readme.io/27c87c3fc9df44d2cf29c63d753ba730ac40ebc7fb19119bd655623b6e0e732d-image.png" className="border" />

<br />
