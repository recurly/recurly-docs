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

> **Note:** Subscriber counts focus on individual subscribers, not the number of subscriptions they hold.  
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

# Key details

### General filters 

* **Date:** Select specific timeframes for deeper insights.
* **Plan Name:** Analyze data by specific subscription plans.
* **Combine Subscriptions:** Combines consecutive subscriptions for accurate metrics.
* **Subscriber Type:** Filter all subscribers, paying subscribers (with or without refunds), non paying or trial users.

### Hourly Activation & Churn

1. Review the **four key widgets** at the top:

   * Subscribers Activated
   * Subscribers Churned
   * Net Subscribers
   * Total Subscribers

   <Image align="center" border={true} src="https://files.readme.io/c9ac3660913f039be73673a554d5628e3516581bf5a209e3c9891a0bdce37e3f-image.png" className="border" />

   <br />

2. Analyze bar charts for **Activations** and **Churn:**

   * Charts are interactive, providing granular account details.

**Activations**

<Image align="center" border={true} src="https://files.readme.io/e299713c63c0164ed435ad7fd70c10738f5b9dbe265425bf0aacd6e99f001435-image.png" className="border" />

<br />

**Churn**

![](https://files.readme.io/d78ed12c2d6cdb04f1ae5808b2df77bdf5aedc458255e39b6f23177cc0474cbe-image.png)

Pay attention to **Plan Rankings** for insights into plan-level performance.

# Recommendations for real-time updates

* If merchants require faster updates, suggest leveraging **webhooks** to build a custom solution. While this requires significant development, it provides more control over data freshness.
* Emphasize the value of existing hourly updates for high-volume days or executive reporting.

By using these tools and insights, you can optimize subscriber management and align your strategies with data-driven outcomes.
