---
title: Explore overview
excerpt: >-
  Explore provides a new powerful and flexible way to visualize your
  organization’s Recurly data. This report builder includes insight into your
  transactions, invoices, accounts, and credit card details, in addition to many
  others.
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

This feature is only available to customers on the Elite subscription plan. To upgrade to this plan, please contact your Recurly account manager or reach out to [support@recurly.com](mailto:support@recurly.com) for more details.

### Prerequisites

* Users must have Analytics user role permission.

### Definition

The Explore feature is a dynamic, versatile, and powerful tool that provides a custom view of your organization's data. It transforms raw data into insightful and actionable information, catering to a wide array of data needs. From transaction details to account information, and from credit card specifics to various other fields, Explore allows you to deeply analyze your Recurly data.

# Key benefits

* **Dimensions and measures**: These are the building blocks used to assemble custom reports. Dimensions (in black text) are qualitative variables such as names, geographical data, and dates. They represent the categories you want to analyze. Measures (in orange text) are quantitative variables like counts, totals, or averages. These provide the numerical metrics you're interested in for each category identified by dimensions. With a range of dimensions and measures, Recurly Explore allows you to create custom reports tailored to your specific needs.
* **Data views**: Recurly Explore offers a variety of predefined data views to help jumpstart your exploration of data.


# Key details

## How to use Explore

### Selecting and removing data in Explore

To select a dimension or measure from the field selector on the left side of the page, click it to add it to the report and click again to remove it.

The left sidebar in Explore (refer to Invoices and Transactions sections for specific options) allows you to:

* **Search** for a field you'd like to use in your report.
* **Click** "All Fields" to see all available fields for your Recurly report.
* **Click** "In Use" to see which fields are currently in use. This view allows you to clear all fields and filters, or just the fields while keeping filters.
* **Hover** over a field to pivot/unpivot it, filter your report based on it, or view more details.
* To remove a dimension or measure, **click** the selected field in the left sidebar or use the "Remove" option from the relevant column's gear menu.
* **Pivot** your data when multiple dimensions are selected. Each value in the dimension becomes a column when pivoted.
* **Use** the “Totals” checkbox in the top right corner of your data viewer to see data summaries. Column and row totals are only available for measures and numerical data.

### Filtering data

Filtering data allows you to refine reports by specific conditions or criteria. You can apply filters to any dimension listed in the left toolbar by hovering over the dimension and selecting the "Filter by field" option. This opens the filter section, where you can specify your desired filter conditions.

For example, for time-based filters, you'll see a date range picker to define a specific timeframe. Numeric filters provide options like "equal to" or "greater than" for targeted data points.

<Image align="center" className="border" border={true} src="https://files.readme.io/39d22e7ea0abe16c4e4874e06f3de8a3347bef9ea427db50c1a9b7c73b28d424-Explore_1.png" />

Text attribute filters show a list of data values, which narrow down as you type in the search bar.

<Image align="center" className="border" border={true} src="https://files.readme.io/273f59d5e6cd3250e869431f83313c1ed6c01cdb50cafd12179e7ba3d5f1e558-explore2.png" />

You can also create filters based on custom expressions entered in the input field.

<Image align="center" className="border" border={true} src="https://files.readme.io/6f4c5d955c4196f1de45137101ba3651b3b91339bb86d7a793bc5690b116fc98-explore_3.png" />

You can create filters based on attributes specific to individual users or user groups, making it useful for tracking performance or analyzing team-specific metrics.

### Creating a custom field

Creating custom fields allows for more personalized reporting. Use custom fields to create formulaic calculations based on existing fields. Click the custom field option in the left navigation bar, input the fields you want to use in the formula, and generate targeted reports.

### Creating a report

To create a report, select relevant dimensions and measures from the left side of the page. Dimensions represent qualitative data (names, dates, geographical data), while measures provide quantitative data (counts, totals, averages).

For instance, to create a report showing the number of subscriptions by country and gateway type in the last three months, select the "Country" and "Transaction Gateway Type" dimensions and the "Total Subscriptions" measure. Filter by "Created At Date" and adjust the filter to "is in the past 3 months". Click "Run" to generate the report.

<Image align="center" className="border" border={true} src="https://files.readme.io/32e43479781ebc5717c5fcc2dc1e4312a14a86b04e4f8724d64dc0b0fa346b59-Screenshot_2024-10-24_at_9.07.32_AM.png" />

### Creating a visualization

Visualizations represent data graphically, making it easier to understand. To create a visualization, select a type from the visualization dropdown menu. Available types include Bar Gauge, Boxplot, Collapsible Tree, Map, Table, Timeline, and others.

Some visualizations may not apply to all data types. For example, a map visualization will only work if location data is present.

Once a visualization is selected, click “Edit” in the top right corner to customize it. Edit options include colors, sizes, labels, axes, and the addition of reference or trend lines.

### Saving a report to a dashboard and downloading data

After creating your report or visualization, save it by clicking the “Settings” button in the top right corner. You can either create a new dashboard or add your report to an existing dashboard.

<Image align="center" className="border" border={true} src="https://files.readme.io/a5818f19763e0ef6629a54c131a5f211458ee1721bc06b76185898190724615f-settings.png" />

Dashboards can be private or shared within your organization. You can also save reports as individual Looks (a single view or visualization of your data).

<Image align="center" className="border" border={true} src="https://files.readme.io/79d9d21ffc7ced940dbbac4c58ea7314993d71a77f51d9d9f241c9e60f484ae9-save_.png" />

Recurly Explore also allows you to download data in formats like TXT, Excel, CSV, JSON, HTML, Markdown, or PNG.

<Image align="center" className="border" width="70% " border={true} src="https://files.readme.io/2713e522c83fc77e47b75c8dea08d2ebdc81696b5621c6191e050d892bc1c21c-download.png" />

### Creating & editing dashboards

To create a dashboard, save your report or visualization first. Once saved, you can set dashboard filters for consistency across all reports and visualizations.

<Image align="center" className="border" width="70% " border={true} src="https://files.readme.io/341aceac6342bd7eeab0f0e144c4b734c1ed8d0165e1902b14764155cebcc111-dashboard_single_explore.png" />

Dashboards can include various elements like visualizations, headers, subheaders, paragraphs, and buttons linked to Explore URLs or external links.

After customizing your dashboard, download it for further use. This feature allows you to compile multiple reports and visualizations into one cohesive view, ideal for sharing with your team.
