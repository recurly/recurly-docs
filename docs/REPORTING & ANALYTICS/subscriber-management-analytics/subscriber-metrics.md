---
title: Subscribers (Legacy)
excerpt: >-
  Dive deep into Recurly's Subscribers analytics for a comprehensive view of
  subscriber behaviors, trends, and growth patterns.
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

- Users must have Analytics user role permission.

# Definition

The Subscribers Metrics section of Recurly's Reporting & Analytics offers a comprehensive set of reports and metrics to help you track and analyze subscriber counts and trends.

> **Note:** It's essential to note the distinction between a subscriber and a subscription. While a single subscriber might hold multiple active subscriptions, this dashboard focuses on counting the individual subscriber, not the number of subscriptions they possess.
>
> **For additional guidance on navigating and utilizing filter tools, consult our documentation <a href="https://docs.recurly.com/docs/recurly-analytics-overview#navigation-features" target="_blank">here</a>.**

# Subscribers

Recurly's Subscribers section within Reporting & Analytics delivers a robust set of reports and metrics, designed to give you a deep dive into subscriber patterns and behaviors. This section illuminates key aspects of subscription signups, churn rates, and overall subscriber growth, empowering businesses to strategize based on actionable data. 

> **Note:** It's essential to note the distinction between a subscriber and a subscription. While a single subscriber might hold multiple active subscriptions, this dashboard focuses on counting the individual subscriber, not the number of subscriptions they possess.

## Subscribers Dashboard

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/cf67f1c-image.png",
        null,
        ""
      ],
      "align": "center",
      "sizing": "75% "
    }
  ]
}
[/block]


### Utilizing the subscribers dashboard

To make the most of the Subscribers dashboard and gain comprehensive insights into your subscriber data, follow these steps:

1. Navigate to the "Subscriber management" section in the Reporting & Analytics menu. This section provides a comprehensive overview of subscriber-related metrics and reports.
2. Within that menu, access the “Subscribers” dashboard.
3. Once you access the dashboard, leverage the "Combine Subscriptions" functionality, which is activated by default. By setting the appropriate interval, subscriptions that start immediately after the expiration of a previous subscription will be counted as a single continuous subscription. This helps provide a more accurate representation of activations and churn.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e95cc2c-image.png",
        null,
        ""
      ],
      "align": "center",
      "sizing": "75% "
    }
  ]
}
[/block]


The way these subscriptions are combined can vary based on the selected gap in the 'combine subscriptions' setting. By adjusting this gap, subscriptions can be further combined.

4. Explore the "Active Subscribers" table. This table provides valuable information about the total number of active subscribers on your platform. It helps you understand the growth and composition of your subscriber base. Additionally, you can pair this table with the "Subscriber Growth" table to gain insights into the breakdown of your active subscriber growth. By comparing the number of activated subscribers to the number of churned subscribers, you can determine the net count and identify trends in your subscriber base.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5f5e35d-image.png",
        null,
        ""
      ],
      "align": "center",
      "sizing": "75% "
    }
  ]
}
[/block]


If you click on any bar, you can drill down into the specific accounts that make up each bar.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/02f6852-image.png",
        null,
        ""
      ],
      "align": "center",
      "sizing": "75% "
    }
  ]
}
[/block]


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2d39eb7-image.png",
        null,
        ""
      ],
      "align": "center",
      "sizing": "75% "
    }
  ]
}
[/block]


**Drills**

[block:parameters]
{
  "data": {
    "h-0": "Id",
    "h-1": "Description",
    "0-0": "**Account Code**",
    "0-1": "A link to the specific account page in the Recurly App upon clicking.  \n  \n![](https://files.readme.io/bed96f6-image.png)",
    "1-0": "**Email**",
    "1-1": "The email address associated with the account.",
    "2-0": "**State (location)**",
    "2-1": "The state location of the account holder.",
    "3-0": "**Country**",
    "3-1": "The country of the account holder.",
    "4-0": "**Activation Date**",
    "4-1": "The date the account was activated.",
    "5-0": "**Expires Date**",
    "5-1": "The expiration date of the account, null if still active.",
    "6-0": "**Plan Name**",
    "6-1": "The name of the plan subscribed to.",
    "7-0": "**Plan Code**",
    "7-1": "The code representing the plan subscribed to.",
    "8-0": "**Activation Count**",
    "8-1": "The number of times the account has been activated.",
    "9-0": "**Churn Count**",
    "9-1": "The number of times the account has churned.",
    "10-0": "**Net Count**",
    "10-1": "The net count of activations and churns.",
    "11-0": "**End of Period Count**",
    "11-1": "The count of accounts at the end of a specified period."
  },
  "cols": 2,
  "rows": 12,
  "align": [
    null,
    null
  ]
}
[/block]


Each field provides particular information regarding the account, its status, and subscription details which could be crucial for tracking and managing customer accounts efficiently.

5. Following up, we have the 'Subscriber Growth Section'. It closely mirrors the default 'Subscriber Growth' section, but with two key distinctions:
   1. The categories 'New' and 'Returning' are merged into a single group labeled “Activated Subscribers”.
   2. Every bar and number can be clicked on, revealing a breakdown of the specific accounts represented by each figure."  
      ![](https://files.readme.io/14fbb57-image.png)  
      ![](https://files.readme.io/0a10663-image.png)

6. Take advantage of the interactive features, such as filters and data drill-downs, to further explore and analyze specific aspects of subscriber metrics within the worksheet. This flexibility allows you to tailor the analysis to your specific needs and focus on the most relevant data points.