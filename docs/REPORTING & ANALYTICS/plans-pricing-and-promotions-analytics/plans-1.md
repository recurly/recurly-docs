---
title: Subscription by plan
excerpt: >-
  Discover the power of 'Subscription By Plans Bars': A vibrant and detailed
  breakdown of plan subscription trends over time.
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

Recurly's 'Subscription By Plans Bars' offers a rich, color-coded visualization of your subscriptions categorized by different plans. Displayed over your chosen timeframe, this feature enables users to effortlessly discern the popularity and performance of each plan. The bars can be interacted with, giving a deeper dive into specific subscription data and metrics, while the subsequent 'Subscriptions by Plans Details Chart' offers a thorough trend analysis of your active subscriptions.

> **Note:** It's essential to note the distinction between a subscriber and a subscription. While a single subscriber might hold multiple active subscriptions, this dashboard focuses on counting the individual subscriber, not the number of subscriptions they possess.
>
> **Note**: Data only includes plans that have had at least 1 subscriber.
>
> **For additional guidance on navigating and utilizing filter tools, consult our documentation <a href="https://docs.recurly.com/docs/recurly-analytics-overview#navigation-features" target="_blank">here</a>.**

# Key benefits

- **Instant plan popularity overview**: The color-coded bars provide an immediate insight into the traction of each plan, helping users identify dominant trends at a glance.
- **Interactive deep dives**: With each bar being drillable, users can seamlessly access detailed subscription metrics, facilitating in-depth analysis without leaving the visualization.
- **Strategic trend analysis**: The detailed chart highlights the performance trajectories of your plans, assisting in proactive decision-making, plan refinement, and the crafting of targeted subscription strategies.

# Subscription by plans

The Subscription By Plans Bars is a visual representation of your subscriptions, segmented by different plans over a selected timeframe. Each bar corresponds to a specific time unit (day, week, or month), and the height of the bar represents the total number of subscriptions. The bar is further color-coded based on different plans, giving you an instant visual clue about which plans are gaining more subscriptions. By clicking on any bar or its section, you can view specific subscription totals for each plan, making it an intuitive tool to understand and compare the popularity of your various plans.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5e2564f-subscription_by_plan_bar_chart.png",
        "subscription by plan bar chart.png",
        ""
      ],
      "align": "center",
      "sizing": "75% "
    }
  ]
}
[/block]


Each bar is a drill so the user can drill into the specific subscriptions that make up each bar.

The drill fields are:

1. Account Code (links to Account in RA)
2. Subscription UUID (links to subscription in RA)
3. Plan Name (links to plan in RA)
4. Plan Code (links to plan in RA)
5. Subscription_plan_started_at_local_time
6. Subscription_trial_started_at_local_time
7. Subscription_trial_ended_at_local_time
8. Subscription_plan_canceled_at_local_time
9. Subscription_plan_expiree_at_local_time
10. Subscription_plan_expiration_reason
11. Active_invoice_number
12. Successful_payment_made (yes/no if there was a payment > $0 made on the subscription)
13. Total_subscriptions
14. Total_new_subscriptions
15. Total_churned_subscriptions

## Subscriptions by plans details chart

The Subscriptions by Plans Details Chart offers a comprehensive view of your active subscriptions for the selected plans compared to the total for all plans. It's organized by timeframe, which can be daily, weekly, or monthly based on your preference. This chart is a powerful tool for analyzing plan performance trends over time. You can identify which plans are consistently popular, which ones are growing, and which might need some attention or restructuring. It's an indispensable resource for strategic planning and informed decision-making regarding your plan offerings.

![](https://files.readme.io/9df20da-subscription_by_plan_details.png "subscription by plan details.png")