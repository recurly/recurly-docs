---
title: Dashboard
excerpt: >-
  Experience real-time business insights with dynamically updating widgets and
  illustrative charts on the Analytics Dashboard, your window to performance
  metrics.
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

The Analytics Dashboard serves as your window into the vital performance metrics, dynamically updating widgets, and illustrative charts, providing a succinct view of your business's pulse. It's designed to furnish you with real-time insights; the widgets on this dashboard facilitate data refresh. A dedicated widget at the bottom of the dashboard allows you to verify the timestamp of the latest data update, ensuring you're always informed and never missing out on crucial information.

# Analytics dashboard overview

The Overview Dashboard is neatly segmented into three sections: Customers, Subscriptions, and Revenue, each tailored to provide a comprehensive understanding of different business facets. The intuitive user interface hosts a variety of widgets, each offering a suite of common features for a seamless user experience.  
Below you can find a summary of the interaction tools.

<br />

**Vertical Ellipses**:

Present on widgets featuring charts or tables, the vertical ellipses unveil a dropdown menu offering a host of options:

* When you click the vertical ellipse on a widget, you can either download its data or clear the cache to refresh the widget's content.
* Clicking the vertical ellipse on a column in a table opens options to download data, clear cache and refresh displayed data, or auto-size/resize columns.

**Charts and Legends**:

Articulating data through bar, line, and pie charts, the widgets on this dashboard encapsulate various metrics including customer, subscriber, subscription, plans, and revenue totals, delineated by time and date ranges. Color-coded information comes with a handy legend on the widget, clarifying the color-value correlation.

* Clicking on a point in a line chart or a specific color on a bar or pie chart reveals the corresponding timeframe and value in hover text.
* By clicking the corresponding color in the legend, you can toggle the visibility of that specific line, bar, or pie chart segment on the widget. Clicking the color again restores the data display.

# Customers section overview

The Customers Section on the dashboard offers a deep dive into key subscriber metrics through five insightful widgets, as illustrated in the following screenshot:

![Customer Dashboard Segment](https://files.readme.io/58793ed-dashboard_customers_section.png)

**1. Active Subscribers:**

* Reflects the count of unique subscriptions with at least one active subscriber. This encompasses subscribers in a trial phase as well as those who have canceled but haven't churned out yet.

**2. Subscriber Churn Rate:**

* Represents the percentage of subscribers who churned in the last month, calculated against the number of active subscribers at the start of that month.

**3. Subscriber Lifetime Value (LTV):**

* Estimates the lifetime value of each subscriber based on discounted cash flows, accounting for future revenue risks and the time value of money. The formula is articulated as follows:

> ✅ **Subscriber LTV = ARPS (1 + d) / d + Churn Rate**
>
> **ARPS** = Average revenue per subscriber (Monthly Recurring Revenue \{MRR} at the end of the month/ number of active subscribers at the end of the month). A subscriber is anyone with at least 1 subscription.
>
> **Churn rate** = Calculation used above.
>
> **d** = discount rate. This constant is commonly used when looking at future revenue. It takes into account market, financial and other risks as well as the time value of money. Using a discount rate helps you understand: In today’s dollars, what future dollars are worth? Recurly uses a discount rate of 1%.
>
> →**Note:** Recurly uses a discount rate of 1% because this is a generally accepted value for SaaS companies. (see: <a href="https://www.forentrepreneurs.com/discount-rate-for-dcf/" target="_blank">[https://www.forentrepreneurs.com/discount-rate-for-dcf/](https://www.forentrepreneurs.com/discount-rate-for-dcf/)</a>)
>
> **Example:**
>
> Company X has an MRR at the end of August of $555,000. This is found in the Monthly Recurring Revenue Report.
>
> Company X has 5,000 total subscribers at the end of August. This is found in the Subscribers Report.
>
> Company X has a Subscriber Churn rate in August of 3.5%. This is found on the Dashboard. The average Subscriber LTV of Company X's subscribers can be calculated as such: Subscriber LTV = ($555,000/ 5,000) (1 + 0.01) / (0.01 + .035), which equals ~$904

**4. Net Subscriber Change:**

* Demonstrates the net subscriber change, formulated as: new subscriber + returning subscriber + churned subscriber.
  * Click on any point on the line to unveil net subscriber totals for the chosen timeframe in hover text.
  * Click on color-coded sections of any bar to display totals for the selected timeframe in hover text, with the color correlations elucidated in the legend below the chart.

**5. Subscriber Churn Rate (Detailed):**

* Illustrates the churn rate over a selected date range. It is noteworthy that the churn rate won't be computed if the subscription duration doesn't span a full month.
  * Click on any point along the line to view churn rates for the selected timeframe in hover text.
  * Use the vertical ellipse to clear cache and refresh for updated data in the Subscriber Data widget at the dashboard's bottom.

Each of these widgets is instrumental in understanding and improving subscriber engagement and retention. By utilizing the interactive features, you can glean actionable insights and refine your strategies for better customer satisfaction and business growth.

# Subscriptions section overview

The Subscriptions section provides critical insights into the various subscription plans through three engaging widgets, illustrated in the screenshot below:

![Subscriptions Dashboard Segment](https://files.readme.io/505bedc-Dashboard_subscriptions_section.png)

### **1. Total Subscriptions:**

* Displays the total number of subscriptions for your top five plans as of the most recent update.
  * Toggle the arrow in the first column to arrange the data in either ascending or descending order.
  * Click on the vertical ellipse in the second column for options to freeze or copy values, or to auto size or resize the columns.
  * Utilize the vertical ellipse→clear cache and refresh action in the Subscriptions Data widget at the dashboard's bottom to view the last update timestamp.

### **2. Top 5 Plans by Subscriptions (Pie Chart):**

* Presents a pie chart illustrating the distribution of subscriptions across the top five plans over the last six months.
  * Click on a color-coded segment to either exclude that plan from the calculation or to unveil hover text showing the total number of subscriptions for the plan.
  * Access the vertical ellipse→clear cache and refresh action in the Plans Data widget at the dashboard's bottom to check the last update timestamp.

### **3. Top 5 Plans by Subscriptions (Line Chart):**

* Depicts the trend of subscriptions across the top five plans over the last six months through a line chart.
  * Click on any point along the lines to view total subscriptions for the selected timeframe in hover text.
  * Employ the vertical ellipse→clear cache and refresh action in the Plans Data widget at the dashboard's bottom to verify the last update timestamp.

# Revenue section overview

The Revenue section encompasses four widgets capturing diverse revenue metrics, as shown in the screenshot below:

![Revenue Dashboard Segment](https://files.readme.io/c6d3857-dashboard_revenue_section.png)

### **1. Average Revenue per Customer:**

* Calculates the average revenue per customer by dividing the sum of all billings (covering both recurring and nonrecurring subscriptions) in the previous month by the count of unique customers making payments.

### **2. Current Monthly Recurring Revenue (MRR):**

* Calculates the expected monthly revenue by adding up charges from active subscriptions and adjusting it for the month, shown in the site's main currency.

### **3. Recovered Revenue:**

* Represents the revenue recovered by Recurly that otherwise would have been lost due to failed credit card transactions.

### **4. Net Billings Month to Date:**

* Compares the net billings for the ongoing month to the preceding month.
  * Click on any point in the color-coded line to reveal details for the selected timeframe in hover text.
  * Toggle the color-coded points in the legend at the widget's bottom to hide or show lines in the widget representing net billings for the current and previous months.
  * Use the vertical ellipse→clear cache and refresh action in the Billing Data widget at the page's bottom to check the last update timestamp.

Each widget in the Subscriptions and Revenue sections is designed to deliver actionable insights, aiding in comprehensively understanding and augmenting your subscription and revenue streams. By leveraging the interactive features, you can work towards making informed decisions and driving substantial growth for your business.
