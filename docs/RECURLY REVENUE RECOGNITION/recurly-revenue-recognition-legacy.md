---
title: Recurly Revenue Recognition Legacy
excerpt: Learn about our legacy solution for revenue recognition.
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

This feature is no longer available for new subscriptions.

### Additional cost

This feature is no longer offered.

# Legacy solution: Recurly Revenue Recognition

Please be advised that our **legacy revenue recognition solution is no longer available for new subscriptions**. However, we are committed to ensuring that existing users can continue to access this solution without interruption.

Because we no longer sell our legacy solution, we recommend new merchants explore our enhanced Recurly Revenue Recognition Advanced or Standalone editions, which are both designed to meet today's complex financial reporting requirements with ease and precision, and are ASC 606 and IFRS 15 compliant.

> 📘 Notes:
>
> * Our basic solution is not an accounting or ERP system. It provides raw data to assist you in computing the amount of revenue you can recognize more easily.
> * We strongly advise consulting with your accountant before using our basic solution, as they can provide guidance on correct accounting practices.
> * We recommend against changing your revenue recognition type for subscription changes via the API, as this may result in invoices being reassigned to a different revenue recognition method.
> * Please note that the **legacy solution for revenue recognition is not ASC 606 compliant**. It is important to ensure compliance with ASC 606 standards for revenue recognition in your accounting practices.

# Legacy solution: Revenue recognition methods

Recurly offers six different methods for merchants to recognize revenue through the basic solution:

1. **Evenly:** Revenue is distributed evenly over the date range of the charge.
2. **At Invoice Creation Date:** Revenue is recognized at the date the invoice is created.
3. **At Charge Range Start:** Revenue is recognized at the start date of the charge range.
4. **At Charge Range End:** Revenue is recognized at the end date of the charge range.
5. **Recognize at Charge Date:** Revenue is recognized at the date of the charge.
6. **Do not Recognize Revenue:** Charges are excluded from the revenue recognition export.

> ★	You can set revenue recognition rules on the plan, setup fee, add-on, one-time charge, credit, and subscription objects.
>
> ★	When an invoice is created, Recurly automatically calculates the deferred revenue waterfall and generates revenue schedules for each charge or credit. Additionally, it provides a revenue amortization report through an export, facilitating your revenue accounting process.

Please note that this information pertains to the legacy solution. For a more advanced and comprehensive revenue recognition solution, we encourage you to explore our Recurly revenue recognition offering.

## Evenly

Revenue for a charge is recognized evenly over the range of time specified. This option is most common for services provided over a period of time (i.e. SaaS, OTT).

A merchant may choose to recognize revenue evenly by day over a set period of time. As an example, let's use Kale Software. Kale Software is a SaaS organization that provides access to a suite of analytics tools. Kale offers many Plans, Add Ons, and Setup Fees to its customers for its SaaS service. Kale Software also charges customers outside the scope of a subscription for non-recurring charges such as professional services.

**Example 1: one-month subscription:**

On July 26th, Customer A signs up for Kale Software's "Gold Plan", which costs $30 a month, has a Setup Fee of $10, and one Add On for $5. Customer A purchases the recurring "Gold Plan", and the optional Add On. Revenue for the Plan and AddOn will be recognized evenly over the date range of each month's invoice, which is determined by the subscription period. Since this subscription started on July 26, revenue will be recognized over the period billed, in this case July 26 to August 26. A portion of the revenue will be recognized each day, so revenue will appear in the export for both July and August on this charge. Revenue for the Setup Fee is recognized evenly only over the first month's invoice period since it is not recurring.

![](https://files.readme.io/2fc4d4e-image.png)

With the "Evenly" revenue recognition method, you can ensure that revenue is recognized consistently and accurately over the specified time range, providing a clear understanding of your revenue streams for SaaS or other subscription-based services.

An invoice for this example is below:

![](https://files.readme.io/b234f10-image.png)

**Example 2: one-time charge recognized evenly over time**

Let's continue with Kale Software as an example. On July 15th, Kale Software creates a one-time charge with a specific date range from March 1st to August 1st. They choose to recognize revenue evenly over this time period.\
In this scenario, the revenue for the one-time charge will be recognized evenly for each day within the range of March 1st to August 1st. This means that the revenue generated by this charge will be spread out evenly over the entire duration of the specified period.

![](https://files.readme.io/50fa5be-image.png)

When exporting the revenue schedule for this charge, you will see the revenue recognition distributed evenly across the days within the defined range, as shown in the example below:

![](https://files.readme.io/b96f3c8-image.png)

By choosing to recognize revenue evenly over the time period of the one-time charge, Kale Software can accurately account for and report the revenue associated with this specific charge. This approach provides clarity and consistency in revenue recognition, ensuring accurate financial reporting for one-time charges within the specified date range.

## At Invoice Creation

Let's explore two examples of revenue recognition at invoice creation using Kale Software.

**Example 1: Creation Date and Invoice Date Are Different**

On July 15th, Kale Software creates a one-time charge with a scheduled date for August 10th. They select the option to recognize revenue at the time of invoice creation and then generate an invoice. In this case, the revenue for the charge will be recognized on July 15th, the date when the invoice is created, even though the charge itself is scheduled for a later date.

![](https://files.readme.io/8d01cfe-image.png)

**Example 2: Creation Date and Invoice Date Are the Same**

On July 15th, Kale Software creates a one-time charge for June 10th, selecting the option to recognize revenue at invoice creation time. They then generate an invoice on the same day, July 15th. In this scenario, the revenue for the charge will be recognized on July 15th, which is both the creation date of the charge and the invoice date.\
By choosing to recognize revenue at the time of invoice creation, Kale Software ensures that the revenue associated with the one-time charge is recognized immediately upon generating the invoice. This approach allows for accurate financial reporting and provides a clear understanding of revenue recognition for one-time charges within the Recurly system.

## At change range start

**Example 1: Date Range in the Future**

On July 15th, Kale Software creates a charge with a date range from August 10th to September 10th. They select the option to recognize revenue at the start of the charge range. Regardless of when the invoice is created, revenue for this charge will be recognized on August 10th, the start date of the charge range.

**Example 2: Date Range in the Past**

On July 15th, Kale Software creates a charge with a date range from March 1st to May 1st. They select the option to recognize revenue at the start of the charge range. Regardless of when the invoice is created, revenue for this charge will be recognized on March 1st, the start date of the charge range.

## At change range end

**Example 1: Date Range in the Future**

On July 15th, Kale Software creates a charge with a date range from August 10th to September 10th. They select the option to recognize revenue at the end of the charge range. Regardless of when the invoice is created, revenue for this charge will be recognized on September 10th, the end date of the charge range.

**Example 2: Date Range in the Past**

On July 15th, Kale Software creates a charge with a date range from March 1st to May 1st. They select the option to recognize revenue at the end of the charge range. Regardless of when the invoice is created, revenue for this charge will be recognized on May 1st, the end date of the charge range.

By choosing to recognize revenue at either the start or end of the charge date range, Kale Software ensures that revenue is recognized at the appropriate time based on the duration of the charge. This approach allows for accurate revenue reporting and aligns with the specific needs of their business model within the Recurly system.

## At charge date

**Example: Recognizing revenue at charge date**

On July 16th, Kale Software receives a request from a customer to deliver a physical hard disk. The terms of the transaction state that payment will be made upon the physical hard disk's receipt at the customer's office. Kale Software ships the hard disk on July 16th and receives confirmation that the customer will receive it on July 18th.\
Kale Software issues an invoice with an Invoice Date and Charge Date of July 18th and selects the option to recognize revenue on the charge date. Regardless of when the invoice was issued, the revenue for the hard disk shipment will be recognized entirely on July 18th when the disk is received by the customer.

# Export details

To access the detailed revenue schedule data, you can refer to the Exports section in Recurly. Specifically, the "Revenue Recognition" export generates a `.csv` file containing comprehensive information about revenue schedules.

# Gift cards

If you utilize Recurly's Gift Subscriptions feature, it's essential to consider certain factors regarding revenue recognition. In the revenue recognition export, invoices for gift card purchases are not included. However, when a gift card is redeemed, it will act as payment for the associated invoice. Consequently, the resulting invoice will appear similar to other invoices in the revenue recognition export.