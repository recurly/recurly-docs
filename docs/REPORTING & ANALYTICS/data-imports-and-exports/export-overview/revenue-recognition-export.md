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

* **Overview**: Accommodates every invoice generated on your Recurly site, regardless of the status.

#### Charge

* **Overview**: Encompasses charge invoices awaiting a payment attempt.-

#### Credit

* **Overview**: Denotes credit invoices.

e line items persist in the account history, with the owed balance cleared from the account.

### Time Range Filter

**Detail**: Harness the invoice\_created\_at date column in the export to display all schedules stemming from invoices conceived within the chosen timeframe.

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

<Table>
  <thead>
    <tr>
      <th>
        <span id="Id">Id</span>
      </th>

      <th>
        Example
      </th>

      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        <span id="revenue_schedule_id">revenue\_schedule\_id</span>
      </td>

      <td>
        224934254870915
      </td>

      <td>
        The unique identifier of the revenue schedule.
      </td>
    </tr>

    <tr>
      <td>
        <span id="invoice_number">invoice\_number</span>
      </td>

      <td>
        192880
      </td>

      <td>
        The invoice number visible in the Recurly UI.
      </td>
    </tr>

    <tr>
      <td>
        <span id="invoice_date">invoice\_date</span>
      </td>

      <td>
        2017-06-01 00:00:00 UTC
      </td>

      <td>
        The date when the invoice was created.
      </td>
    </tr>

    <tr>
      <td>
        <span id="invoice_state">invoice\_state</span>
      </td>

      <td>
        paid, processing, open, failed
      </td>

      <td>
        The current state of the invoice.
      </td>
    </tr>

    <tr>
      <td>
        <span id="account_code">account\_code</span>
      </td>

      <td>
        11734
      </td>

      <td>
        The account code being charged for this invoice.
      </td>
    </tr>

    <tr>
      <td>
        <span id="accounting_code">accounting\_code</span>
      </td>

      <td>
        monthly\_fee
      </td>

      <td>
        Internal accounting code for a specific invoice line item. This value will only populate if you define an accounting code for the line item. Accounting codes can be defined for all line items.
      </td>
    </tr>

    <tr>
      <td>
        <span id="line_item_id">line\_item\_id</span>
      </td>

      <td>
        3a6ae2555a2e2a76c077604bf5b90457
      </td>

      <td>
        Unique internal identifier for the adjustment. Also referred to as line\_item\_uuid or adjustment\_uuid in other exports.
      </td>
    </tr>

    <tr>
      <td>
        <span id="line_item_start_date">line\_item\_start\_date</span>
      </td>

      <td>
        2017-06-01 12:00:00 UTC
      </td>

      <td>
        Bill cycle start date for a specific invoice line item. Equivalent to line\_item\_start\_date in the deprecated Invoices export.
      </td>
    </tr>

    <tr>
      <td>
        <span id="line_item_end_date">line\_item\_end\_date</span>
      </td>

      <td>
        2017-07-01 12:00:00 UTC
      </td>

      <td>
        Bill cycle end date for a specific invoice line item. This date will not exist for custom charges (one-time).
      </td>
    </tr>

    <tr>
      <td>
        <span id="origin">origin</span>
      </td>

      <td>
        plan, add\_on, credit, charge
      </td>

      <td>
        The original source for a line item. A credit created from an original charge will have the value of the charge's origin.
      </td>
    </tr>

    <tr>
      <td>
        <span id="days">days</span>
      </td>

      <td>
        31
      </td>

      <td>
        The number of days between line\_item\_start\_date and line\_item\_end\_date.
      </td>
    </tr>

    <tr>
      <td>
        <span id="amount_per_day">amount\_per\_day</span>
      </td>

      <td>
        4.88
      </td>

      <td>
        The total amount divided by the number of days.
      </td>
    </tr>

    <tr>
      <td>
        <span id="total_amount">total\_amount</span>
      </td>

      <td>
        1000
      </td>

      <td>
        The total amount of the charge to be recognized for this schedule, in other words, "subtotal after discounts".
      </td>
    </tr>

    <tr>
      <td>
        <span id="currency">currency</span>
      </td>

      <td>
        USD
      </td>

      <td>
        The currency of the line item.
      </td>
    </tr>

    <tr>
      <td>
        <span id="schedule_type">schedule\_type</span>
      </td>

      <td>
        at\_range\_start, evenly
      </td>

      <td>
        The method in which revenue is recognized for that schedule, as defined in the plan settings for revenue recognition.
      </td>
    </tr>

    <tr>
      <td>
        <span id="revenue_recognition_date">revenue\_recognition\_date</span>
      </td>

      <td>
        2017-06-05 00:00:00 UTC
      </td>

      <td>
        The date revenue is recognized. Only populated if the schedule type is at\_range\_start or at\_rate\_end.
      </td>
    </tr>

    <tr>
      <td>
        <span id="deferred_revenue_balance">deferred\_revenue\_balance</span>
      </td>

      <td>
        evenly
      </td>

      <td>
        Reflects the total remaining deferred revenue to be recognized as of the date the export is requested.
      </td>
    </tr>

    <tr>
      <td>
        <span id="arrears">arrears</span>
      </td>

      <td>
        0
      </td>

      <td>
        The portion of the line item that applies to the past, i.e., before the time range "start date".
      </td>
    </tr>

    <tr>
      <td>
        <span id="month_1">month\_1</span>
      </td>

      <td>
        20
      </td>

      <td>
        The total amount recognized in a specific month. Note that the first month will be the current month.
      </td>
    </tr>

    <tr>
      <td>
        <span id="month_2">month\_2</span>
      </td>

      <td>
        20
      </td>

      <td>
        The total amount recognized in a specific month. The second column will be the month after the current month.
      </td>
    </tr>

    <tr>
      <td>
        <span id="month_3_etc">month\_3, etc.</span>
      </td>

      <td>
        20
      </td>

      <td>
        The total amount recognized in a specific month. There will be a column for each month after the current month, creating 12 columns of months in total.
      </td>
    </tr>

    <tr>
      <td>
        <span id="future_revenue">future\_revenue</span>
      </td>

      <td>
        90
      </td>

      <td>
        Revenue to be recognized in the future past 12 months from the current month.
      </td>
    </tr>

    <tr>
      <td>
        <span id="invoice_origin">invoice\_origin</span>
      </td>

      <td>
        purchase, refund
      </td>

      <td>
        The event that created the invoice. Invoices issued before the Credit Invoices feature was enabled on your site will have either purchase or refund as the value. Once Credit Invoices is enabled, new origins like renewal, immediate\_change, and write\_off will appear.
      </td>
    </tr>
  </tbody>
</Table>

### **Version 2 - 11/1/2018**

* Modification to the arrear and deferred revenue calculations.
