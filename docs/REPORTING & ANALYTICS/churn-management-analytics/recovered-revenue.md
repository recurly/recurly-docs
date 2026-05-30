---
title: Recovered revenue
excerpt: >-
  Boost your bottom line with Recurly's Recovered Revenue dashboard. Track,
  analyze, and optimize your strategies to minimize involuntary churn and
  maximize recovered revenue.
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

The **Recovered Revenue** dashboard highlights revenue reclaimed through Recurly’s tools, focusing on declined invoices and recovery strategies.

1. **Expiration Date Changes** – Automatically updates expiration dates for continuous invoices.
2. **Account Updater** – Refreshes payment details to prevent transaction failures.
3. **Intelligent Retries** – Strategically retries failed invoices to maximize recovery.
4. **Backup Payment Method** – Automatically retries failed payments using a backup payment method.
5. **Customer Updates** – Allows customers to update their payment method to resolve failed payments.
6. **External Recovery** – Recovers failed invoices using other systems outside of Recurly.
7. **Forced Recovery** – When merchants manually initiate a collection attempt on a past-due invoice.

# Recovered Revenue

The Recovered Revenue dashboard is a robust tool that provides insights into how much revenue you have recovered through Recurly's system. By monitoring involuntary churn from declined invoices, the dashboard uses three main mechanisms - Expiration Date Changes, Account Updater, and Dunning Retries, to ensure the highest rate of paid invoices.

**Expiration date changes:** This mechanism updates the expiration date on the account's billing information, allowing continuity of invoices and subscriptions. This reduces the likelihood of service disruption for the customer and prevents potential revenue loss.

**Account updater:** If enabled, this tool checks for credit card updates with providers before a subscription renewal, or when a one-time invoices or re-subscribe sign-up results in a hard decline. By staying up-to-date with customer's payment details, this tool aids in reducing failed invoices and maintaining a steady revenue stream.

**Intelligent retries:** This is Recurly's sophisticated retry logic that maximizes the likelihood of turning failed invoices into successful ones. By strategically timing the retries, it significantly reduces involuntary churn caused by failed invoices.

**Backup payment method:** Our Backup Payment Method feature acts as your safety net, ensuring uninterrupted service for your customers even when their primary payment method fails. By securely storing an alternative payment option, it safeguards your revenue stream and minimizes disruptions.

**Customer Updates:** When a customer updates their payment method, Recurly will attempt collection on the failed automated invoice. Customers may be prompted to update their payment method via Recurly's dunning emails, or other notifications built into your application. This data does not include manual invoices.

**External Recovery:** When other systems successfully collect on a failed invoice, and send an update to Recurly.

## Features and benefits

The Recovered Revenue dashboard has an intuitive layout, presenting you with an at-a-glance view of the revenue key performance indicators, a detailed bar chart showing the recovered revenue, and a chart detailing the revenue recovered by each of Recurly's processes. This overview gives you a comprehensive understanding of your business's health and Recurly's impact on your revenue recovery.

You are able to filter on the invoice creation date, or the invoice closed date, to track the success of automated invoice recovery. You are also able to view the amount recovered based on specific currencies, where the default will include all invoices, converted to your primary currency. When viewing the time graph, note that the current month will start off low, and increase as the month progresses, and invoices are recovered.

1. **Recovered revenue KPI:** These indicators offer a real-time snapshot of your revenue dynamics. They help you measure the effectiveness of your revenue recovery strategies by comparing your current payment amounts with totals for the last month, previous month, three months ago, and a year ago. This enables you to identify trends and track progress, supporting informed decisions to proactively manage involuntary churn as you track the amount of revenue recovered over time, and compared to last year.


<Image src="https://files.readme.io/82bf6559f3b90ad2b458c0d0e513079879d6d33d951e0050a89d5dd077bc7baa-image.png" align="center" border={true} />


<br />

2. **Recovered Revenue chart:** This bar chart visualizes the revenue that Recurly has helped you recover by minimizing involuntary churn from declined automated invoices. It allows you to see at a glance the financial impact of Recurly's services, making it a powerful tool for forecasting and resource allocation. These charts are displayed as a total revenue saved, or a count of invoices recovered.


<Image src="https://files.readme.io/40dfc0fa1fe13c6e9c395906a99fab9b12cc298514d48502e78a8e6915813e60-image.png" align="center" border={true} />


<br />

3. **Recovered Revenue Detail:** This detailed breakdown gives you insights into the processes that drive revenue recovery. By displaying the amount recovered through each process (Expired Card Management, Account Updater, Intelligent Retries, Backup Payment Method, Customer Updates, and External Recovery), it enables you to see which tools are most effective. This knowledge empowers you to focus your efforts on the most productive areas, thereby improving recovery rates, enhancing service continuity, and fostering customer retention. These charts are displayed as a total revenue saved, or a count of invoices recovered.


<Image src="https://files.readme.io/1b47403d9847c0becfa5fab2226f73ff73c118f2aae3fb1490013271d45ad266-image.png" align="center" border={true} />


By having a clear understanding of the Recovered Revenue features, you can maximize their usage and significantly reduce involuntary churn, thereby enhancing your revenue recovery.

## Related dashboards

Continue to learn more about how Recurly helps you prevent churn and your recovered invoice rate by navigating to the related dashboards. Also review your dunning campaign strategy to continue to increase your dunning recoveries.


<Image src="https://files.readme.io/91d2dd4-Screen_Shot_2024-01-22_at_7.58.05_PM.png" align="center" />


<br />
