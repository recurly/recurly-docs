---
title: Adjustments - export
excerpt: Unveil detailed insights with the Adjustments Export feature.
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

# Definition

Recurly's Adjustments Exports allow you to closely monitor the invoiced and uninvoiced adjustments associated with your accounts. This exportencompasses every invoiced charge and credit adjustment and even offers the option to include uninvoiced adjustments that are presently on the account. You can avail of the Adjustments export by visiting the [Exports](http://app.recurly.com/go/exports) page found under the "Reports" tab on your Recurly site.

### **Options**

You are granted two distinct options for exporting data:

#### **Include uninvoiced adjustments**

By default, the export primarily includes invoiced adjustments. However, upon selecting this option, you can view both charges and credits that haven't been invoiced as of yet, within a specified date range. These adjustments bear a 'pending' status and are placed at the commencement of the export document.

#### **Use invoice posted date**

Ordinarily, the export utilizes the adjustment's creation date rather than the invoice date. Consequently, an older uninvoiced charge or credit that was created within a set date range but invoiced later will not be reflected in the export. To counter this, choose this option to instead use the invoice posted date for a comprehensive view. Note that the creation date determines the presence of uninvoiced adjustments in the export as they lack an associated invoice date.

# Filters

### **Time Range Filter**

Utilize this feature to visualize charge and credit adjustments initiated in a specified timeframe. The "adjustment\_created\_at" date in the export is the default parameter used to filter results. In case you wish to filter adjustments based on the invoice creation date, simply opt for the "Use invoice date" option.

**Note**:  Adjustments are immutable; hence, a 'modified' time range option is non-existent.

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

<Table align={["left","left","left","left"]}>
  <thead>
    <tr>
      <th style={{ textAlign: "left" }}>
        Column Name
      </th>

      <th style={{ textAlign: "left" }}>
        Example
      </th>

      <th style={{ textAlign: "left" }}>
        Description
      </th>

      <th style={{ textAlign: "left" }}>
        Data type (max size)
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="uuid">uuid</span>
      </td>

      <td style={{ textAlign: "left" }}>
        b964b5439c2548a489
      </td>

      <td style={{ textAlign: "left" }}>
        Unique internal identifier for the adjustment. Equivalent to line\_item\_uuid in the deprecated Invoices export.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(32)
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="account_code">account\_code</span>
      </td>

      <td style={{ textAlign: "left" }}>
        123122E
      </td>

      <td style={{ textAlign: "left" }}>
        Account code being charged for this invoice.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(50)
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="subscription_id">subscription\_id</span>
      </td>

      <td style={{ textAlign: "left" }}>
        1fed8d153fcf4ea2a1
      </td>

      <td style={{ textAlign: "left" }}>
        Subscription UUID associated with this adjustment on the invoice.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(32)
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="invoice_id">invoice\_id</span>
      </td>

      <td style={{ textAlign: "left" }}>
        4bdb2171cebe4ecf
      </td>

      <td style={{ textAlign: "left" }}>
        Unique internal identifier for the invoice. This is called the 'id' in the Invoices - Summary export or 'uuid' for the invoice in the API.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(32)
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="adjustment_status">adjustment\_status</span>
      </td>

      <td style={{ textAlign: "left" }}>
        invoiced or pending
      </td>

      <td style={{ textAlign: "left" }}>
        Current status of the adjustment. Pending adjustments are charges or credits on an account that have not been applied to an invoice yet. Invoiced adjustments will always have an invoice associated with them.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="adjustment_type">adjustment\_type</span>
      </td>

      <td style={{ textAlign: "left" }}>
        charge or credit
      </td>

      <td style={{ textAlign: "left" }}>
        Charges are positive adjustments that debit the account. Credits are negative adjustments that credit the account.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(10)
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="adjustment_created_at">adjustment\_created\_at</span>
      </td>

      <td style={{ textAlign: "left" }}>
        2012-02-19 12:01:33 PST
      </td>

      <td style={{ textAlign: "left" }}>
        Creation date of the adjustment. This date will equal the billed\_date of the invoice in most cases, but will be older than the billed\_date if the adjustment was created on the account a period of time before it was invoiced. The adjustment\_created\_at date will never be after the invoice's billed\_date.
      </td>

      <td style={{ textAlign: "left" }}>
        timestamp
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="adjustment_start_at">adjustment\_start\_at</span>
      </td>

      <td style={{ textAlign: "left" }}>
        2012-02-19 12:01:33 PST
      </td>

      <td style={{ textAlign: "left" }}>
        Bill cycle start date for a specific adjustment. Equivalent to line\_item\_start\_date in the deprecated Invoices export.
      </td>

      <td style={{ textAlign: "left" }}>
        timestamp
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="adjustment_end_at">adjustment\_end\_at</span>
      </td>

      <td style={{ textAlign: "left" }}>
        2012-02-19 12:01:33 PST
      </td>

      <td style={{ textAlign: "left" }}>
        Bill cycle end date for a specific adjustment. Equivalent to line\_item\_end\_date in the deprecated Invoices.
      </td>

      <td style={{ textAlign: "left" }}>
        timestamp
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="adjustment_description">adjustment\_description</span>
      </td>

      <td style={{ textAlign: "left" }}>
        Gold Plan
      </td>

      <td style={{ textAlign: "left" }}>
        Description for a specific adjustment. This is automatically generated for all plan adjustments. This is custom for one-time custom charges and credits. Equivalent to line\_item\_description in the deprecated Invoices export
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(255)
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="adjustment_quantity">adjustment\_quantity</span>
      </td>

      <td style={{ textAlign: "left" }}>
        1
      </td>

      <td style={{ textAlign: "left" }}>
        Quantity of the adjustment.
      </td>

      <td style={{ textAlign: "left" }}>
        numeric
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="adjustment_currency">adjustment\_currency</span>
      </td>

      <td style={{ textAlign: "left" }}>
        USD
      </td>

      <td style={{ textAlign: "left" }}>
        Currency of the adjustment.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(3)
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="adjustment_amount">adjustment\_amount</span>
      </td>

      <td style={{ textAlign: "left" }}>
        100
      </td>

      <td style={{ textAlign: "left" }}>
        Adjustment amount, before discounts or taxes.
      </td>

      <td style={{ textAlign: "left" }}>
        numeric
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="adjustment_total">adjustment\_total</span>
      </td>

      <td style={{ textAlign: "left" }}>
        50
      </td>

      <td style={{ textAlign: "left" }}>
        The total amount of the adjustment after discounts and taxes [(quantity x price) + discount + tax]. Equivalent to line\_item\_total in the deprecated Invoices.
      </td>

      <td style={{ textAlign: "left" }}>
        numeric
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="adjustment_taxable">adjustment\_taxable</span>
      </td>

      <td style={{ textAlign: "left" }}>
        0 or 1
      </td>

      <td style={{ textAlign: "left" }}>
        0 indicates adjustment is not taxable, 1 indicates adjustment is taxable.
      </td>

      <td style={{ textAlign: "left" }}>
        boolean
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="adjustment_discount">adjustment\_discount</span>
      </td>

      <td style={{ textAlign: "left" }}>
        5
      </td>

      <td style={{ textAlign: "left" }}>
        The discount applied to the adjustment.
      </td>

      <td style={{ textAlign: "left" }}>
        numeric
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="adjustment_tax">adjustment\_tax</span>
      </td>

      <td style={{ textAlign: "left" }}>
        5
      </td>

      <td style={{ textAlign: "left" }}>
        The tax amount for the adjustment.
      </td>

      <td style={{ textAlign: "left" }}>
        numeric
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="adjustment_accounting_code">adjustment\_accounting\_code</span>
      </td>

      <td style={{ textAlign: "left" }}>
        X100
      </td>

      <td style={{ textAlign: "left" }}>
        Internal accounting code for a specific adjustment. This value will only populate if you define an accounting code for the adjustment. Accounting codes can be defined for all adjustments except free trials, which will inherit the plan's accounting code. Equivalent to line\_item\_accounting\_code in the deprecated Invoices export.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(25)
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="adjustment_product_code">adjustment\_product\_code</span>
      </td>

      <td style={{ textAlign: "left" }}>
        gold
      </td>

      <td style={{ textAlign: "left" }}>
        Product code for a specific adjustment. This will populate automatically with the plan code or add-on code if the adjustment is for a subscription. This will populate for custom charges and credits (origin = debit or one\_time) if a value was set when the adjustment was created. Equivalent to line\_item\_product\_code in the deprecated Invoices export.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(50)
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="adjustment_tax_code">adjustment\_tax\_code</span>
      </td>

      <td style={{ textAlign: "left" }}>
        P0000000, physical
      </td>

      <td style={{ textAlign: "left" }}>
        Tax code is a field associated with the adjustment that we send to Avalara for tax calculations. If you are using Recurly's EU VAT feature, you can use values of 'unknown', 'physical', or 'digital'. If you have your own Avalara AvaTax account configured, you can use Avalara tax codes to assign custom tax rules.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(50)
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="adjustment_origin">adjustment\_origin</span>
      </td>

      <td style={{ textAlign: "left" }}>
        plan, plan\_trial, setup\_fee, add\_on, add\_on\_trial, usage\_add\_on, usage\_add\_on\_trial, one\_time, debit, credit, coupon, carryforward, gift\_card, external\_gift\_card
      </td>

      <td style={{ textAlign: "left" }}>
        The original source for an adjustment. A credit created from an original charge will have the value of the charge's origin. Equivalent to line\_item\_origin in the deprecated Invoices export. (plan = subscription fee, plan\_trial = trial period 0 amount charge, setup\_fee = subscription setup fee, add\_on = subscription add-on fee, debit = custom charge through the UI or Adjustments API, one\_time = custom charge through the Transactions API, credit = custom credit, carryforward = the charge that zeros out a negative invoice and should be ignored)
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(20)
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="tax_type">tax\_type</span>
      </td>

      <td style={{ textAlign: "left" }}>
        usst, vat, ca, au, nz
      </td>

      <td style={{ textAlign: "left" }}>
        Tax type for the adjustment. Will be "vat" for EU VAT, "usst" for U.S. Sales Tax, or the 2 letter country code for country level tax types like Canada, Australia, New Zealand, Israel, and all non-EU European countries.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(6)
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="tax_region">tax\_region</span>
      </td>

      <td style={{ textAlign: "left" }}>
        NY, FR, GST, VAT
      </td>

      <td style={{ textAlign: "left" }}>
        The tax region for the adjustment. For U.S. Sales Tax, this will be the 2 letter state code. For EU VAT this will be the 2 letter country code. For all country level tax types, this will display the regional tax, like VAT, GST, or PST.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(15)
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="tax_rate">tax\_rate</span>
      </td>

      <td style={{ textAlign: "left" }}>
        0.09
      </td>

      <td style={{ textAlign: "left" }}>
        Tax rate applied to the adjustment.
      </td>

      <td style={{ textAlign: "left" }}>
        numeric
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="tax_amount">tax\_amount</span>
      </td>

      <td style={{ textAlign: "left" }}>
        5
      </td>

      <td style={{ textAlign: "left" }}>
        The tax amount for the adjustment. This column is the same as the adjustment\_tax column, but tax\_amount may be missing a few values for merchants who have used Recurly's older VAT feature (pre-2015). Merchants who used the old VAT feature should use the adjustment\_tax column for older reports.
      </td>

      <td style={{ textAlign: "left" }}>
        numeric
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="country_juris">country\_juris</span>\*
      </td>

      <td style={{ textAlign: "left" }}>
        united states
      </td>

      <td style={{ textAlign: "left" }}>
        Country tax jurisdiction of the adjustment. This will be the full name of the country in lowercase.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="country_rate">country\_rate</span>\*
      </td>

      <td style={{ textAlign: "left" }}>
        0
      </td>

      <td style={{ textAlign: "left" }}>
        Country tax rate of the adjustment. This is the tax rate that corresponds to the country\_juris and country\_amount.
      </td>

      <td style={{ textAlign: "left" }}>
        numeric
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="country_amount">country\_amount</span>\*
      </td>

      <td style={{ textAlign: "left" }}>
        0
      </td>

      <td style={{ textAlign: "left" }}>
        Country tax amount of the adjustment. This is the tax amount that corresponds to country\_rate and country\_juris.
      </td>

      <td style={{ textAlign: "left" }}>
        numeric
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="state_juris">state\_juris</span>\*
      </td>

      <td style={{ textAlign: "left" }}>
        california, ontario
      </td>

      <td style={{ textAlign: "left" }}>
        State or province tax jurisdiction of the adjustment. This will be the full name of the state or province in lowercase.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="state_rate">state\_rate</span>\*
      </td>

      <td style={{ textAlign: "left" }}>
        0.065
      </td>

      <td style={{ textAlign: "left" }}>
        State or province tax rate of the adjustment. This is the tax rate that corresponds to the state\_juris and state\_amount.
      </td>

      <td style={{ textAlign: "left" }}>
        numeric
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="state_amount">state\_amount</span>\*
      </td>

      <td style={{ textAlign: "left" }}>
        0.33
      </td>

      <td style={{ textAlign: "left" }}>
        State or province tax amount of the adjustment. This is the tax amount that corresponds to state\_rate and state\_juris.
      </td>

      <td style={{ textAlign: "left" }}>
        numeric
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="county_juris">county\_juris</span>\*
      </td>

      <td style={{ textAlign: "left" }}>
        san mateo
      </td>

      <td style={{ textAlign: "left" }}>
        County tax jurisdiction of the adjustment. This will be the full name of the county in lowercase.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="county_rate">county\_rate</span>\*
      </td>

      <td style={{ textAlign: "left" }}>
        0.01
      </td>

      <td style={{ textAlign: "left" }}>
        County tax rate of the adjustment. This is the tax rate that corresponds to the county\_juris and county\_amount.
      </td>

      <td style={{ textAlign: "left" }}>
        numeric
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="county_amount">county\_amount</span>\*
      </td>

      <td style={{ textAlign: "left" }}>
        0.05
      </td>

      <td style={{ textAlign: "left" }}>
        County tax amount of the adjustment. This is the tax amount that corresponds to county\_rate and county\_juris.
      </td>

      <td style={{ textAlign: "left" }}>
        numeric
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="city_juris">city\_juris</span>\*
      </td>

      <td style={{ textAlign: "left" }}>
        san francisco
      </td>

      <td style={{ textAlign: "left" }}>
        City tax jurisdiction of the adjustment. This will be the full name of the city in lowercase.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="city_rate">city\_rate</span>\*
      </td>

      <td style={{ textAlign: "left" }}>
        0.1
      </td>

      <td style={{ textAlign: "left" }}>
        City tax rate of the adjustment. This is the tax rate that corresponds to the city\_juris and city\_amount.
      </td>

      <td style={{ textAlign: "left" }}>
        numeric
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="city_amount">city\_amount</span>\*
      </td>

      <td style={{ textAlign: "left" }}>
        0.05
      </td>

      <td style={{ textAlign: "left" }}>
        City tax amount of the adjustment. This is the tax amount that corresponds to city\_rate and city\_juris.
      </td>

      <td style={{ textAlign: "left" }}>
        numeric
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="special_juris">special\_juris</span>\*
      </td>

      <td style={{ textAlign: "left" }}>
        san francisco
      </td>

      <td style={{ textAlign: "left" }}>
        Special tax jurisdiction of the adjustment. This will be the full name of the jurisdiction in lowercase.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="special_rate">special\_rate</span>\*
      </td>

      <td style={{ textAlign: "left" }}>
        0.1
      </td>

      <td style={{ textAlign: "left" }}>
        Special jurisdiction tax rate of the adjustment. This is the tax rate that corresponds to the special\_juris and special\_amount.
      </td>

      <td style={{ textAlign: "left" }}>
        numeric
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="special_amount">special\_amount</span>\*
      </td>

      <td style={{ textAlign: "left" }}>
        0.05
      </td>

      <td style={{ textAlign: "left" }}>
        Special jurisdiction tax amount of the adjustment. This is the tax amount that corresponds to special\_rate and special\_juris.
      </td>

      <td style={{ textAlign: "left" }}>
        numeric
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="adjustment_refund">adjustment\_refund</span>
      </td>

      <td style={{ textAlign: "left" }}>
        TRUE, FALSE
      </td>

      <td style={{ textAlign: "left" }}>
        TRUE indicates that the adjustment is a refund of a charge. FALSE indicates that the adjustment was a standard charge.
      </td>

      <td style={{ textAlign: "left" }}>
        boolean
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="original_adjustment_uuid">original\_adjustment\_uuid</span>
      </td>

      <td style={{ textAlign: "left" }}>
        b964b5439c2548a
      </td>

      <td style={{ textAlign: "left" }}>
        Value is the uuid of the previous related adjustment. Will only have a value if the adjustment is a credit created from a previous credit, or if the credit was created from a charge refund.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(32)
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="invoice_number">invoice\_number</span>
      </td>

      <td style={{ textAlign: "left" }}>
        1291
      </td>

      <td style={{ textAlign: "left" }}>
        Invoice number of the invoice the adjustment was on.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="invoice_state">invoice\_state</span>
      </td>

      <td style={{ textAlign: "left" }}>
        pending
      </td>

      <td style={{ textAlign: "left" }}>
        Current state of the invoice the adjustment was on. Equivalent to invoice\_status in the Invoices - Summary export.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(20)
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="adjustment_coupon_code">adjustment\_coupon\_code</span>
      </td>

      <td style={{ textAlign: "left" }}>
        1monthfree-K09SC9R8
      </td>

      <td style={{ textAlign: "left" }}>
        The coupon code that discounted the specific adjustment\_discount amount on the adjustment.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="invoice_billed_date">invoice\_billed\_date</span>
      </td>

      <td style={{ textAlign: "left" }}>
        2012-02-19 12:01:33 PST
      </td>

      <td style={{ textAlign: "left" }}>
        Creation date of the invoice. Equivalent to date in the deprecated Invoices export.
      </td>

      <td style={{ textAlign: "left" }}>
        timestamp
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="invoice_closed_at">invoice\_closed\_at</span>
      </td>

      <td style={{ textAlign: "left" }}>
        2012-02-19 12:01:33 PST
      </td>

      <td style={{ textAlign: "left" }}>
        Date invoice was paid or failed.
      </td>

      <td style={{ textAlign: "left" }}>
        timestamp
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="invoice_net_terms">invoice\_net\_terms</span>
      </td>

      <td style={{ textAlign: "left" }}>
        on-receipt, net-10, net-30, net-60
      </td>

      <td style={{ textAlign: "left" }}>
        Identifies the net\_terms agreement associated with the invoice. All automatic collection invoices are due 'on-receipt'. Manual collection invoices can have terms of net-10, net-30, net-60, or a custom net day amount.
      </td>

      <td style={{ textAlign: "left" }}>
        numeric
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="invoice_po_number">invoice\_po\_number</span>
      </td>

      <td style={{ textAlign: "left" }}>
        AE12523
      </td>

      <td style={{ textAlign: "left" }}>
        For manual invoicing, this identifies the Purchase Order number associated with the invoice. This value must be entered by the merchant at the time the invoice is created or it will not exist.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(50)
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="invoice_collection_method">invoice\_collection\_method</span>
      </td>

      <td style={{ textAlign: "left" }}>
        automatic or manual
      </td>

      <td style={{ textAlign: "left" }}>
        Identifies whether the invoice fees are collected via manual or automatic invoicing. An automatic invoice means a corresponding transaction is run using the account's billing information at the same time the invoice is created. Manual invoices are created without a corresponding transaction. The merchant must enter a manual payment transaction or have the customer pay the invoice with an automatic method, like credit card, PayPal, Amazon, or ACH bank payment.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="invoice_type">invoice\_type</span>
      </td>

      <td style={{ textAlign: "left" }}>
        purchase or refund
      </td>

      <td style={{ textAlign: "left" }}>
        The original invoice will have a type of 'purchase'. Any refunds or voids will create a negative invoice to cancel out the original. This negative invoice will have a type of 'refund'.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="account_name">account\_name</span>
      </td>

      <td style={{ textAlign: "left" }}>
        JJ Smith
      </td>

      <td style={{ textAlign: "left" }}>
        First and last name from account.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="account_country">account\_country</span>
      </td>

      <td style={{ textAlign: "left" }}>
        US
      </td>

      <td style={{ textAlign: "left" }}>
        The 2 letter country code for the country of the customer's address on the invoice. This will come from the Billing Address or the Account Address depending on your tax settings and the invoice collection method.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(2)
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="account_vat_number">account\_vat\_number</span>
      </td>

      <td style={{ textAlign: "left" }}>
        IE124211145
      </td>

      <td style={{ textAlign: "left" }}>
        VAT registration number for the customer on the invoice. This will come from the VAT Number field in the Billing Info or the Account Info depending on your tax settings and the invoice collection method.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(20)
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="adjustment_plan_code">adjustment\_plan\_code</span>
      </td>

      <td style={{ textAlign: "left" }}>
        basic
      </td>

      <td style={{ textAlign: "left" }}>
        The plan code for the plan associated with the subscription. This value will exist for plan fee, setup fee, add-on fee and free trial adjustments. This value will not exist for custom charges, custom credits, or open amount refund credits.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(50)
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="original_invoice_number">original\_invoice\_number</span>
      </td>

      <td style={{ textAlign: "left" }}>
        1002
      </td>

      <td style={{ textAlign: "left" }}>
        If the row is an adjustment on a refund invoice, this value will exist and show the invoice number of the purchase invoice the refund was created from.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="invoice_due_on">invoice\_due\_on</span>
      </td>

      <td style={{ textAlign: "left" }}>
        2012-02-19 12:01:33 PST
      </td>

      <td style={{ textAlign: "left" }}>
        The due date of the invoice.
      </td>

      <td style={{ textAlign: "left" }}>
        timestamp
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="adjustment_subtotal">adjustment\_subtotal</span>
      </td>

      <td style={{ textAlign: "left" }}>
        50.25
      </td>

      <td style={{ textAlign: "left" }}>
        The adjustment amount after discounts, but before taxes.
      </td>

      <td style={{ textAlign: "left" }}>
        numeric
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="adjustment_credit_reason_code">adjustment\_credit\_reason\_code</span>
      </td>

      <td style={{ textAlign: "left" }}>
        general, service, promotional, refund, write\_off, gift\_card
      </td>

      <td style={{ textAlign: "left" }}>
        The credit reason code of the adjustment. This is a new attribute with Recurly defined values the merchant can choose from when creating custom credits, or Recurly will set when issuing credits.\
        **This column will be null until Recurly's Credit Invoices feature is enabled on your Recurly site.**
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="adjustment_refundable_amount">adjustment\_refundable\_amount</span>
      </td>

      <td style={{ textAlign: "left" }}>
        50.25
      </td>

      <td style={{ textAlign: "left" }}>
        The refundable amount of the charge adjustment, which is the adjustment total, including discounts and tax, minus all credit adjustments issued against it.\
        **This column will be null until Recurly's Credit Invoices feature is enabled on your Recurly site.**
      </td>

      <td style={{ textAlign: "left" }}>
        numeric
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="ship_address_name">ship\_address\_name</span>
      </td>

      <td style={{ textAlign: "left" }}>
        Jane Doe
      </td>

      <td style={{ textAlign: "left" }}>
        The first and last name associated with the shipping address for the adjustment.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="ship_address_line1">ship\_address\_line1</span>
      </td>

      <td style={{ textAlign: "left" }}>
        123 Main Street
      </td>

      <td style={{ textAlign: "left" }}>
        The first address line associated with the shipping address for the adjustment
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="ship_address_line2">ship\_address\_line2</span>
      </td>

      <td style={{ textAlign: "left" }}>
        Suite #202
      </td>

      <td style={{ textAlign: "left" }}>
        The second address line associated with the shipping address for the adjustment
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="ship_address_city">ship\_address\_city</span>
      </td>

      <td style={{ textAlign: "left" }}>
        San Francisco
      </td>

      <td style={{ textAlign: "left" }}>
        The city associated with the shipping address for the adjustment.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="ship_address_state">ship\_address\_state</span>
      </td>

      <td style={{ textAlign: "left" }}>
        CA
      </td>

      <td style={{ textAlign: "left" }}>
        The state associated with the shipping address for the adjustment.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="ship_address_zip">ship\_address\_zip</span>
      </td>

      <td style={{ textAlign: "left" }}>
        94110
      </td>

      <td style={{ textAlign: "left" }}>
        The zip code associated with the shipping address for the adjustment
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="ship_address_country">ship\_address\_country</span>
      </td>

      <td style={{ textAlign: "left" }}>
        US
      </td>

      <td style={{ textAlign: "left" }}>
        The country ISO code associated with the shipping address for the adjustment
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="ship_address_phone">ship\_address\_phone</span>
      </td>

      <td style={{ textAlign: "left" }}>
        510-100-1000
      </td>

      <td style={{ textAlign: "left" }}>
        The phone number associated with the shipping address for the adjustment
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="shipping_method_code">shipping\_method\_code</span>
      </td>

      <td style={{ textAlign: "left" }}>
        usps-overnight
      </td>

      <td style={{ textAlign: "left" }}>
        The Shipping Method code used when the Shipping Method was created.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(50)
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="item_code">item\_code</span>
      </td>

      <td style={{ textAlign: "left" }}>
        item123
      </td>

      <td style={{ textAlign: "left" }}>
        The Item Code maps to the user-specified unique ID of the item that was sold on this adjustment.  

        Reference [this page](https://docs.recurly.com/docs/catalog) for more on items.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(50)
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="item_id">item\_id</span>
      </td>

      <td style={{ textAlign: "left" }}>
        12345678998
      </td>

      <td style={{ textAlign: "left" }}>
        The Item ID maps to the system-generated unique ID of the item that was sold on this adjustment.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="external_sku">external\_sku</span>
      </td>

      <td style={{ textAlign: "left" }}>
        abc123
      </td>

      <td style={{ textAlign: "left" }}>
        The External SKU mapps to the user-specified SKU of the item that was sold on this adjustment.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(50)
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="tax_inclusive">tax\_inclusive</span>
      </td>

      <td style={{ textAlign: "left" }}>
        true
      </td>

      <td style={{ textAlign: "left" }}>
        Indicates whether the purchase was inclusive or exclusive of tax.
      </td>

      <td style={{ textAlign: "left" }}>
        boolean
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="business_entity_code">business\_entity\_code</span>
      </td>

      <td style={{ textAlign: "left" }}>
        2345678
      </td>

      <td style={{ textAlign: "left" }}>
        Business entity code.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        adjustment\_api\_id
      </td>

      <td style={{ textAlign: "left" }}>
        e28zov4fw0v2
      </td>

      <td style={{ textAlign: "left" }}>
        Adjustment API ID
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>
  </tbody>
</Table>

**\*Is not populated when using Vertex tax service**

# Version changelog

### Version 8 - 2/5/2025

* Addition of `adjustment_api_id`.

### **Version 7** - 7/25/2023

* Integrated an additional column to indicate `business_entity_code`.

### **Version 6** - 1/17/2022

* Introduced a column designated for Charge Custom Field Objects, custom field columns will always appear at the end of exports, including the following versions

### **Version 5** - 3/30/2022

* Integrated an additional column to indicate tax\_inclusive.

### **Version 4** - 2/13/2020

* A new column for external\_sku added to facilitate Item Charges.

### **Version 3** - 11/21/2019

* Added columns specifying item\_code and item\_id for Item Charges.

### **Version 2** - 5/2/2019

* Introduced a column to denote shipping\_method\_code.
