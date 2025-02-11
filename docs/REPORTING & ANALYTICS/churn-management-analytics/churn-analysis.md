---
title: Churn analysis (legacy)
excerpt: >-
  Discover key insights on customer retention with our Churn Analysis dashboard.
  Identify churn reasons, analyze trends, and devise effective strategies to
  minimize subscription loss and maximize growth.
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Overview

### Required plan

This feature or setting is available to all customers on any Recurly subscription plan.

### Prerequisites

* Users must have Analytics user role permission.

# Definition

The Churn Analysis dashboard is an insightful tool that monitors subscription losses over a specified timeframe, broken down by voluntary and involuntary reasons. Uncover why your subscribers are leaving and identify strategies to mitigate churn and increase customer retention.

Voluntary versus involuntary churn is about whether the customer chooses to quit the service. Voluntary churn measures how often a customer cancels their monthly or annual subscription on purpose. Involuntary churn is when the customer doesn't choose a subscription cancellation, but instead it happens from any other factor.

> **Note:** It's essential to note the distinction between a subscriber and a subscription. While a single subscriber might hold multiple active subscriptions, this dashboard focuses on counting the individual subscriber, not the number of subscriptions they possess.
>
> **For additional guidance on navigating and utilizing filter tools, consult our documentation<a href="https://docs.recurly.com/docs/recurly-analytics-overview#navigation-features" target="_blank">here</a>.**

> 📘 Drills
>
> Drills are available in the Subscription Churn Reasons, Subscription Churn Reasons (%), and Churn Analysis Widgets:
>
> 1. Account code
> 2. First name
> 3. Last name
> 4. Email
> 5. Activated Date
> 6. Expiration Date
> 7. Expiration Reason
> 8. Churn Count

# Churn analysis dashboards

## Voluntary vs. involuntary churn rate

<Image title="Vol vs invol churn analysis.png" alt={2604} align="center" src="https://files.readme.io/7d9e199-Vol_vs_invol_churn_analysis.png">
  Churn Analysis Voluntary vs Involuntary Rate
</Image>

This line chart tracks the number of active subscriptions that have churned over a selected time frame. It separates these totals by churn reason, either voluntary or involuntary, helping you to identify patterns and gain a deeper understanding of why customers are leaving. This information can assist in developing tailored strategies for customer retention. This line chart captures the churn rate of active subscriptions over a selected period, split by voluntary or involuntary reasons.

**Voluntary Churn Reasons**

* **Non-renewing:** Subscription expired after a fixed number of billing cycles and was not renewed.
* **Account closed:** The subscription churned because its linked account was manually closed.
* **Canceled:** Customer-initiated cancellation.
* **Trial Ended:** Cardless free trial ended without billing information added.
* **Gift Ended:** The gift card amount exhausted without adding billing info before the next renewal.

**Involuntary Churn Reasons**

* **Non-payment:** Subscription churned due to failed transaction and unrecovered invoice.
* **Invalid Tax location:** Subscription churned due to failed EU or NZ GST tax validation check.

### Subscription churn reasons

<Image title="subscription churn reason.png" alt={1290} align="center" width="60% " src="https://files.readme.io/f5c0506-subscription_churn_reason.png">
  Subscription Churn Reasons
</Image>

This color-coded bar chart visually represents the reasons for subscription churn over a designated time frame. It allows for quick and easy comparisons and trends spotting. Click on any data point to drill down into the specific accounts related to each churn reason. This can offer critical insights into individual account behaviors and highlight potential areas for intervention or improvement.

### Subscription churn reasons %

<Image title="subscription churn reasons %.png" alt={1288} align="center" width="60% " src="https://files.readme.io/f1b892c-subscription_churn_reasons_.png">
  Churn Reasons by Percentages
</Image>

This is another bar chart that shows the total churn, but each reason is represented as a percentage. This provides a relative comparison, highlighting which reasons are having the most impact on your overall churn. By identifying the most prominent causes of churn, you can prioritize your efforts and allocate resources effectively.

**Active subscriptions:** This includes any subscription that has not expired, giving you a clear view of your potential revenue sources. For monthly/weekly intervals, this value represents the total number of subscriptions at the start of the month or week, helping you track the health of your subscription base over time.

**% Churn:** This key metric is calculated as the total subscriptions churned over the selected interval divided by total active subscriptions at the beginning of the interval. It offers a quick overview of your business's health and can serve as an indicator of customer satisfaction and the effectiveness of your retention strategies.

### Churn analysis detail

<Image title="churn analysis detail.png" alt={2608} align="center" width="70% " src="https://files.readme.io/68883ec-churn_analysis_detail.png">
  Churn Analysis Detail
</Image>

This section provides a detailed breakdown of churn rates, categorized by reasons for active subscribers. Clicking on any non-percentage value lets you delve into the specifics, aiding in pinpointing problematic accounts and taking appropriate action.

# Churn analysis workflow

## Understanding churn rates

1. Under the Churn Analysis section, locate the Voluntary vs Involuntary Churn Rate line chart.
2. Review the chart to understand the number of active subscriptions that have churned during the selected time frame, split by voluntary or involuntary reasons.
3. This chart allows you to identify trends and patterns, informing your customer retention strategy.

## Classifying churn reasons

1. Review the listed reasons for both voluntary and involuntary churn. These reasons provide insights into why subscribers might be leaving.
2. Understanding these reasons can guide intervention strategies to improve the user experience and reduce churn.

## Analyzing subscription churn reasons

1. View the Subscription Churn Reasons bar chart. This color-coded chart visually represents the reasons for subscription churn over a designated time frame.
2. Click on any data point on the bar chart to drill down and view the specific accounts that correspond to each churn reason.

## Reviewing churn percentage

1. View the Subscription Churn Reasons % bar chart. This graph shows the total churn, but with each reason represented as a percentage.
2. This feature helps identify the most significant churn factors, enabling you to prioritize and address these issues strategically.

## Monitoring active subscriptions

1. Keep track of all active subscriptions, including those that are in trial, canceled, or paused. This helps provide a clear view of your potential revenue sources.

## Calculating churn percentage

1. Understand the % Churn figure, which is calculated as the total subscriptions churned over the selected interval divided by total active subscriptions at the beginning of the interval. This key metric serves as an indicator of customer satisfaction and the effectiveness of your retention strategies.

## Detailed churn analysis

1. Check out the Churn Analysis Detail section for a more comprehensive understanding of churn rates among active subscribers.
2. Click on any non-percentage value to drill down and view the specific accounts that correspond to each churn reason. This helps to pinpoint problematic accounts and devise suitable intervention strategies.
