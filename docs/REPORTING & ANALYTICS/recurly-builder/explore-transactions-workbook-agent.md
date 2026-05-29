---
title: Explore - Transactions & Workbook Agent
excerpt: >-
  The Transactions Explore feature is a is an interactive analytics tool that
  lets you slice and filter transaction-related data across payment
  transactions, fraud signals, geographic data, and subscription activity. Use
  the Workbook Agent to ask natural-language questions and surface actionable
  payment insights.
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

## Required plan

This feature **may not be included** in the Starter or Pro plans. If you are interested, please contact [Recurly Sales](https://recurly.com/demo/contact-sales/) to discuss upgrade options.

### Prerequisites

- Users must have Analytics user role permission.

## Definition

The transactions Explore feature is a dynamic, versatile, and powerful tool that provides a custom view of your organization's data. It transforms raw data into insightful and actionable information, catering to a wide array of data needs. This feature is a flexible way to query transaction outcomes, monitor fraud signals, analyze geographic payment patterns, and correlate transaction data with subscription and account records

The Workbook Agent accompanies every Explore session. Ask it plain-language questions and it will identify the relevant fields, construct the query, and return results or a chart. You can refine results conversationally or switch to the field picker for manual control.

# Key benefits

- **Detailed transaction insights for better decision-making**: Explore provides a comprehensive view of all transactions, helping you gain deeper insights into your payment processes.
- **Customizable reports for enhanced gateway analysis**: Easily build tailored reports to track gateway activity, failures, and payment trends, optimizing your financial operations.
- **Streamlined fraud monitoring through Kount integration**: Gain a clear view of multiple fraud line items with seamless Kount fraud integration data.
- **AI-assisted analytics**: Use the Workbook Agent to ask data questions in plain language. The agent interprets your question, selects the relevant fields, and returns a result set or chart.

# Key details

The Transactions Explore includes **all** transactions processed through a gateway, along with corresponding invoices and line items. It does not include all invoices or charge items. Multiple transactions may be associated with a single invoice, and multiple lines may be included for a given transaction when multiple fraud line items are returned from a Kount fraud integration.

This tool is useful for building reports related to gateway activity, failures, and payment information. It is **not** intended for accounting purposes, which are better handled by the invoices Explore.

## Explore interface

The Explorer is divided into three areas:

| Interface Area              | Description                                                                                                                                                                                                                  |
| --------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Left panel -Workbook        | Agent Ask natural-language questions about your invoice data. The agent suggests fields and runs queries on your behalf.                                                                                                     |
| Center panel - Field picker | Browse and search the full field catalog. Fields are grouped by topic. Click any field to add it to your active query. Use the In-use filter to see only selected fields.                                                    |
| Right panel - results area  | Toggle between Results (table view), Chart (visualization), or Both. Use the Options tab to configure axes, grouping, and chart type. Click Preview to run a sample query and verify your field selection before committing. |


<Image src="https://files.readme.io/26bc849b2829527adb5b7c95cefc555b6c50b03e68b2b68ee44ee4b027b03743-image.png" align="center" width="700px" border={true} />


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

### Creating a new explorer

1. Browse and search the full field catalog. Fields are grouped by data topic.&#x20;
2. Click any field to add it to your active query. Use the In-use filter to see only selected fields.
3. Toggle between Results (table view), Chart (visualization), or both.&#x20;
4. Use the Options tab to configure axes, grouping, and chart type.&#x20;

### Available data

The field picker organizes all available dimensions and metrics by topic. Each topic maps to a set of underlying data entities:

| Data                    | Description                                                                                              |
| :---------------------- | :------------------------------------------------------------------------------------------------------- |
| Billing Info            | Payment method details, billing address and card metadata associated with accounts                       |
| Accounts                | Account-level attributes including account code, email, address, name, etc                               |
| Business Entities       | Legal entity data for multi-entity merchants, including entity name and tax region.                      |
| Country                 | Country-level geographic dimensions for filtering and grouping transaction data by region.               |
| Credit Card             | Card brand, card type (debit/credit), issuing bank, last four digits, and expiration data.               |
| Dunning Info            | Retry attempts, dunning state, and communication timing for failed payment recovery.                     |
| Fraud Infos             | Fraud risk scores, decision outcomes, and signals returned by Recurly’s fraud detection layer.           |
| Invoice Line Items      | Individual charges and credits at the line level, including unit amounts, quantities, and product codes. |
| Invoices                | Invoice totals, state (open, collected, failed, voided), currency, and dates.                            |
| Operations              | Internal processing metadata including gateway response codes and operation type.                        |
| Plans                   | Plan codes, names, intervals, and pricing tiers.                                                         |
| Subscriptions           | Subscription state, start/end dates, trial info, and associated plan and add-on metadata.                |
| Transaction Statuses    | Standardized transaction outcome states: success, declined, error, voided, and more.                     |
| Transaction\_Geo (maps) | Geographic coordinates and region data for map-based transaction visualizations.                         |
| Transactions            | Core transaction fields: amount, currency, type (purchase, refund, void), gateway, and timestamp.        |

### Tips & best practices

- Use Preview before adding many fields to confirm the data shape and avoid slow load times on large result sets.
- The In-use toggle in the field picker narrows the view to your current selection, making it easier to audit what’s included before running a query.
- Combine Transaction Statuses with Credit Card or Country topics to identify regional or card-type-specific decline patterns.
- Use the Fraud Infos topic alongside Transactions to correlate fraud signals with transaction outcomes — useful for investigating dispute spikes.
- For high-volume date ranges, start with aggregated metrics (totals, counts, rates) before drilling into row-level detail to keep performance fast.
- Save frequently used queries as a Dashboard using the + Dashboard button in the top-right corner so teammates can access them without rebuilding.
- The Workbook Agent works best with scoped, specific questions. Include a timeframe, a transaction outcome (e.g. failed, declined), and at least one grouping dimension for the most precise results.

### Saving a new explore

To save an explore:

1. In the workbook, click **File > Save**.
2. Give the document a Name and an optional Description
3. Use the Locations browser to find and select the folder you want to save the document to. The document can be moved after saving if needed.
4. Click **Save** to save the document.


<Image src="https://files.readme.io/41965e12577df2175ead2737ac62f6672243bc0a79b460e3204b6eb9dfcd49d7-image.png" align="center" width="500px" border={true} />


<br />

<br />
