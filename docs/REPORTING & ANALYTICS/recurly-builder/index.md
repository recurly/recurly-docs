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

- Users must have Analytics user role permission.

### Definition

The Explore feature is a dynamic, versatile, and powerful tool that provides a custom view of your organization's data. It transforms raw data into insightful and actionable information, catering to a wide array of data needs. From transaction details to account information, and from credit card specifics to various other fields, Explore allows you to deeply analyze your Recurly data.

The Workbook Agent accompanies every Explore session. Ask it plain-language questions and it will identify the relevant fields, construct the query, and return results or a chart. You can refine results conversationally or switch to the field picker for manual control.

# Key benefits

- **Customizable reports for actionable insights**: Recurly Explore provides flexible report-building capabilities, allowing you to create custom reports tailored to your specific business needs.
- **Comprehensive data views for deep analysis**: From accounts to transactions, Explore offers predefined data views, enabling you to analyze every aspect of your Recurly data.
- **Optimized decision-making through detailed metrics**: Use dimensions and measures to uncover patterns and make informed decisions that enhance business performance.
- **AI-assisted analytics**: Use the Workbook Agent to ask data questions in plain language. The agent interprets your question, selects the relevant fields, and returns a result set or chart.

# Key details

## Explore interface

The Explorer is divided into three areas:

| Interface Area              | Description                                                                                                                                                                                                                  |
| --------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Left panel -Workbook        | Agent Ask natural-language questions about your invoice data. The agent suggests fields and runs queries on your behalf.                                                                                                     |
| Center panel - Field picker | Browse and search the full field catalog. Fields are grouped by topic. Click any field to add it to your active query. Use the In-use filter to see only selected fields.                                                    |
| Right panel - results area  | Toggle between Results (table view), Chart (visualization), or Both. Use the Options tab to configure axes, grouping, and chart type. Click Preview to run a sample query and verify your field selection before committing. |


<Image src="https://files.readme.io/69c5288cf91e6fd87bde330738bd87315b96bf3ad235a6255de9920e5ae4838b-image.png" align="center" border={true} />


### Using the Workbook Agent

The Workbook Agent is the fastest way to start an analysis. Type a question in the text box at the bottom of the left panel and press Enter (or click the send icon).

**Example prompts:**

- &#x20;“Show me all failed transactions in the last 7 days grouped by failure reason”
- “What is the total transaction volume by country this month?”
- &#x20;“Which credit card types have the highest decline rates?”
- &#x20;“List transactions flagged for fraud in the past 30 days”
- “Break down successful transactions by plan and subscription state”

  ![](https://files.readme.io/2b46f6b413106f780ea6650e6320f24661730c8a142c3ae7dbc64c18b667a9cc-image.png)

<br />

<br />

<br />

**Switching between Agent and manual mode**

You can use the Agent and the field picker together. After the agent populates a query, you can add or remove fields manually using the center panel. Changes are reflected immediately in the results view.

### Opening an existing report

1. Click the **yellow Recurly logo** in the upper left corner of the Explore


<Image src="https://files.readme.io/876fbccfd3e5c64960151b19b40148fb6688a7320eea40e9af93909becda1147-image.png" align="left" width="200px" border={true} />


<br />


<Image src="https://files.readme.io/fd6030aad81cb48304317f0583221f7df52b0df245f6ced971bf8d3103c5e81f-image.png" align="center" width="200px" border={true} />


2. Either go to **My documents** or the **Hub&#x20;**&#x74;o access saved reports. My documents stores your private personal data reports and folders while the Hub is the shared workspace for the entire site.
3. Click on the folder or report to open
4. Select **File-Edit** or click th&#x65;**&#x20;Edit button** in the upper right corner to edit the report.
5. Save your updates by selecting **File-Save**.

### Run/refresh a report with or without cache

1. Once in an existing report, you can run or refresh the report with or without cache by selecting the View menu


<Image src="https://files.readme.io/2b464a13cc19f2e8b6d97c2c3b14107122f810eadc506f0bdda21000c3e77450-image.png" align="center" width="200px" border={true} />


<br />

- **Refresh** - this re-runs or refreshes the report against previously saved data. As an example, If you (or a colleague) ran the exact same query with the same filters, sorts, and fields within the last 6 hours, Explore will instantly load those pre-saved results. It only sends a new query to your data source if the cache has expired or if filters, sorts, and/or fields are changed in the report.
- **Refresh w/o cache** - this bypasses the stored query results for the report and sends a direct query to your data source to pull live, up-to-the-minute data.

### Creating a new report

1. Browse and search the full field catalog. Fields are grouped by data topic.&#x20;
2. Click any field to add it to your active query. Use the In-use filter to see only selected fields.
3. Toggle between Results (table view), Chart (visualization), or both.&#x20;
4. Use the Options tab to configure axes, grouping, and chart type.&#x20;

### Creating a custom field

Creating custom fields allows for more personalized reporting. Use custom fields to create formulaic calculations based on existing fields.&#x20;

1. Fields can be created by clicking on ”+ Add Field” menu at the bottom of the field list. Field can also be adjusted by right-clicking on any existing field and selecting ‘Edit.’
2. Right click on any existing dimension and choose an aggregation (e.g. count distinct, sum, average, min, max). This will automatically create a new custom measure that appears in the field picker.
3. Click **Add** to save the field

<br />


<Image src="https://files.readme.io/a85fd88769b0f602d2cb52ad356f6a88c91a566447a030eedbfb3fc09ac5970c-image.png" align="center" width="400px" border={true} />


### Saving a new report

To save a report:

1. In the workbook, click **File > Save**.
2. Give the document a Name and an optional Description
3. Use the Locations browser to find and select the folder you want to save the document to. The document can be moved after saving if needed.
4. Click **Save** to save the document.


<Image src="https://files.readme.io/41965e12577df2175ead2737ac62f6672243bc0a79b460e3204b6eb9dfcd49d7-image.png" align="center" width="500px" border={true} />


<br />

### Creating & editing dashboards

- To create a dashboard, click the + Dashboard button in the top right corner of the document.&#x20;
- You can add, modify, resize, and remove elements in the dashboard. Your changes will be automatically saved while you work.
- Dashboards can include various elements like visualizations, headers, filters, and texts.
- After customizing your dashboard, download it for further use. This feature allows you to compile multiple reports and visualizations into one cohesive view, ideal for sharing with your team.

<br />
