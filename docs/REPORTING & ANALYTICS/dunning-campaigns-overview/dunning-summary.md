---
title: Dunning summary
excerpt: >-
  The dunning recovery dashboard has an intuitive layout, presenting you with an
  at-a-glance view of the revenue key performance indicators, a detailed bar
  chart showing the recovered revenue, and a chart detailing the revenue
  recovered by each of Recurly's processes.
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

The Dunning Recovery dashboard is designed to showcase the effectiveness of Recurly's mechanisms in recovering revenue from declined transactions. It features several tools aimed at mitigating payment failures and enhancing overall collection rates:

1. **Account updater:** Automatically refreshes payment details to ensure up-to-date information, reducing the chances of transaction declines due to outdated payment methods.
2. **Customer updates (dunning):** Encourages customers to update their payment method when a transaction fails, facilitating successful future attempts.
3. **Intelligent retries:** Employs a strategic approach to retrying failed transactions, optimizing the timing and methodology to increase the likelihood of success.
4. **Manual:** Allows merchants to manually initiate a collection attempt on a past-due invoice, providing a direct intervention option when automated processes do not succeed.
5. **Other:** Includes scenarios when expiration data forwarding applies to retry transactions as a recovery reason, and for external recoveries.

# Key benefits

* **Effectiveness**: Ensure your dunning strategy is effective to recover failed invoices. 

* **Insights**: Gain insights into how your dunning recovery rate is trending over time.

# Key details

## Recovered revenue KPI

These indicators offer a real-time snapshot of your revenue dynamics. They help you measure the effectiveness of your dunning recovery strategies by comparing your current payment amounts with totals for the last month, previous month, three months ago, and a year ago. This enables you to identify trends and track progress, supporting informed decisions to proactively manage involuntary churn as you track the amount of revenue recovered over time, and compared to last year.

## Dunning recovery chart

This bar chart visualizes the revenue that Recurly has helped you recover by minimizing involuntary churn from declined invoices. It allows you to see at a glance the financial impact of Recurly's services, making it a powerful tool for forecasting and resource allocation. These charts are displayed as a total revenue saved, or a count of invoices recovered.

## Dunning recovery detail

This detailed breakdown gives you insights into the processes that drive revenue recovery. By displaying the amount recovered through each process (Account Updater, Customer Updates, Intelligent Retries, and Manual Collection), it enables you to see which tools are most effective. This knowledge empowers you to focus your efforts on the most productive areas, thereby improving recovery rates, enhancing service continuity, and fostering customer retention. These charts are displayed as a total revenue saved, or a count of invoices recovered.

# Dunning Recovery

The Dunning Recovery dashboard offers a detailed view of the revenue you've successfully recaptured through Recurly's specialized system. It's a focused part of the broader Recovered Revenue dashboard, concentrating on invoices that fail initial payment attempts and subsequently enter the dunning process. The dashboard leverages four key strategies—Account Updater, Customer Updates, Intelligent Retries, and Manual Collection—to maximize the collection of payments.

* **Account Updater:** This feature proactively updates credit card information ahead of subscription renewals, one-time invoice payments, or re-subscription attempts that result in a hard decline. By ensuring payment details are current, it plays a crucial role in minimizing failed transactions and securing continuous revenue flow.

* **Customer Updates:** This mechanism enables customers to update their payment methods after a failure, facilitating another attempt at invoice collection. Recurly can prompt customers for updates through dunning emails or other integrated notifications within your service, aiding in recovering potential lost revenue.

* **Intelligent Retries:** Employing advanced logic, this system aims to convert failed payment attempts into successes by optimizing the timing of retries. This method effectively decreases involuntary churn due to payment failures.

* **Manual Collection:** Allows merchants to manually intervene and attempt to collect payment on failed invoices, offering a direct path to address and resolve payment issues.

* **Other:** Invoices that are collected by all other methods not listed above, included backup payment method 

This dashboard empowers you with actionable insights into the effectiveness of your dunning strategies and the impact on your revenue recovery efforts.

<Image alt="Dunning Summary" align="center" width="80% " border={true} src="https://files.readme.io/321b7d1-Dunning_Summary.png">
  Dunning Summary
</Image>

<Image alt="Invoice Revenue" align="center" width="80% " border={true} src="https://files.readme.io/1d9cccf-Invoice_Revenue_.png">
  Invoice Revenue
</Image>

<Image alt="Invoice Counts" align="center" width="80% " border={true} src="https://files.readme.io/866f6d4-Invoice_Counts.png">
  Invoice Counts
</Image>

By having a clear understanding of the Dunning Recovery features, you can maximize their usage and significantly reduce involuntary churn, thereby enhancing your revenue recovery.
