---
title: Fraud prevention
excerpt: >-
  Monitor transaction blocking and fraud risk score trends. Track fraud
  protection effectiveness while balancing security with customer experience.
deprecated: false
hidden: false
metadata:
  title: Fraud Prevention
  robots: index
---
# Overview

### Required plan

This feature or setting is available to all customers on any Recurly subscription plan.

### Prerequisites

- Users must have analytics user role permission.
- Users must have Kount enabled on their Recurly site.

# Definition

The Fraud Prevention dashboard provides a comprehensive view of your Kount integration's performance, tracking key metrics such as blocked transactions, risk scores, and fraud patterns across payment methods and gateways. Together, these charts enable fraud and operations teams to monitor threats in real time, identify emerging risk trends early, and focus prevention efforts where they will have the greatest impact.

# Key benefits

- **Quantify Fraud Prevention at a Glance** - The Transactions Blocked KPI immediately communicates how actively the system is protecting your Recurly site. The period-over-period comparison lets stakeholders quickly assess whether fraud pressure is increasing or decreasing without needing a deep data dive.
- **Detect and Respond to Fraud Attacks in Real Time** - The Blocked Transactions Over Time chart makes sudden fraud spikes immediately visible. This allows fraud and ops teams to investigate and respond quickly, rather than discovering an attack after significant damage has already occurred.
- **Understand Escalating Risk Before It Becomes a Problem** - The Average Risk Score and its Over Time chart work together to provide an early warning system. A rising risk score trend often precedes a spike in blocked transactions, giving teams a window to tighten rules or thresholds proactively rather than reactively.
- **Target Fraud Prevention Efforts Where They Matter Most** -The Fraud by Payment Method breakdown shows that card-based payments (credit and debit combined) account for nearly 80% of fraud attempts. This helps teams prioritize where to add friction, strengthen authentication, or adjust risk rules for maximum impact.

# Key details

## General Filters (Top Left Corner)

- **Date Range:** Adjust the time interval for your data to track and analyze long-term trends. The default view is  30 days.

- **Country:** Filter data to one or more countries.

- **Gateway:** This filter allows you to isolate individual payment gateways.

- **Payment method:** This filter lets you drill down into fraud for a specific payment method.

- **Currency:** This filter allows filtering by the various currencies for your site's geo-location

## Transactions Blocked (Fraud)

The total number of transactions flagged and blocked as fraudulent in the selected period.

If this number is higher than you think it should be, or has spiked, there are a few options to consider:

- Your site may be under attack from a fraudster and Kount is working properly.
- You have updated a fraud rule in Kount recently that may be misbehaving. Speak to your Kount representative to review rules on blocked transactions that you believe to be false positives.


<Image src="https://files.readme.io/b5fff756ef3175909531dfc747c58471a1837253a0b15604962ce1792ceca132-image.png" align="center" border={true} />


## Blocked Transactions Over Time

This line chart tracks the daily count of fraud-blocked transactions in the time period.


<Image src="https://files.readme.io/f680c12887edb3f40f467bf19548b4ca3d655731ee1d93fe0003abe0e482880b-image.png" align="center" border={true} />


## Average Risk Score

The mean Kount risk score assigned to transactions in the selected period, along with comparison to the previous time period.


<Image src="https://files.readme.io/8c0173d36cf361d293b7c93b4fcb4e0254974106a97f735c1b445e1bd73650ab-image.png" align="center" border={true} />


## Average Risk Score Over Time

This line chart tracks the daily average Kount risk score in the time period. Use this chart to identify when risk levels begin rising so action can be taken before blocked transaction volume surges.


<Image src="https://files.readme.io/bb4fa2907dee107ab721ce5670bba48681c1c7d6dbdcdf7a84e2d8d4e2e1fb3a-image.png" align="center" border={true} />


## Fraud by Payment Method

This pie chart breaks down blocked fraud transactions by payment method.


<Image src="https://files.readme.io/209e7687a5c62bdb347d4293fe68568eef1344f3f562cf7e9367b7ba8b3820c0-image.png" align="center" border={true} />


## Blocked Transactions by Gateway

This bar chart shows the volume of fraud-blocked transactions by payment gateway.


<Image src="https://files.readme.io/e3edc529acadd48b9440084b0a9be5bc6b6167c4b89428766ba3c7e4766cbbbd-image.png" align="center" width="00px" border={true} />



<Image src="https://files.readme.io/6447de1fd5e69285189708a13155df282cb500ff2c57bdb22d044769b65f43a0-image.png" align="center" border={true} />


<br />
