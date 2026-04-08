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
* Site must have Account Updater enabled.

# Definition

The Account Updater dashboard gives a real-time view of card update activity across your payment ecosystem, combining pending, at risk, and rescued cards into a single unified view. This enables payments teams to quickly detect emerging risks to subscriptions, understand where card updates and lack-there-of are most concentrated, and take proactive action before it impacts revenue or customers.

# Key benefits

* **Measure Revenue Protection** - The "Payments Authorized on Updated Cards" metric directly quantifies how much revenue was saved by processing successfully on updated cards.
* **Catch Problems Early** - The two time-series charts (Updates Over Time and Payments Over Time) let you spot sudden drops in activity before they compound into significant revenue loss. A dip in updates that isn't addressed quickly can cascade into failed payments days or weeks later.
* **Benchmark Performance Period-Over-Period** - The KPI tiles for both Successful Card Updates and Payments Authorized include comparison values and percentage changes against the prior period, making it easy to assess whether the service is trending in the right direction without digging into raw data.
* **Prioritize Outreach and Card Management** - The Update Type breakdown tells you whether customers are primarily getting new card numbers or just new expiration dates — useful for anticipating how disruptive card changes will be to your payment flows, since full number changes carry more risk of payment failure.
* **Optimize Network Relationships** - The Updates by Card Type chart reveals which card networks are driving the most update activity. If a particular card scheme like Discover shows near-zero updates, it may signal a gap in your Account Updater enrollment or coverage worth investigating with your payment processor.

# Key details

## General Filters (Top Left Corner)

* **Date Range:** Adjust the time interval for your data to track and analyze long-term trends. The default view is typically 30 days.

* **Card type:** This filter allows filtering by credit card type.

## Successful Card Updates

The total number of cards successfully updated in the selected period. The current value of 254 represents a 21% decrease compared to the previous period (322), indicating a decline in update volume that may warrant investigation.

<Image align="center" border={true} src="https://files.readme.io/72e147d58271c121c8f9397658dd1a5bd68aa1ab6e74c33ab88bad002d5c8103-image.png" className="border" />

## Successful Card Updates Over Time

This line chart plots the daily count of successful card updates in the time period.

<Image align="center" border={true} src="https://files.readme.io/fa245ce7fda681233578742b6870751c33ebd9d2ac09f5a33f5feb1cdaa20bc2-image.png" className="border" />

## Payments Authorized on Updated Cards

The total value of payments successfully authorized on cards that were updated through Account Updater in the time period, with a comparison to the previous time period.

<Image align="center" border={true} src="https://files.readme.io/87d8de2d2b81c54a13d0b39ccb0cfe29e6eaa87f1cb7606aaa5b4a9267fbb883-image.png" className="border" />

## Successful Payments Over Time

This bar chart shows the transaction volume of successful payments made on updated cards in the time period.

<Image align="center" src="https://files.readme.io/2cb267bc927ab22ae454d3953f31c524614c0abef46c90f97ab5defc0c7e41f4-image.png" />

## Update Type

This pie chart breaks down the successful counts of card number vs card expiration date updates.

<Image align="center" border={true} width="500px" src="https://files.readme.io/f1c86c68b2acdeff9e4aa5faafb82d05a8e405765c158eeca18c5cd4a3dbd167-image.png" className="border" />

## Updates by Card Type

This bar chart shows the distribution of successful card updates across card networks.

<Image align="center" border={true} width="500px" src="https://files.readme.io/4b15e4dd5639b40728f7cf6584391bd945ec4f9c9402ee36772edf0bed5cd87a-image.png" className="border" />
