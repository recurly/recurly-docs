---
title: LTV by plan
excerpt: >-
  Unlock the monetary potential of long-term customer relationships with 'Plan
  Performance LTV'. Delve into the true value each customer brings over time.
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

'Plan Performance LTV' offers an in-depth analysis of the Lifetime Value (LTV) associated with your customers. By assessing the fiscal dimension of customer relationships, this view highlights the average projected revenue a customer is expected to contribute throughout their tenure. With two primary segments - 'Subscription Lifetime Value' and 'Average LTV' - users can discern both holistic and granular perspectives on the economic significance of sustained customer associations.

> **Note:** It's essential to note the distinction between a subscriber and a subscription. While a single subscriber might hold multiple active subscriptions, this dashboard focuses on counting the individual subscriber, not the number of subscriptions they possess.
>
> **Note**: Data only includes plans that have had at least 1 subscriber.
>
> **For additional guidance on navigating and utilizing filter tools, consult our documentation<a href="https://docs.recurly.com/docs/recurly-analytics-overview#navigation-features" target="_blank">here</a>.**

# Key benefits

- **Strategic revenue projection:** Through the 'Average LTV' formula, businesses can gain a clearer picture of potential revenue streams by understanding the average projected income from each plan.
- **Holistic customer valuation:** The 'Subscription Lifetime Value' section offers both a detailed breakdown and an overarching view of lifetime values for various plans, spotlighting plans that excel in long-term fiscal performance.
- **Informed business decision-making:** By identifying high-performing plans and understanding the true value of customers, businesses can refine their strategies in pricing, acquisition, and retention, ensuring sustainable growth and profitability.

# Plan performance LTV

The Lifetime Value (LTV) view of the Plan Performance dashboard dives deep into the valuation of customer relationships by presenting the average projected revenue a customer will generate over the course of their relationship with your business. Comprising two main sections - 'Subscription Lifetime Value' and 'Average LTV' - the LTV view offers critical insight into the fiscal value of long-term customer relationships.

#### Average LTV

Average LTV reflects the average projected revenue of subscriptions in the selected plans. It's calculated using the formula:

**Average Subscription LTV = ARPS (1 + d) / (d + subscription churn Rate)**

Where:

- ARPS is the Average Revenue Per Subscription, calculated by dividing the MRR contributed by all subscriptions active at the end of the month by the number of active subscriptions at the end of the month.
- Subscription churn rate is calculated by taking the number of churned subscriptions and dividing it by the number of subscriptions active at any time during that month.
- The symbol (d) stands for the discount rate, a consistent value used in revenue projection calculations. This rate factors in various elements such as market, financial, and other associated risks, in addition to the time value of money. By default, Recurly sets this rate at 1%. However, users have the flexibility to modify it via the “Monthly Discount Rate” dropdown.

### Subscription lifetime value

The Subscription Lifetime Value section visualizes the lifetime values of your subscriptions for selected plans in a detail chart and a total line chart.

- **Lifetime value**: The line chart represents the calculated lifetime values of subscriptions for the selected plans, offering a glimpse of the fiscal value associated with maintaining long-term customer relationships.

  <Image src="https://files.readme.io/e7b5b44af7271b28bc5a561c403f612c74a2e219455ee2ca3516537ac779505f-image.png" align="left" width="1000px" border={true} />


* **Subscription lifetime values:** This detailed chart provides a breakdown of lifetime values for the top five plans by selected timeframes, aiding in understanding the long-term financial performance of different plans.


<Image src="https://files.readme.io/0c426c7757bc49e9f5b316df96ff266b5d46bb0f61e4e080e8adb91b652e2e69-image.png" align="center" width="1000em" border={true} />


### How to use the Average LTV feature

1. Access the Plan Performance LTV view: On your Plan Performance Dashboard, navigate to the LTV view.
2. Explore the Subscription Lifetime Value section: Here, you will find two charts: 'Lifetime Value' and 'Subscription Lifetime Values'. Spend some time analyzing these charts to understand the LTV of different plans.
3. Use the Average LTV formula: To get a deeper understanding of your LTV, use the Average Subscription LTV formula. Note that you need the ARPS, churn rate, and discount rate to make these calculations.
4. Identify high-performing plans: Use the information provided by these charts to identify which plans have the highest LTV. Consider focusing your marketing and retention efforts on these plans.
5. Use this data for strategic planning: Incorporate these insights into your broader business strategy. Use it to inform decisions about pricing, customer acquisition, and customer retention.

<br />
