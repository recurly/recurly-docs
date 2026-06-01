---
title: Subscriber benchmarks
excerpt: >-
  Built-in subscriber benchmarks allow merchants to see their key performance
  metrics, related to subscribers, how they stack against similar companies
  within their industry, and how they’re trending.
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

* Users must have analytics user role permission.

# Definition

The subscriber benchmarks dashboard will provide insights on your acquisition rate, signup decline rate, and overall churn rate, comparing yourself to others in your industry with Recurly’s built-in benchmarks.

# Key benefits

* **Industry comparison**: Compare key subscription metrics with industry benchmarks to understand performance relative to peers, identifying areas of strengths and weaknesses.

* **Competitive insights**: Gain insights into how competitors are faring in terms of subscription metrics, uncovering areas to differentiate and improve to gain a competitive edge.

* **Informed decision-making**: Make informed decisions based on real-world data to help set realistic goals and expectations for subscription growth and customer retention.

* **Forecasting and planning**: Enable more accurate forecasting and long-term planning to help businesses set reachable growth targets and allocate resources effectively.

# Key Details

## General Filters (Top Left Corner)

* **Date Range:** Adjust the monthly period for benchmark comparisons, with a default setting of 14 months, to track and analyze long-term trends.

* **Benchmarks Industry:** See benchmark data specific to your industry, offering relevant insights and comparisons.

* **Subscriber Type:** This filter is fixed to “Paying Subscribers,” focusing the benchmark comparison on subscribers with at least one paid invoice.

## Subscriber Benchmarks

The Subscriber Benchmarks dashboard is designed to enhance your understanding of the effectiveness of your strategies throughout the subscription lifecycle. By examining your acquisition rate, sign-up decline rate, and churn rate, you gain a full picture of what’s working and what areas need improvement.

**Acquisition Rate**

The acquisition rate is calculated by dividing the number of subscribers gained during a certain period by the number of subscribers at the start of that period. Important notes include:

* **Eligibility:** Only includes subscribers who have a paid invoice with an amount greater than zero, excluding those in trial or undergoing dunning from trial.
* **Detailed Calculation:** To be considered an acquisition in a given month, the subscriber must either have only expired subscriptions at the beginning of the month OR no subscriptions at all and also have at least one non-expired subscription at the end of the month  (e.g. the subscription state could be active, canceled, or paused). Future, pending, and failed subscriptions are not included. Because benchmarks are calculated on a monthly basis, this omits any subscribers acquired intra month that were also present at the beginning of the month (referred to as ‘ghost acquisition’).

Example: assume a subscriber is active on Jan 1st, 2024 and in dunning, then expires/churns on Jan 10th, and signs back up on Jan 15th while remaining active through the end of the month. This customer who won't count as an acquisition since they were active at the beginning of the month (despite the fact they did churn and signup in the month)

* **Benchmark Calculation** Benchmark quartiles are generated monthly, providing a consistent framework for comparison at the start of each new month. However, individual Merchant KPI rates, such as the renewal invoice paid rate, are calculated on a daily basis. This means that while the benchmarks themselves are updated monthly, the underlying data for specific KPIs is refreshed throughout the day and can be observed on their respective dashboards. It's important for users to note that although these daily updates occur, the broader benchmark comparisons remain static throughout the month until the next monthly update cycle.

<Image align="center" border={true} src="https://files.readme.io/496ee080d8409235e089fd6918f1ac06ffb94e375ee030882156c8918a02260b-image.png" className="border" />

Your ranking within your industry is shown as a percentile, allowing you to track how your acquisition rate compares to peers over time through the trend of your percentile ranking.

**Sign-up Decline Rate**

The sign-up decline rate is calculated by dividing the number of unsuccessful initial transaction attempts on an account by the total number of initial transaction attempts on an account. Here’s how it works:

* **Failed Sign-up Definition:** An account is considered to have a failed sign-up if its initial attempt to sign up does not succeed. Even if the account makes subsequent attempts and eventually succeeds, it is still marked as a failed sign-up due to the initial failure.

* **Inclusion Criteria:** The calculation includes all kinds of initial transactions such as authorization/verification transactions, one-time purchases, and subscription sign-up attempts.

* **Example Calculation:** If 5 accounts try to sign up, and 3 succeed on the first try, 1 fails initially but succeeds later, and 1 fails and never succeeds, the decline rate is 40%. This is because 2 out of the 5 initial sign-up attempts were unsuccessful.

<Image align="center" border={true} src="https://files.readme.io/c75301528d853b2ea0819fd5023ff98351eaff3847ee0ed8c0dcc42571ee9a7b-image.png" className="border" />

Your performance in this area is displayed as a percentile, showing how you rank compared to others in your industry. Monitoring your percentile trend over time can provide insights into how your sign-up process compares to industry standards and highlights areas for improvement.

**Churn Rate**

The churn rate metric offers insight into the proportion of subscribers lost during a specified time period, compared to the total number of subscribers at the beginning of that period. Here’s how it’s determined:

* **Subscriber Eligibility:** Only includes subscribers who have had at least one paid subscription invoice. This means those in trial periods or in dunning following a trial are not considered.

* **Detailed Calculation:** Churn benchmarks are calculated on a monthly basis. To be considered churned in a given month, the subscriber must have a non-expired subscription at the beginning of the month (e.g. the subscription state could be active, canceled, or paused) and  only expired subscriptions at the end of the month. Future, pending, and failed subscriptions are not considered. Churn that occurs within the month, often referred to as ‘ghost churn,’ is not included in the benchmarks. Example of ghost churn: a subscriber is not active at the beginning of the month, signs up for a subscription mid-month, then expires before the end of the month is NOT churn since they were not active at the beginning of the month

* **Benchmark Calculation** Benchmarks are calculated at the end of each month, with a new benchmark ranking and percentile available at the start of each month.

* **Multiple Subscriptions:** For subscribers with several subscriptions,  the last expired subscription is used to categorize the churn as either voluntary (the subscriber chose to leave) or involuntary (due to issues like payment failure).

![](https://files.readme.io/7449fa5015cd883529d9e15eed5b3b36a5fd718d4b4338d127c887501bf8064c-image.png)

Your performance is represented as a percentile, showing how your churn rate compares to others in your industry. Watching the trend of your percentile over time can reveal valuable insights into the effectiveness of your retention strategies and how they stack up against industry norms.

## About Benchmarks

Recurly's benchmark reports offer insights into your performance metrics compared to similar businesses in your industry over time. This tool helps you understand your competitive position and identify growth opportunities by comparing your key performance indicators (KPIs) with industry standards.

# FAQs

**What is a "Paid Subscriber"?**  
A "Paid Subscriber" refers to a subscriber who has paid for at least one invoice associated with their subscription. This excludes those currently in a trial period or in a dunning process following a trial.

**Why is the timeframe preset to "Monthly"?**  
Benchmarks are set to be compiled and analyzed monthly to ensure uniform data aggregation and calculation, providing clear and comparable metrics consistently across different periods.
