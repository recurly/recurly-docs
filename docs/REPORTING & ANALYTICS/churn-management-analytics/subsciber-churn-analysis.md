---
title: Subscriber churn analysis
excerpt: >-
  Discover key insights on customer retention with our Churn Analysis dashboard.
  Identify churn reasons, analyze trends, and devise effective strategies to
  minimize subscription loss and maximize growth.
deprecated: false
hidden: false
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

- Users must have analytics user role permission.

# Definition

The Subscriber Churn Analysis dashboard is an insightful tool that monitors subscription losses over a specified timeframe, broken down by voluntary and involuntary reasons. Uncover why your subscribers are leaving and identify strategies to mitigate churn and increase customer retention.

# Key benefits

- **Industry comparison**: Compare key subscription metrics with industry benchmarks to understand performance relative to peers, identifying areas of strengths and weaknesses. 

- **Competitive insights**: Gain insights into how competitors are faring in terms of subscription metrics, uncovering areas to differentiate and improve to gain a competitive edge.

- **Informed decision-making**: Make informed decisions based on real-world data to help set realistic goals and expectations for subscription growth and customer retention.

- **Forecasting and planning**: Enable more accurate forecasting and long-term planning to help businesses set reachable growth targets and allocate resources effectively.

# Key details

> **Note:** It's important to understand the difference between a subscriber and a subscription. A single subscriber may have several active subscriptions, but this dashboard's focus is on counting each subscriber as one entity, rather than tallying the total subscriptions they may hold.
>
> **For more information on how to navigate and make the most of the filter tools available, please refer to our documentation [here](https://docs.recurly.com/docs/recurly-analytics-overview#navigation-features).**

## Filters (Top left corner)

- **Date Range:** Utilize dropdown menus to select a specific timeframe and date range for the data displayed on the dashboard.
- **Timeframe:** Adjust this to view data over different periods for a more detailed or broader overview.
- **Subscriber Type:** This filter lets you categorize the data by the type of subscriber, whether they are paying, non-paying, or in a trial phase.

## Churn rates

The subscriber churn benchmarks dashboard is a powerful tool for evaluating the success of your customer retention strategies. By presenting your churn rates clearly, it helps you identify both the strengths and weaknesses of your current approach. Understanding these metrics is crucial for refining your tactics and enhancing subscriber retention effectively.

**Churn Rates**

Churn rates are calculated by dividing the number of subscribers lost during a specified time period by the total number of subscribers at the beginning of that period.

There are three key churn rates to consider:

1. **Overall Churn:** This metric aggregates both involuntary and voluntary churn, providing a comprehensive view of total subscriber loss.
2. **Involuntary Churn:** This benchmark focuses on subscribers lost due to payment issues, helping you understand the effectiveness of your payment recovery efforts.
3. **Voluntary Churn:** This measures the rate at which subscribers choose to leave of their own accord, offering insights into subscriber satisfaction and the value they perceive from your service.

## Involuntary churn reasons

- **Non-payment:** Subscription churned due to failed transaction and unrecovered invoice.
- **Invalid tax location:** Subscription churned due to failed a tax validation check.
- **Non-payment gift:** Subscription churned because gift subscription ended without converting to a paid subscription.
- **Non-payment trial:** Subscription churned because a trail ended without converting to a paid subscription.

## Voluntary churn reasons

- **Non-renewing:** Subscription expired after a fixed number of billing cycles and was not renewed.
- **Account closed:** The subscription churned because its linked account was manually closed.
- **Canceled:** Customer-initiated cancellation.
- **Trial ended:** Cardless free trial ended without billing information added.
- **Gift ended:** The gift card amount exhausted without adding billing info before the next renewal.

# Churn rate

View your performance for all your churn rates (overall, involuntary, voluntary) at a single glance to see how the breakdown changes over time. This will allow you to know if there are important changes in the effectiveness of your retention tactics. You can also view your overall churn rate compared to the previous year. 

Dive into the breakdown of involuntary vs voluntary to gain additional details.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ff5e5bf-Screen_Shot_2024-04-15_at_4.11.57_PM.png",
        null,
        null
      ],
      "align": "center",
      "sizing": "80% ",
      "border": true
    }
  ]
}
[/block]


## Involuntary churn

Understand the rate of involuntary churn due to non payment, comparing specific involuntary churn reasons and the year over year trend.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/200c5ee-Screen_Shot_2024-04-15_at_4.12.13_PM.png",
        null,
        null
      ],
      "align": "center",
      "sizing": "80% ",
      "border": true
    }
  ]
}
[/block]


## Voluntary churn

Understand the rate of voluntary churn, comparing specific involuntary churn reasons and the year over year trend.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/49b9c55-Screen_Shot_2024-04-15_at_4.12.23_PM.png",
        null,
        null
      ],
      "align": "center",
      "sizing": "80% ",
      "border": true
    }
  ]
}
[/block]


## Churn reasons

Dive into the data to understand the specifics across all churn reasons.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/282a130-Screen_Shot_2024-04-15_at_4.13.05_PM.png",
        null,
        null
      ],
      "align": "center",
      "sizing": "80% ",
      "border": true
    }
  ]
}
[/block]


<br>