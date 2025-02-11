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

Recurly’s Revenue Recognition Schedules export is your gateway to detailed revenue amortization data. This legacy solution, although no longer available for new purchases, continues to aid existing users in listing all schedules from each charge or credit alongside vital revenue amortization details. Visit our [Legacy Solution](https://docs.recurly.com/docs/revenue-recognition#legacy-solution) page for more insight and consider exploring the new [Recurly Revenue Recognition](https://dash.readme.com/project/reference-docs/v1.0/docs/revenue-recognition) for a more robust experience.

Ensure to configure the [Revenue Recognition](https://docs.recurly.com/docs/revenue-recognition) feature properly to find this export in your admin console, exclusive to sites with this feature enabled.

# Filters

### Invoice Status Filter

#### All

- **Overview**: Accommodates every invoice generated on your Recurly site, regardless of the status.

#### Charge

- **Overview**: Encompasses charge invoices awaiting a payment attempt.-

#### Credit

- **Overview**: Denotes credit invoices.

e line items persist in the account history, with the owed balance cleared from the account.

### Time Range Filter

**Detail**: Harness the invoice_created_at date column in the export to display all schedules stemming from invoices conceived within the chosen timeframe.



# Exports table

[block:html]
{
  "html": "<!DOCTYPE html>\n<html lang=\"en\">\n<head>\n    <meta charset=\"UTF-8\">\n    <meta http-equiv=\"X-UA-Compatible\" content=\"IE=edge\">\n    <meta name=\"viewport\" content=\"width=device-width, initial-scale=1.0\">\n    <title>Download Button</title>\n    <style>\n        .download-button {\n            display: inline-block;\n            padding: 5px 10px;\n            text-align: center;\n            text-decoration: none;\n            color: #1C2833FF; \n            background-color: #F8F8F8FF; \n            border-radius: 5px;\n            font-weight: normal;\n            transition: background-color 0.5s ease, transform 0.3s ease;\n          \ttransition: 0.4s !important;\n            font-family: 'Proxima-nova', Arial, sans-serif;\n            max-width: 100%; \n        }\n\n        .download-button:hover {\n            background-color: #FFFFFFFF; \n            transform: scale(1.02); \n        }\n      \ta:hover {\n          \tcolor: #1C2833FF;\n          \ttext-decoration: underline !important;\n        }\n      </style>\n</head>\n<body>\n    <a href=\"https://docs.google.com/spreadsheets/d/1U0_Wl_NMScJqKBZoBKMmQnybmLEr0gFi6r7dfNiP9Qc/export?format=xlsx\" class=\"download-button\">Download our complete export schema</a>\n</body>\n</html>\n\n"
}
[/block]


To help you identify and organize information effectively, the export provides a structured table that contains the following columns:

| <span id="Id">Id</span>                                             | Example                          | Description                                                                                                                                                                                                                                                               |
| ------------------------------------------------------------------- | -------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
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

- Modification to the arrear and deferred revenue calculations.