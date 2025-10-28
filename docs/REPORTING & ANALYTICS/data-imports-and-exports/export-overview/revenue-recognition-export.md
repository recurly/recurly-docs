---
title: Revenue recognition schedules - export
excerpt: Unlock revenue insights with the Revenue Recognition Schedules export feature.
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

This feature is no longer available for activation.

# Definition

Recurly’s Revenue Recognition Schedules export is your gateway to detailed revenue amortization data. This legacy solution, although no longer available for new purchases, continues to aid a small subset of users in listing all schedules from each charge or credit alongside vital revenue amortization details. Visit our [Legacy Solution](https://docs.recurly.com/recurly-revrec/docs/recurly-revenue-recognition-legacy) page for more insight and consider exploring the new [Recurly Revenue Recognition](https://docs.recurly.com/recurly-revrec/docs/overview-revenue-recognition)   for a more robust experience.

Ensure to configure the Revenue Recognition feature properly to find this export in your admin console, exclusive to sites with this feature enabled.

<Image border={false} src="https://files.readme.io/b36c7d6c24073e3e25e1c58217201ceaf5cda85802a55b1c244976b39c2f2080-image.png" />

# Filters

### Versions Filter

* The Versions filter allows you to select the version that is most appropriate for your needs. This is based on the version changelog at the bottom of this page.

### Invoice Type Filter

* **All** -  accommodates every invoice generated on your Recurly site, regardless of the status.
* **Charge** - encompasses charge invoices awaiting a payment attempt.
* **Credit** - denotes credit invoices.

e line items persist in the account history, with the owed balance cleared from the account.

### Time Range Filter

**Detail**: Harness the invoice_created_at date column in the export to display all schedules stemming from invoices conceived within the chosen timeframe. Depending on a specific time range selected in the dropdown, the Start Date and End Date will automatically update. You can also choose "Between..." in the dropdown, which will allow you to enter a customized date range.

# Exports table

<HTMLBlock>{`
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Download Button</title>
    <style>
        .download-button {
            display: inline-block;
            padding: 5px 10px;
            text-align: center;
            text-decoration: none;
            color: #1C2833FF; 
            background-color: #F8F8F8FF; 
            border-radius: 5px;
            font-weight: normal;
            transition: background-color 0.5s ease, transform 0.3s ease;
          	transition: 0.4s !important;
            font-family: 'Proxima-nova', Arial, sans-serif;
            max-width: 100%; 
        }

        .download-button:hover {
            background-color: #FFFFFFFF; 
            transform: scale(1.02); 
        }
      	a:hover {
          	color: #1C2833FF;
          	text-decoration: underline !important;
        }
      </style>
</head>
<body>
    <a href="https://docs.google.com/spreadsheets/d/1U0_Wl_NMScJqKBZoBKMmQnybmLEr0gFi6r7dfNiP9Qc/export?format=xlsx" class="download-button">Download our complete export schema</a>
</body>
</html>
`}</HTMLBlock>

To help you identify and organize information effectively, the export provides a structured table that contains the following columns:

| <span id="Id">Id</span>                                             | Example                          | Description                                                                                                                                                                                                                                                               |
| :------------------------------------------------------------------ | :------------------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| <span id="revenue_schedule_id">revenue_schedule_id</span>           | 224934254870915                  | The unique identifier of the revenue schedule.                                                                                                                                                                                                                            |
| <span id="invoice_number">invoice_number</span>                     | 192880                           | The invoice number visible in the Recurly UI.                                                                                                                                                                                                                             |
| <span id="invoice_date">invoice_date</span>                         | 2017-06-01 00:00:00 UTC          | The date when the invoice was created.                                                                                                                                                                                                                                    |
| <span id="invoice_state">invoice_state</span>                       | paid, processing, open, failed   | The current state of the invoice.                                                                                                                                                                                                                                         |
| <span id="account_code">account_code</span>                         | 11734                            | The account code being charged for this invoice.                                                                                                                                                                                                                          |
| <span id="accounting_code">accounting_code</span>                   | monthly_fee                      | Internal accounting code for a specific invoice line item. This value will only populate if you define an accounting code for the line item. Accounting codes can be defined for all line items.                                                                          |
| <span id="line_item_id">line_item_id</span>                         | 3a6ae2555a2e2a76c077604bf5b90457 | Unique internal identifier for the adjustment. Also referred to as line_item_uuid or adjustment_uuid in other exports.                                                                                                                                                    |
| <span id="line_item_start_date">line_item_start_date</span>         | 2017-06-01 12:00:00 UTC          | Bill cycle start date for a specific invoice line item. Equivalent to line_item_start_date in the deprecated Invoices export.                                                                                                                                             |
| <span id="line_item_end_date">line_item_end_date</span>             | 2017-07-01 12:00:00 UTC          | Bill cycle end date for a specific invoice line item. This date will not exist for custom charges (one-time).                                                                                                                                                             |
| <span id="origin">origin</span>                                     | plan, add_on, credit, charge     | The original source for a line item. A credit created from an original charge will have the value of the charge's origin.                                                                                                                                                 |
| <span id="days">days</span>                                         | 31                               | The number of days between line_item_start_date and line_item_end_date.                                                                                                                                                                                                   |
| <span id="amount_per_day">amount_per_day</span>                     | 4.88                             | The total amount divided by the number of days.                                                                                                                                                                                                                           |
| <span id="total_amount">total_amount</span>                         | 1000                             | The total amount of the charge to be recognized for this schedule, in other words, "subtotal after discounts".                                                                                                                                                            |
| <span id="currency">currency</span>                                 | USD                              | The currency of the line item.                                                                                                                                                                                                                                            |
| <span id="schedule_type">schedule_type</span>                       | at_range_start, evenly           | The method in which revenue is recognized for that schedule, as defined in the plan settings for revenue recognition.                                                                                                                                                     |
| <span id="revenue_recognition_date">revenue_recognition_date</span> | 2017-06-05 00:00:00 UTC          | The date revenue is recognized. Only populated if the schedule type is at_range_start or at_rate_end.                                                                                                                                                                     |
| <span id="deferred_revenue_balance">deferred_revenue_balance</span> | evenly                           | Reflects the total remaining deferred revenue to be recognized as of the date the export is requested.                                                                                                                                                                    |
| <span id="arrears">arrears</span>                                   | 0                                | The portion of the line item that applies to the past, i.e., before the time range "start date".                                                                                                                                                                          |
| <span id="month_1">month_1</span>                                   | 20                               | The total amount recognized in a specific month. Note that the first month will be the current month.                                                                                                                                                                     |
| <span id="month_2">month_2</span>                                   | 20                               | The total amount recognized in a specific month. The second column will be the month after the current month.                                                                                                                                                             |
| <span id="month_3_etc">month_3, etc.</span>                         | 20                               | The total amount recognized in a specific month. There will be a column for each month after the current month, creating 12 columns of months in total.                                                                                                                   |
| <span id="future_revenue">future_revenue</span>                     | 90                               | Revenue to be recognized in the future past 12 months from the current month.                                                                                                                                                                                             |
| <span id="invoice_origin">invoice_origin</span>                     | purchase, refund                 | The event that created the invoice. Invoices issued before the Credit Invoices feature was enabled on your site will have either purchase or refund as the value. Once Credit Invoices is enabled, new origins like renewal, immediate_change, and write_off will appear. |

### **Version 2 - 11/1/2018**

* Modification to the arrear and deferred revenue calculations.
