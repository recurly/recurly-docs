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

* Users must have Analytics user role permission.

# Definition

The Subscribers Metrics section of Recurly's Reporting & Analytics offers a comprehensive set of reports and metrics to help you track and analyze subscriber counts and trends.

> **Note:** It's essential to note the distinction between a subscriber and a subscription. While a single subscriber might hold multiple active subscriptions, this dashboard focuses on counting the individual subscriber, not the number of subscriptions they possess.
>
> **For additional guidance on navigating and utilizing filter tools, consult our documentation<a href="https://docs.recurly.com/docs/recurly-analytics-overview#navigation-features" target="_blank">here</a>.**

# Subscribers

Recurly's Subscribers section within Reporting & Analytics delivers a robust set of reports and metrics, designed to give you a deep dive into subscriber patterns and behaviors. This section illuminates key aspects of subscription signups, churn rates, and overall subscriber growth, empowering businesses to strategize based on actionable data. 

> **Note:** It's essential to note the distinction between a subscriber and a subscription. While a single subscriber might hold multiple active subscriptions, this dashboard focuses on counting the individual subscriber, not the number of subscriptions they possess.

## Subscribers Dashboard

<Image align="center" width="75% " src="https://files.readme.io/cf67f1c-image.png" />

### Utilizing the subscribers dashboard

To make the most of the Subscribers dashboard and gain comprehensive insights into your subscriber data, follow these steps:

1. Navigate to the "Subscriber management" section in the Reporting & Analytics menu. This section provides a comprehensive overview of subscriber-related metrics and reports.
2. Within that menu, access the “Subscribers” dashboard.
3. Once you access the dashboard, leverage the "Combine Subscriptions" functionality, which is activated by default. By setting the appropriate interval, subscriptions that start immediately after the expiration of a previous subscription will be counted as a single continuous subscription. This helps provide a more accurate representation of activations and churn.

<Image align="center" width="75% " src="https://files.readme.io/e95cc2c-image.png" />

The way these subscriptions are combined can vary based on the selected gap in the 'combine subscriptions' setting. By adjusting this gap, subscriptions can be further combined.

4. Explore the "Active Subscribers" table. This table provides valuable information about the total number of active subscribers on your platform. It helps you understand the growth and composition of your subscriber base. Additionally, you can pair this table with the "Subscriber Growth" table to gain insights into the breakdown of your active subscriber growth. By comparing the number of activated subscribers to the number of churned subscribers, you can determine the net count and identify trends in your subscriber base.

<Image align="center" width="75% " src="https://files.readme.io/5f5e35d-image.png" />

If you click on any bar, you can drill down into the specific accounts that make up each bar.

<Image align="center" width="75% " src="https://files.readme.io/02f6852-image.png" />

<Image align="center" width="75% " src="https://files.readme.io/2d39eb7-image.png" />

**Drills**

<Table>
  <thead>
    <tr>
      <th>
        Id
      </th>

      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        **Account Code**
      </td>

      <td>
        A link to the specific account page in the Recurly App upon clicking.  

        ![](https://files.readme.io/bed96f6-image.png)
      </td>
    </tr>

    <tr>
      <td>
        **Email**
      </td>

      <td>
        The email address associated with the account.
      </td>
    </tr>

    <tr>
      <td>
        **State (location)**
      </td>

      <td>
        The state location of the account holder.
      </td>
    </tr>

    <tr>
      <td>
        **Country**
      </td>

      <td>
        The country of the account holder.
      </td>
    </tr>

    <tr>
      <td>
        **Activation Date**
      </td>

      <td>
        The date the account was activated.
      </td>
    </tr>

    <tr>
      <td>
        **Expires Date**
      </td>

      <td>
        The expiration date of the account, null if still active.
      </td>
    </tr>

    <tr>
      <td>
        **Plan Name**
      </td>

      <td>
        The name of the plan subscribed to.
      </td>
    </tr>

    <tr>
      <td>
        **Plan Code**
      </td>

      <td>
        The code representing the plan subscribed to.
      </td>
    </tr>

    <tr>
      <td>
        **Activation Count**
      </td>

      <td>
        The number of times the account has been activated.
      </td>
    </tr>

    <tr>
      <td>
        **Churn Count**
      </td>

      <td>
        The number of times the account has churned.
      </td>
    </tr>

    <tr>
      <td>
        **Net Count**
      </td>

      <td>
        The net count of activations and churns.
      </td>
    </tr>

    <tr>
      <td>
        **End of Period Count**
      </td>

      <td>
        The count of accounts at the end of a specified period.
      </td>
    </tr>
  </tbody>
</Table>

Each field provides particular information regarding the account, its status, and subscription details which could be crucial for tracking and managing customer accounts efficiently.

5. Following up, we have the 'Subscriber Growth Section'. It closely mirrors the default 'Subscriber Growth' section, but with two key distinctions:
   1. The categories 'New' and 'Returning' are merged into a single group labeled “Activated Subscribers”.
   2. Every bar and number can be clicked on, revealing a breakdown of the specific accounts represented by each figure."\
      ![](https://files.readme.io/14fbb57-image.png)\
      ![](https://files.readme.io/0a10663-image.png)

6. Take advantage of the interactive features, such as filters and data drill-downs, to further explore and analyze specific aspects of subscriber metrics within the worksheet. This flexibility allows you to tailor the analysis to your specific needs and focus on the most relevant data points.
