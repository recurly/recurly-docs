---
title: Account Updater
excerpt: >-
  Tracks retained revenue through automated card updates. Monitor how the
  Account Updater service prevents payment failures by keeping payment methods
  current.
deprecated: false
hidden: true
metadata:
  title: Account Updater
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

* **Measure Revenue Protection** - The "Payments Authorized on Updated Cards" metric directly quantifies how much revenue was saved from potential failed transactions. At $632,368 in the example, it makes the ROI of Account Updater immediately visible to stakeholders.
* **Catch Problems Early** - The two time-series charts (Updates Over Time and Payments Over Time) let you spot sudden drops in activity before they compound into significant revenue loss. A dip in updates that isn't addressed quickly can cascade into failed payments days or weeks later.
* **Benchmark Performance Period-Over-Period** - The KPI tiles for both Successful Card Updates and Payments Authorized include comparison values and percentage changes against the prior period, making it easy to assess whether the service is trending in the right direction without digging into raw data.
* **Prioritize Outreach and Card Management** - The Update Type breakdown tells you whether customers are primarily getting new card numbers or just new expiration dates — useful for anticipating how disruptive card changes will be to your payment flows, since full number changes carry more risk of payment failure.
* **Optimize Network Relationships** - The Updates by Card Type chart reveals which card networks are driving the most update activity. If a network like Discover shows near-zero updates, it may signal a gap in your Account Updater enrollment or coverage worth investigating with your payment processor.

# Key details

## General Filters (Top Left Corner)

* **Date Range:** Adjust the time interval for your data to track and analyze long-term trends. The default view is typically 30 days.

* **Card type:** This filter allows filtering by credit card type.

## Successful Card Updates

The total number of cards successfully updated in the selected period. The current value of 254 represents a 21% decrease compared to the previous period (322), indicating a decline in update volume that may warrant investigation.

<Image align="center" border={true} src="https://files.readme.io/72e147d58271c121c8f9397658dd1a5bd68aa1ab6e74c33ab88bad002d5c8103-image.png" className="border" />

## Successful Card Updates Over Time

This line chart plots the daily count of successful card updates from February 20 through March 20. Update volume fluctuates day-to-day, generally ranging between 5 and 15 updates per day, with a notable peak around March 4 and another around March 8. Use this chart to identify spikes or dips that correlate with card reissuance events, processing issues, or changes in your customer base.

<Image align="center" border={true} src="https://files.readme.io/fa245ce7fda681233578742b6870751c33ebd9d2ac09f5a33f5feb1cdaa20bc2-image.png" className="border" />

## Payments Authorized on Updated Cards

The total value of payments successfully authorized on cards that were updated through Account Updater in the selected period. The current value of $632,368 is nearly flat compared to the previous period ($633,342), reflecting a 0% change — indicating stable revenue recovery despite the drop in raw update volume seen above.

<Image align="center" border={true} src="https://files.readme.io/87d8de2d2b81c54a13d0b39ccb0cfe29e6eaa87f1cb7606aaa5b4a9267fbb883-image.png" className="border" />

## Successful Payments Over Time

This bar chart shows the daily transaction value (in currency totals) of successful payments made on updated cards from February 20 through March 20. Most days fall in the $10,000–$40,000 range, with notable peaks around February 21, February 28–March 1, and March 12 and March 19. A few days, particularly around March 7–8 and March 14, show significantly lower volume. Use this chart to identify high- and low-revenue days and correlate payment performance with update activity.

<Image align="center" src="https://files.readme.io/2cb267bc927ab22ae454d3953f31c524614c0abef46c90f97ab5defc0c7e41f4-image.png" />

## Update Type

This pie chart breaks down successful card updates by the type of change applied. The majority — 61% — were card number updates, where the account number itself changed (typically due to card reissuance). The remaining 39% were expiration date updates only. This split helps you understand how often your customers are receiving entirely new card numbers versus simple renewals.

<Image align="center" border={true} width="500px" src="https://files.readme.io/f1c86c68b2acdeff9e4aa5faafb82d05a8e405765c158eeca18c5cd4a3dbd167-image.png" className="border" />

## Updates by Card Type

This bar chart shows the distribution of successful card updates across card networks. Mastercard leads with the highest update volume (approximately 85), followed closely by Visa (approximately 80). Amex accounts for a moderate share (approximately 65), while Discover has minimal activity (near 0). Use this breakdown to understand which networks contribute most to your Account Updater coverage and whether your customer card mix aligns with expected update patterns.

<Image align="center" border={true} width="500px" src="https://files.readme.io/4b15e4dd5639b40728f7cf6584391bd945ec4f9c9402ee36772edf0bed5cd87a-image.png" className="border" />
