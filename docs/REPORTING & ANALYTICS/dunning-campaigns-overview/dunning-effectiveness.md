---
title: Dunning campaigns dashboards
excerpt: >-
  Boost your bottom line with Recurly's dunning campaigns effectiveness
  dashboards.
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

Dunning management is key to Recurly’s revenue recovery efforts. Through the Dunning Effectiveness dashboard, you can gain insights into the dunning recovery rate, amount of revenue recovered, and the number of subscriptions saved from overdue invoices. The Dunning Effectiveness dashboard allows you to monitor, analyze, and optimize your dunning efforts, leading to improved revenue recovery.

> **Note:** It's essential to note the distinction between a subscriber and a subscription. While a single subscriber might hold multiple active subscriptions, this dashboard focuses on counting the individual subscriber, not the number of subscriptions they possess.

# Dunning effectiveness charts

The Dunning Effectiveness feature in Recurly allows for a comprehensive analysis of your dunning campaigns with eight different view configurations divided into three significant sections. **The information available depends on the dunning campaigns created and active in the system.**

## All dunning campaigns

### By invoices

This section provides a comprehensive view of your invoice recovery performance across all dunning campaigns.

**Charts and information available:**

1. **KPIs:** These indicators provide a snapshot of your total past due invoices and recovery rate, allowing you to track changes over time and make informed decisions about your dunning strategies.  
   ![](https://files.readme.io/23d072b-image.png)
2. **Invoice recovery rate:** This chart shows the recovery rate of invoices that went past due during the selected date range. It's a valuable tool for gauging the success of your overall recovery efforts.  
   ![](https://files.readme.io/0a8e038-image.png)

For both the Invoice by Recovery Reason and Dunning Life Cycle by Day graphs below, the following are the recovery reasons:  
**Successful retries:** our static or [intelligent retries](https://docs.recurly.com/docs/retry-logic)  
**Customer updates:** updates your customers made to their accounts usually prompted by dunning  
**Manual:** updates you and your team made to your customer accounts  
**Other:** can include invoices which briefly entered Dunning processing and were saved using our expiration management process

1. **Invoice recovery by reason (Recovered Invoices by Recovery Reason): **This detailed breakdown helps you understand the reasons for invoice recovery, providing valuable insights into where your strategies are most effective.  
   ![](https://files.readme.io/baaaf1c-image.png)
2. **Dunning lifecycle by day (Percent Recovered by Days in Dunning):** This chart tracks the recovery of revenue over time, helping you understand the efficiency of your dunning strategies throughout different stages of the dunning lifecycle.  
   ![](https://files.readme.io/501dc3a-image.png)

### By revenue

This view focuses on the financial impact of your dunning campaigns.

**Charts and information available:**

1. **KPIs:** Key performance indicators here focus on past due and recovered revenue. By monitoring these figures, you can assess the financial effectiveness of your dunning efforts.  
   ![](https://files.readme.io/e6eb23b-image.png)
2. **Dunning recovered revenue by recovery reason:** This chart provides a breakdown of recovered revenue by reason, allowing you to identify which areas of your recovery strategies are most financially successful.  
   ![](https://files.readme.io/5c49022-image.png)
3. **Dunning lifecycle by day (Percent Recovered by Days in Dunning):** This chart tracks the recovery of revenue over time, helping you understand the efficiency of your dunning strategies throughout different stages of the dunning lifecycle.  
   ![](https://files.readme.io/1c795c5-image.png)

### By subscriptions

The focus here is on how dunning campaigns affect your subscription numbers.

**Charts and information available:**

1. **KPIs:** The key performance indicators here revolve around subscriptions, including the number of subscriptions past due and saved. By monitoring these metrics, you can assess the effect of your dunning campaigns on your subscriber base.  
   ![](https://files.readme.io/8df91db-image.png)
2. **Subscriptions saved:** This chart presents the total number of subscriptions saved through your dunning efforts.  
   ![](https://files.readme.io/7c75b32-image.png)
3. **Subscriptions saved by recovery reason:** This breakdown provides insight into the reasons for subscription recovery, aiding in the refinement of your dunning strategies.  
   ![](https://files.readme.io/93a92ff-image.png)
4. **Dunning lifecycle by day (Percent Recovered by Days in Dunning):** This chart tracks the number of subscriptions recovered over the dunning cycle, giving you a sense of when most recoveries occur.  
   ![](https://files.readme.io/23d05c3-image.png)

## Individual dunning campaigns

### By invoices

**Charts and information available:**

1. **Invoice recovery rate:** This chart tracks the recovery rate of invoices for a specific dunning campaign.  
   ![](https://files.readme.io/d7dca90-image.png)
2. **Invoice recovery by reason (Recovered Invoices by Recovery Reason):** This provides a breakdown of recovered invoices by reason for an individual campaign.  
   ![](https://files.readme.io/6e2df47-image.png)
3. **Dunning lifecycle by day (Percent Recovered by Recovery Reason):** This tracks the recovery of revenue over the dunning lifecycle for a specific campaign.  
   ![](https://files.readme.io/75ef79e-image.png)
4. **Dunning lifecycle by bucket (Dunning Bucket by Recovery Reason): **This table presents when during the dunning cycle subscriptions are most commonly saved for a specific campaign.  
   ![](https://files.readme.io/bc8632f-Screen_Shot_2024-07-18_at_2.43.59_PM.png)

### By revenue

**Charts and information available:**

1. **Dunning recovered revenue by recovery reason:** This chart breaks down recovered revenue by reason for an individual campaign.  
   ![](https://files.readme.io/28d44c4-image.png)

2. **Dunning lifecycle by day (Percent Recovered by Days in Dunning):** This tracks the recovery of revenue over the dunning lifecycle for a specific campaign.

3. **Dunning lifecycle by bucket (Dunning Bucket by Recovery Reason):** This chart presents when during the dunning cycle subscriptions are most commonly saved for a specific campaign.  
   ![](https://files.readme.io/00d9a01-image.png)

4. **Dunning lifecycle by day (Dunning Day by Recovery Reason):** This tracks the recovery of subscriptions over the dunning lifecycle for a specific campaign.  
   ![](https://files.readme.io/910885a-image.png)

### By subscriptions

**Charts and information available:**

1. **Saved subscriptions:** This chart shows the total number of subscriptions saved through a specific dunning campaign.  
   ![](https://files.readme.io/bbc8735-image.png)
2. **Subscriptions saved by recovery reason: **This breaks down saved subscriptions by reason for an individual campaign.  
   ![](https://files.readme.io/f569a77-image.png)
3. **Dunning lifecycle by bucket (Dunning Bucket by Recovery Reason): **This chart presents when during the dunning cycle subscriptions are most commonly saved for a specific campaign.  
   ![](https://files.readme.io/8e88275-image.png)
4. **Dunning lifecycle by day (Dunning Day by Recovery Reason): **This tracks the recovery of subscriptions over the dunning lifecycle for a specific campaign.  
   ![](https://files.readme.io/4f14549-image.png)

## Compare dunning

This section allows you to compare the effectiveness of different versions of a campaign or different campaigns altogether.

### By versions

**Charts and information available:**

1. **Recovery rate:** This comparison between two versions provides information about their respective recovery rates and durations, alongside a month-by-month breakdown for each.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/90adef7-image.png",
        null,
        ""
      ],
      "align": "center",
      "sizing": "75% "
    }
  ]
}
[/block]


2. **Dunning lifecycle by day (Dunning Version A Buckets by Recovery Reason & Dunning Version B Buckets by Recovery Reason):** These charts allow you to compare when recoveries typically occur in the lifecycle of each version.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ce003b8-image.png",
        null,
        ""
      ],
      "align": "center",
      "sizing": "75% "
    }
  ]
}
[/block]


### By campaigns

**Charts and information available:**

1. **Recovery rate: **This comparison between two campaigns provides information about their respective recovery rates and durations, alongside a month-by-month breakdown for each.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2229926-image.png",
        null,
        ""
      ],
      "align": "center",
      "sizing": "75% "
    }
  ]
}
[/block]


2. **Dunning lifecycle by day (Dunning Campaign A Buckets by Recovery Reason & Dunning Campaign B Buckets by Recovery Reason):** These charts allow you to compare when recoveries typically occur in the lifecycle of each campaign.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7cb65ea-image.png",
        null,
        ""
      ],
      "align": "center",
      "sizing": "75% "
    }
  ]
}
[/block]


# Leverage dunning effectiveness functionalities

1. **Navigating to the Dunning Effectiveness dashboards:** Log into your Recurly account. From the left navigation pane, click on "Analytics", then select "Dunning Effectiveness".
2. **Interacting with the dashboard actions:** The actions are located in the top right corner of the dashboard. Use these to refresh your data (the "Reload" action), hide filters ("Hide Filters" action), clear cache and refresh the data, download the dashboard, reset filters to default settings, or open folders from the dashboard. These actions ensure you're always working with the most current and relevant data.
3. **Applying filters:** Use the filters in the top left corner to refine the displayed data. You can adjust the time frame for displaying subscriber data (daily, weekly, monthly), choose a metric type, select a specific date range, or choose the currency type that displays on the dashboard. These filters allow you to dive deeper and find the exact data you need. **In the “Compare Dunning” screens, you can configure additional filters to select which campaigns or versions the system is loading for the comparisons.**
4. **Enabling multi-currency support:** If you're using Recurly Professional, or Elite plans, you can run transactions in more than one currency. To enable this, specify which currencies you want to accept for your account. Then, define the pricing for your subscription plans and coupons using the new currency. Now, you can choose one of the enabled currencies for the dashboard.
5. **Viewing the total billings across all currencies:** If your site supports more than one currency, you'll see a default view that shows the total payments, refunds, and net billings across all currencies, converted to your primary currency.Refreshing your data: The "Clear Cache" option allows you to refresh your data. You can do this in three ways: at the bottom of the dashboard, within each widget, or from the top right corner. This ensures your dashboard always reflects the most current data.
6. **Interacting with charts and legends:** The dashboard presents your data in various formats, like bar, line, and pie charts. Color-coded legends help you understand the values. Click on a point in a chart to display the corresponding timeframe and value. You can also hide and restore data on the widget by clicking on the colors in the legend. This interactive feature enables you to understand your data at a glance.

# Getting dunning effectiveness full potential

Leveraging the full potential of the "Dunning Effectiveness" section involves not only understanding its features but also how to use these features to improve your dunning campaigns. Below are some steps to guide you:

1. **Understand your dunning campaigns**

Start by familiarizing yourself with all your active dunning campaigns. The "All Dunning Campaigns" section provides an overview of these campaigns. Focus on the following data:

- Key Performance Indicators (KPIs)
- Recovery rates (for invoices, revenue, and subscriptions)
- Recovery reasons

Identify any trends or patterns, such as common recovery reasons or periods when recovery rates tend to spike or drop.

2. **Deep dive into individual campaigns**

Use the "Individual Dunning Campaigns" section to get detailed insights on specific campaigns. You can compare different campaigns and versions of campaigns to identify what's working and what's not.

- For invoice data, check the "Invoice recovery rate" and the "Invoice Recovery by Reason".
- For revenue data, check the "Dunning Recovered Revenue by Recovery Reason" and the "Dunning Lifecycle by Day".
- For subscriptions, check the "Saved Subscriptions", "Subscriptions Saved by Recovery Reason", and the "Dunning Lifecycle by Bucket".

Pay attention to which strategies lead to the highest recovery rates. Also, watch for strategies that don't seem to be working, as indicated by low recovery rates or high churn rates.

3. **Compare Dunning Campaigns and Versions**

This step helps identify best practices and areas for improvement. Use the "Compare Dunning'' section to evaluate the effectiveness of different campaigns or versions of a campaign.

- In comparing versions, focus on the "Recovery rate" and "Dunning Lifecycle by Day".
- In comparing campaigns, look at similar metrics but across different campaigns.

Compare the performance of each campaign/version in terms of recovery rate and when during the dunning lifecycle recovery happens.

4. **Apply insights to improve dunning campaigns**

Use the insights gathered from the above steps to make informed decisions about how to modify your dunning campaigns. This could mean changing the timing, frequency, or content of your dunning emails, or it could mean altering how you segment and target customers within your dunning campaigns.

5. **Continually monitor and adjust**

The Dunning Effectiveness feature is not a set-it-and-forget-it tool. To get the most out of it, you need to continually monitor your campaign performance and adjust your strategies as needed. Pay close attention to any changes in your recovery rates or in the reasons for recovery, as these could signal that further changes to your dunning campaigns are needed.

By following these steps, you can ensure that you're using the Dunning Effectiveness feature to its fullest potential, and in turn, making your dunning campaigns as effective as possible.