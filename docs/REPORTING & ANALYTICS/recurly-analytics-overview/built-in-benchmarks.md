---
title: Built-in benchmarks
excerpt: >-
  Built-in benchmarks allow merchants to see their key performance metrics,
  related to their business, how they stack against similar companies within
  their industry, and how they’re trending.
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

Recurly’s new built-in benchmarks will help companies gauge their performance against similar companies to prioritize strategies and initiatives to improve key business metrics. All Recurly merchants are included in benchmarking.

# Key benefits

- **Industry comparison:** Compare key subscription metrics with industry benchmarks to understand performance relative to peers, identifying areas of strengths and weaknesses. 
- **Competitive insights:** Gain insights into how competitors are faring in terms of subscription metrics, uncovering areas to differentiate and improve to gain a competitive edge.
- **Data-driven decisions: **Develop informed strategies with real-world data to help set realistic goals and expectations for subscription growth and customer retention.
- **Forecasting and planning: **Enable more accurate forecasting and long-term planning to help businesses set reachable growth targets and allocate resources effectively.

# Key details

Recurly’s built-in benchmark reports provide customers with a detailed view of their key performance metrics and how these metrics stack up against similar companies within their industry over a specific timeline. These comprehensive reports offer the following features:

- **Percentile display**: Metrics are displayed as a percentile, reflecting your site’s performance against a variety of benchmarks.

- **Industry comparison**: Reports show how your specific metrics compare to the industry median as well as the top and bottom quartiles of customers within your industry.
  - Users can change the default industry via the Analytics settings page.

- **Trend analysis**: The reports present a trend of your benchmarks over time, which can be adjusted based on the invoice creation date range, allowing for tailored temporal analysis.

## Benchmarks

**Acquisition rate**

The acquisition rate is calculated by dividing the number of subscribers gained during a certain period by the number of subscribers at the start of that period. [Learn more](https://docs.recurly.com/docs/subscriber-benchmarks).

**Sign-up decline rate**

The sign-up decline rate is calculated by dividing the number of unsuccessful initial transaction attempts on an account by the total number of initial transaction attempts on an account. [Learn more](https://docs.recurly.com/docs/subscriber-benchmarks).

**Churn rate**

The churn rate metric offers insight into the proportion of subscribers lost during a specified time period, compared to the total number of subscribers at the beginning of that period. [Learn more](https://docs.recurly.com/docs/subscriber-churn-benchmarks).

There are three key churn benchmarks to consider:

1. **Overall churn:** This metric aggregates both involuntary and voluntary churn, providing a comprehensive view of total subscriber loss.

2. **Involuntary churn:** This benchmark focuses on subscribers lost due to payment issues, helping you understand the effectiveness of your payment recovery efforts.

3. **Voluntary churn:** This measures the rate at which subscribers choose to leave of their own accord, offering insights into subscriber satisfaction and the value they perceive from your service.

**Renewal invoice paid rate**

This metric calculates the percentage of renewal invoices created within a certain period that are successfully paid (marked as "paid") out of the total number of renewal invoices issued. [Learn more](https://docs.recurly.com/docs/renewal-benchmarks). 

**Renewal decline rate**

This calculation shows the percentage of renewal invoices that are not successfully paid on the first attempt. [Learn more](https://docs.recurly.com/docs/renewal-benchmarks).

**Dunning recovery rate **

This metric measures the effectiveness of your dunning process by calculating the percentage of invoices that are successfully recovered after initially entering the dunning process. [Learn more](https://docs.recurly.com/docs/dunning-benchmarks). 

## About benchmarks

Recurly's benchmark reports offer insights into your performance metrics compared to similar businesses in your industry over time. This tool helps you understand your competitive position and identify growth opportunities by comparing your key performance indicators (KPIs) with industry standards.

# FAQs

**What is a "paid subscriber"?**

A "Paid Subscriber" refers to a subscriber who has paid for at least one invoice associated with their subscription. This excludes those currently in a trial period or in a dunning process following a trial.

**Q: What should be my approach when using built-in benchmarks, and how do I respond to low benchmark rankings?**

**A**: It's crucial not to immediately worry if you encounter a low benchmark rating. Such ratings do not necessarily mean there is a problem. In many cases, businesses have legitimate reasons for lower scores in certain metrics. Remember, your percentile ranking is just a comparative measure against your peers. Here are some points to consider:

- A change in your benchmark ranking, such as a drop from the 85th to the 65th percentile over a year, should prompt an analysis of changes within your business relative to your peers.
- Understand that customer demographics, a significant factor in benchmark metrics, tend to remain constant. For instance, serving lower-income consumers often correlates with higher Renewal Invoice Decline Rates and lower Renewal Invoice Paid Rates.
- Adjustments in your Dunning settings should be examined for their impact on your Renewal Invoice Paid Rate. Utilizing tools like the Compare Dunning Campaigns and Recovered Revenue dashboards can be insightful.
- If you notice substantial shifts in any benchmark metrics, it's advisable to analyze the trends over several months, particularly for businesses with fewer than 100 subscribers, as they are more prone to fluctuations.
- Enabling additional features like Account Updater in Recurly might help in improving these metrics.

If your benchmark is notably low within your industry or shows a declining trend, consider the following actions:

- A declining Renewal Invoice Paid Rate may indicate ineffective recovery mechanisms. Re-evaluating your dunning settings and ensuring that the account updater is enabled for all card types could enhance your paid rates, thereby improving your industry percentile.
- An increasing Renewal Invoice Decline Rate can be addressed by analyzing and prioritizing your most effective gateways or payment methods, and deemphasizing less efficient ones.

**Q: What companies am I benchmarked against?**

**A**: Benchmarks compare your business to that of other companies in the same vertical as you are. Recurly’s exclusive built-in benchmarks are drawn from the experiences of over 58 million unique subscribers and 2,200 global brands, which includes merchants with different subscriber volume and and order sizes.

**Q: What additional benchmarks capabilities are coming?**

**A**: In the coming months, new benchmarks will be added to focus on subscriber acquisition and retention.  Recurly is also considering adding in additional ways to filter these benchmarks, such as average order size, and other considerations.

**Q: How can I change the industry against which I am benchmarked?**

**A**: To adjust your benchmark industry, simply navigate to the [Analytics Settings](https://docs.recurly.com/docs/analytics-settings) page and request the change. This adjustment will enable you to compare your percentile rankings with merchants in the newly selected industry. Please note that the change will take effect one day after your request.

**Q: Why do I see changes in my historical benchmarks?**

**A**: Variations in historical benchmarks are typically due to a few reasons:

- Benchmarks will change as invoices are processed throughout the course of the month. For example, invoice paid rate is based on the invoice creation date, but invoices in dunning at the end of the month will continue to be collected after month end, impacting invoice paid rate and associated benchmarks. Additionally, the renewal invoice decline rate can change after the end of the month if the initial invoice transaction attempt occurs after the invoice was created. 
- When merchants leave the Recurly platform, Recurly is required to delete the site’s data, which results in changes to historical benchmarks.
- New merchants joining the Recurly platform will alter the percentile rankings of existing merchants.
- Occasionally, Recurly may reclassify the industries of certain merchants, which can also lead to changes in benchmarks.

**Q: What defines a “Renewal” Invoice?**

**A**: A renewal invoice is created as part of an ongoing subscription. Key characteristics of a renewal invoice include:

- Exclusion of the initial signup subscription invoice.
- Exclusion of the first invoice following a trial period.
- Renewal invoices are a subset of recurring invoices. While all renewal invoices are recurring, not all recurring invoices are considered renewals. For instance, recurring invoices also encompass the first invoice of a subscription and the first invoice post-trial.
- Not all invoices in a subscription are recurring. For example, invoices for credits or subscription changes are not recurring. This is determined based on the individual charges on the invoice.
- This categorization of invoices (e.g., recurring/renewal) applies to all transactions on the invoice, ensuring alignment between renewal decline rates (based on transactions) and renewal recovery rates (based on invoices).

**Q: I have a sandbox with transactions, so why can't I see any benchmark data?**

**A:** Because we use only live transactions for our benchmarks, sandbox data cannot be compared. To see what benchmark data can look like, make sure the toggle for sample data is on at the top of the page.