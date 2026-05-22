---
title: Business entities overview
excerpt: >-
  The Business Entities Overview dashboard helps provide key insights into
  metrics like MRR, churn, expansion, and growth across each of their business
  entities supported on a single Recurly site.
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

## Required plan

This feature **may not be included** in the Starter or Pro plans. If you are interested, please contact [Recurly Sales](https://recurly.com/demo/contact-sales/) to discuss upgrade options.

### Prerequisites

Users must have the analytics user role permission. This dashboard is intended for use by merchants who have more than one (1) business entity configured on their site.

# Definition

The Business Entity Overview dashboard allows merchants to choose which of their site's defined business entities they wish to view key metrics for. They can choose to view one, several, or all of their business entities' data at once in a single dashboard. Each entity is color coded to distinguish between individual entity performance.

# Key benefits

* **Singular birds eye view into top metrics**: This dashboard is a one-stop-shop surfacing all of our most utilized tables in one place, making understanding individual entity performance a breeze
* **Entity performance comparison**: Compare key subscription metrics across each of your business entities
* **Understand subscriber trends**: Track churn and refund patterns, which entities have the highest rates of acquisition and expansion, and more. This will help in demonstrating when it's time to leverage Recurly's many tools for raising retention and acquisition rates such as launching new promotional and dunning campaigns, adjusting pricing, offering discounted add-ons, and incentivizing loyal customers through descending ramp-pricing plans.

# Key details

## Filters

Filter by the timeframe, date range, and the business entity(ies) you want to see the data for.

* **Timeframe:** How to display the data. Choose between displaying data in your dashboards aggregated in a daily, weekly, monthly, quarterly, or yearly view.
* **Date range:** The duration you want to see the data reflect. For example, you can set your timeframe to monthly and date range to "is in the last 6 months" to have a monthly view of the given dashboard and its performance over the last 6 months.
* **Business Entity:** The entity or entities you wish to view the data for. You can select all, some, or one. The other individual dashboards under Recurly's Analytics section automatically show comprehensive data across all of your business entities.

## Key dashboards

### Monthly Recurring Revenue (MRR)

The Monthly Recurring Revenue (MRR) dashboard is a vital tool for subscription-based businesses, offering a deep dive into predictable monthly revenue patterns. While not equivalent to GAAP revenue, MRR is a pivotal metric that reflects your company's growth and revenue trends. Updated multiple times daily, this dashboard provides the freshest insights into both successful and failed transactions, dunning activities, discounts, and projected MRR.

The MRR calculation incorporates various components related to invoiced recurring charges, credits, and refunds from subscriptions. You can determine if a charge is included in MRR if the line item associated with that charge has a start and end date on the invoice.

Examples of adjustments included in the MRR calculation:

* Subscription and subscription add-on amounts
* Manual recurring charges
* Proration credit from a subscription downgrade/upgrade
* Refund of a subscription amount
* Invoiced one-time charges with start_date and end_date

The following are **NOT** included in the MRR calculation:

* One-time charges without start_date and end_date
* One-time credits
* Taxes
* Usage-based billing amounts

For sites that support multiple currencies, the default view shows total MRR across all currencies, converted to the primary currency and summed. Conversion rates are updated daily using data from [https://openexchangerates.org/](https://openexchangerates.org/). Historical MRR uses the conversion rate at the time the charge was created and does not change over time for current conversion rates.

### Monthly Recurring Revenue Growth

This dashboard provides a breakdown of the key factors driving MRR changes, helping you track revenue trends over time.

* **New Business** – Revenue from new customers subscribing for the first time.
* **Expansion** – Additional revenue from existing customers, such as plan upgrades or add-ons.
* **Reactivation** – Revenue from previously canceled accounts that resubscribed after having no active subscriptions.
* **Total Growth** – Combined revenue from new business, expansion, and reactivation.
* **Churn** – Revenue lost from customers fully canceling their subscriptions.
* **Contraction** – Revenue reduction from downgrades or plan changes.
* **Total Loss** – Combined revenue lost from churn and contraction.
* **Net MRR** – Total Growth minus Total Loss, reflecting overall MRR movement.

#### **Clarification on Reactivation**

Reactivation MRR represents revenue from accounts that previously had no active subscriptions and later resubscribed. Merchants can explore reactivated accounts by drilling into the cohort details, where they can see subscription expirations and subsequent reactivations.

### Billings

The Billings Dashboard is your guide to understanding payments, refunds, and net billings from all customers. It exclusively displays successful transactions, sidelining manual or credit invoices. This comprehensive tool offers a transparent snapshot of your financial activities over a chosen duration, enabling you to grasp your cash flow, make enlightened decisions, and sculpt potent revenue strategies.

**Net New Billings & New Renewal Billings**

* The Net Billings Dashboard offers a meticulous comparative analysis, differentiating between net new and net renewing payments. Here's how it works:
  * **Net New**: Derived by taking the new payments and subtracting any new refunds.
  * **Net Renewing**: Calculated by deducting renewing refunds from renewing payments.  
    The culmination of these two values presents the Total Net Billings.  
    **For clarity**, within this dashboard:
  * “New” refers to the inaugural payment made by a subscriber.
  * “Renewing” encompasses any subsequent payments made after the initial one.

### Recovered Revenue

The Recovered Revenue dashboard is a robust tool that provides insights into how much revenue you have recovered through Recurly's system. By monitoring involuntary churn from declined invoices, the dashboard uses three main mechanisms - Expiration Date Changes, Account Updater, and Dunning Retries, to ensure the highest rate of paid invoices.

* **Expiration date changes:** This mechanism updates the expiration date on the account's billing information, allowing continuity of invoices and subscriptions. This reduces the likelihood of service disruption for the customer and prevents potential revenue loss.
* **Account updater:** If enabled, this tool checks for credit card updates with providers before a subscription renewal, or when a one-time invoices or re-subscribe sign-up results in a hard decline. By staying up-to-date with customer's payment details, this tool aids in reducing failed invoices and maintaining a steady revenue stream.
* **Intelligent retries:** This is Recurly's sophisticated retry logic that maximizes the likelihood of turning failed invoices into successful ones. By strategically timing the retries, it significantly reduces involuntary churn caused by failed invoices.
* **Backup payment method:** Our Backup Payment Method feature acts as your safety net, ensuring uninterrupted service for your customers even when their primary payment method fails. By securely storing an alternative payment option, it safeguards your revenue stream and minimizes disruptions.
* **Customer Updates:** When a customer updates their payment method, Recurly will attempt collection on the failed automated invoice. Customers may be prompted to update their payment method via Recurly's dunning emails, or other notifications built into your application. This data does not include manual invoices.
* **External Recovery:** When other systems successfully collect on a failed invoice, and send an update to Recurly.

### Subscribers

This table allows for a deeper dive into the specific changes month over month, offering insights into the ebb and flow of your subscriber dynamics. This data is crucial for understanding the overall health and growth trajectory of your subscriber base.

* **New Subscribers:** Individuals signing up for a subscription for the first time.
* **Returning Subscribers:** Former subscribers who have reactivated their subscription.
* **Churned Subscribers:** Subscribers whose subscriptions have ended, either voluntarily or involuntarily.

### Churn Reasons

Dive into the data to understand the specifics across all churn reasons

* Active Subscribers
* Churned Subscribers
* Non-payment
* Tax Location Invalid
* Canceled
* Non-Payment Gift Card
* Non-Renewing
* Account Closed
* Unknown
* Non-Payment Trial
* Canceled Trial

### Explore Invoices Dashboard

View details around all invoices created across your Recurly site in the Explore Invoices dashboard.

**This dashboard has an array of ways to filter down invoice details by, including:**

* Custom Fields
* Account Primary Billing Info
* Accounts
* Business Entities
* Charges
* Dunning Settings
* Plans
* Subscriptions
