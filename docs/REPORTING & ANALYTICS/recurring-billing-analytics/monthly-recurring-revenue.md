---
title: Monthly recurring revenue
excerpt: ''
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

This feature **may not be included** in the Starter or Pro plans. If you are interested, please contact [Recurly Sales](https://recurly.com/demo/contact-sales/) to discuss upgrade options.

### Prerequisites

* Users must have Analytics user role permission.

# Definition

The Monthly Recurring Revenue (MRR) dashboard is a vital tool for subscription-based businesses, offering a deep dive into predictable monthly revenue patterns. While not equivalent to GAAP revenue, MRR is a pivotal metric that reflects your company's growth and revenue trends. Updated multiple times daily, this dashboard provides the freshest insights into both successful and failed transactions, dunning activities, discounts, and projected MRR.

> **Note:** It's essential to note the distinction between a subscriber and a subscription. While a single subscriber might hold multiple active subscriptions, this dashboard focuses on counting the individual subscriber, not the number of subscriptions they possess.
>
> **For additional guidance on navigating and utilizing filter tools, consult our documentation<a href="https://docs.recurly.com/docs/recurly-analytics-overview#navigation-features" target="_blank">here</a>.**

# Understanding MRR

The Monthly Recurring Revenue (MRR) dashboard provides valuable insights into your business's growth and revenue momentum by tracking total MRR and MRR changes. MRR represents the predictable revenue that a business can expect on a monthly basis and is a key metric for subscription-based businesses. It's important to note that MRR is not the same as reportable Generally Accepted Accounting Principles (GAAP) revenue and should not be treated as such.

The data is updated multiple times a day, and you can check the widget at the bottom of the dashboard to verify the time of the last update.

The MRR dashboard now offers a more nuanced view of your monthly recurring revenue, including insights into failed transactions, transactions in dunning, discounts, and expected MRR.

## What's included on the dashboard?

The MRR calculation incorporates various components related to invoiced recurring charges, credits, and refunds from subscriptions. You can determine if a charge is included in MRR if the line item associated with that charge has a start and end date on the invoice.

Examples of adjustments included in the MRR calculation:

* Subscription and subscription add-on amounts
* Manual recurring charges
* Proration credit from a subscription downgrade/upgrade
* Refund of a subscription amount

The following are **NOT** included in the MRR calculation:

* One-time charges without start_date and end_date
* One-time credits
* Taxes
* Usage-based billing amounts

You have the option to include or exclude the following in the MRR calculation:

* Recurring charges from failed invoices
* Coupon discounts
* Multi-currency support

For sites that support multiple currencies, the default view shows total MRR across all currencies, converted to the primary currency and summed. Conversion rates are updated daily using data from [https://openexchangerates.org/](https://openexchangerates.org/). Historical MRR uses the conversion rate at the time the charge was created and does not change over time for current conversion rates.

For both the Total MRR graph and the MRR Break-Out we have drills for accounts, plans or add-ons.

<Image align="center" border={true} src="https://files.readme.io/f1e965f8fbc00c3b359d588f0fb00b8bfec4e46f49309bc84b24c2f9a29e0730-image.png" className="border" />

<br />

<Image align="center" border={true} width="75% " src="https://files.readme.io/0bcc8ae-image.png" className="border" />

These drills provide a detailed view of each account contributing to the data in the bar/number, sorted by total MRR. A convenient filter at the top lets you narrow down the data by specific accounts or emails.

For a more granular view, you can further drill into a particular account by selecting the Total MRR or Total ARR number.

<Image align="center" width="75% " src="https://files.readme.io/02f934a-image.png" />

This deeper drill showcases all the associated charges that contribute to the total MRR or ARR for the selected account. The same drill-down functionality is available in the MRR Growth section.

### MRR Break-Out

This feature offers users a detailed breakdown of the four components that make up the total MRR, with the added ability to drill into account-level specifics for each component.

Currently, both discounts and failed invoices are integrated into the analytics settings, resulting in four potential default states. The displayed Total MRR is a reflection of the chosen settings combination. Note: If there are any modifications to the analytical settings within the Recurly application, the Total MRR line in the chart will adjust accordingly. This Total MRR is also mirrored in the Total MRR chart and table.

The newly added “In Dunning” series provides insights into the MRR of the current period that's still undergoing the Recurly revenue collection process. Invoices that remain uncollected after retries transition into the failed category and eventually exit the MRR report once the subscription end date is surpassed.

"Expected MRR" denotes the MRR amount for the daily, weekly, or monthly period that's yet to be collected. For clarity, the monthly and weekly views display data for the last day of the respective period. The daily view offers a more dynamic perspective, illustrating the month's progression.

In this section, the MRR can be viewed by:

* Collected MRR
* MRR in Dunning
* Expected MRR (based on upcoming subscription bills)
* Discounts applied to MRR
* Total MRR (Sum of MRR, In Dunning, Expected MRR, minus Discounts)

<Image align="center" border={true} src="https://files.readme.io/9e1cce6ae5a9994bb180d575c2eb898cdc0fbec1f46c8ebb091aebc7b73a9d16-image.png" className="border" />

As you can see with the MRR graph,  you have the ability to drill by account, plan or add-on and then can dive even further, as needed.

## Ways to leverage the MRR dashboard

The MRR data provides valuable insights and helps answer important questions for subscription businesses:

1. What is the expected revenue for each month?
2. Is the revenue increasing or decreasing month over month?
3. Are the monthly recurring revenue targets being met?

By analyzing the MRR dashboard, you can gain a deeper understanding of your business's revenue trends and make informed decisions to drive growth and meet your financial goals.
