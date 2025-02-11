---
title: Hourly activation & churn
excerpt: >-
  Dive deep into Recurly's Hourly Activation & Churn analytics for a
  comprehensive view of subscriber behaviors, trends, and growth patterns.
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

The "Hourly Activations and Churn" section of Recurly's Reporting & Analytics provides an operational overview of subscriber activity and trends, updated hourly. It offers insights into subscription signups and churn rates to help you make informed decisions. 

> **Note:** Subscriber counts focus on individual subscribers, not the number of subscriptions they hold.\
> For guidance on filter tools, visit our <a href="https://docs.recurly.com/docs/recurly-analytics-overview#navigation-features" target="_blank">documentation</a>.

# Key updates on data freshness

* Dashboards are updated hourly, and data can lag up to **two hours.**
* **MRR updates every two hours** due to computational complexity. 
* Dashboards include a timestamp at the bottom, indicating the data's last refresh time. 

**Exceptions and insights:**  

1. Some reports can reflect data as recent as **20–25 minutes** due to faster data lake refreshes (10–15 minutes). However, analytics mart processes introduce up to **1–1.5 hours of staleness** before the next run.  
2. Dashboards have a **four-hour cache**. Merchants can clear the cache manually for more recent updates.

# Key benefits

* **Near real-time visibility:** Gain up-to-date insights into subscriber activations, churn, and net growth.  
* **Trend analysis:** Monitor subscriber behavior on an hourly basis and spot emerging patterns.  
* **Performance tracking:** Compare daily data with past periods for actionable insights.  
* **Decision-making support:** Use detailed metrics to optimize subscriptions and retention strategies.

# Hourly Activation & Churn

### Accessing Hourly Activation & Churn

Follow these steps to access and interpret this report:

1. Navigate to **Subscriber management** in the Reporting & Analytics menu.

2. Open the **Hourly Activations and Churn** dashboard.

3. Apply filters to refine the data:

   * **Combine Subscriptions:** Combines consecutive subscriptions for accurate metrics.
   * **Plan Name:** Analyze data by specific subscription plans.
   * **Subscriber Type:** Filter paying subscribers or trial users.
   * **Date:** Select specific timeframes for deeper insights.  

   <br />

   <Image align="center" className="border" border={true} src="https://files.readme.io/ae47489-Screen_Shot_2024-01-22_at_6.46.43_PM.png" />

4. Review the **four key widgets** at the top:  

   * Subscribers Activated  
   * Subscribers Churned  
   * Net Subscribers  
   * Total Subscribers 

   <br />

   <Image alt="**Click** on widget numbers to drill into account-specific data." align="center" border={true} src="https://files.readme.io/0c2e58e-image.png">
     **Click** on widget numbers to drill into account-specific data.
   </Image>

5. Analyze bar charts for **Activations** and **Churn:**  

   * Charts are interactive, providing granular account details.

**Activations**

<Image align="center" className="border" border={true} src="https://files.readme.io/686ab54-image.png" />

**Churn**

<Image align="center" className="border" border={true} src="https://files.readme.io/1b9c916-image.png" />

Pay attention to **Plan Rankings** for insights into plan-level performance.

# Recommendations for real-time updates

* If merchants require faster updates, suggest leveraging **webhooks** to build a custom solution. While this requires significant development, it provides more control over data freshness.  
* Emphasize the value of existing hourly updates for high-volume days or executive reporting.  

By using these tools and insights, you can optimize subscriber management and align your strategies with data-driven outcomes.
