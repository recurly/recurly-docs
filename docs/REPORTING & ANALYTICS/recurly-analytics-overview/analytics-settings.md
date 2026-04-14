---
title: Analytics settings
excerpt: >-
  Customize your analytics with ease: Set time zones, manage MRR calculations,
  and benchmark against industry standards to optimize insights and drive
  strategic growth on the analytics settings page.
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

### Prerequisites

* Users must have Analytics user role permission.

# Definition

The "analytics settings" page is designed to empower you with control over various analytics features integral to your business operations. This platform allows for the customization of settings such as time zone, Monthly Recurring Revenue (MRR) calculations, encompassing considerations like coupon discounts, failed charge handling, and industry benchmarking. This intuitive configuration interface streamlines the process, ensuring that your analytics reflect your specific operational needs and preferences.

# Key details

## Time zone

Recurly records all transactions in UTC as the underlying billing timezone. The analytics system then aligns its displayed calculations with the time zone specified in your site settings. This approach ensures that while billing events are consistently tracked in UTC, your analytics, reports, and metrics are presented in the local time most relevant to your business operations.

<Image align="center" border={true} src="https://files.readme.io/68f8f91-image.png" className="border" />

## MRR calculations

<Image align="center" border={true} src="https://files.readme.io/df2c11a-image.png" className="border" />

Configure how Recurly Analytics processes various factors affecting Monthly Recurring Revenue, such as coupon discounts and failed charges. These settings are crucial for accurate revenue tracking and forecasting.

### Coupon discounts

Choose how to account for the impact of coupon discounts on MRR:

* **Include the discount value of coupons in MRR (Recommended):** This option adjusts MRR to reflect the actual revenue received. For instance, if a service typically costs $100 but is offered at $75 after a $25 coupon discount, MRR is reported as $75, acknowledging the discount's impact on revenue.
* **Exclude the discount value of coupons from MRR:** Opting for this setting maintains the original service price in MRR calculations, disregarding the discount. Using the previous example, MRR would remain at $100, ignoring the $25 discount applied.

### Failed charges

Determine how to treat failed recurring charges in MRR calculations:

* **Keep all recurring charges in MRR (Recommended):** This setting opts to include all anticipated recurring charges in MRR calculations, regardless of their success or failure, maintaining a consistent revenue outlook.
* **Remove failed recurring charges from MRR:** Selecting this option adjusts MRR to exclude revenues from failed charges, potentially offering a more realistic view of actual earnings.

> **Note:** Modifying how failed charges are accounted for will retroactively affect historical MRR and Lifetime Value (LTV) reports. For a comprehensive understanding, refer to our detailed documentation.

## Benchmarking

<Image align="center" border={true} src="https://files.readme.io/de57084-image.png" className="border" />

Select the industry category that most accurately represents your business to enable benchmarking. This feature compares your performance metrics against standards within your industry, offering insights into your competitive stance and identifying opportunities for growth and improvement.

<Image align="center" border={true} width="400px" src="https://files.readme.io/e077bd2-image.png" className="border" />

> **Note**: Benchmark percentiles will take effect one day after the request. Benchmark quartiles will take effect immediately.

## Back-to-back subscriptions

Use this setting to automatically apply the desired configuration to the Hourly Activations and Churn dashboard.

By using this configuration, if a subscriber started a new subscription after their previous subscription expired, this can be counted as one continuous subscription. This helps ensure that activations and churn are counted appropriately for your business.

<Image align="center" src="https://files.readme.io/6d3975e-Screen_Shot_2024-06-20_at_3.03.28_PM.png" />
