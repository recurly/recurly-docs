---
title: Products Catalog - export
excerpt: >-
  Unlock detailed insights into your product catalog with the products catalog
  export.
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

### Required plan

This feature or setting is available to all customers on any Recurly subscription plan.

# Definition

The "Products Catalog" export provides comprehensive details of all product offerings, add-ons and items, whether active or inactive.

# Filters

### Versions Filter

* The Versions filter allows you to select the version that is most appropriate for your needs. This is based on the version changelog at the bottom of this page.

### **Product Type Filter**

The Product type filter allows you to select existing plan, add on, setup fee, or item

* **Plan**: Recurring billing products that define the billing frequency and the product's base price, allowing businesses to create a revenue model that provides consistent income.
* **Add-on**: Additional features, services, or products that customers can purchase alongside their subscription plan.
* **Setup fee**: One time initial fee.
* **Item**: Collection of the sellable units of a business. This can include standalone products, services, or even add-ons

### &#x20;Export On Filters

* **Created**: Product created within the chosen timeframe.
* **Modified**: Product altered in the specified period.

### Time range filters

* The Time range filter (dropdown) allows you to view data within a specific period such as last month, year to date or a custom date range. The Start Date and End Date will automatically update based on the value selected in the Time range filter. You can also choose "Between..." in the dropdown, which will allow you to enter a customized date range.

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

Note: The unique identifier for each record is the combination of product_id, plan_id, and add_on_id. If an item type is configured as an add-on, it can be associated with multiple plans; in such cases, the same product_id is reused across those plans.

<Table align={["left","left","left","left"]}>
  <thead>
    <tr>
      <th>
        Column Name
      </th>

      <th>
        Example
      </th>

      <th>
        Description
      </th>

      <th>
        Data type (max size)
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        <span id="product_id:">product_id:</span>
      </td>

      <td>
        e28zov4fw0v2
      </td>

      <td>
        The api_id of the product (this matches item_api_id)
      </td>

      <td>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="plan_id">plan_id</span>
      </td>

      <td>
        p47mx1taq9b5
      </td>

      <td>
        The api_id of the plan
      </td>

      <td>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="add_on_id">add_on_id</span>
      </td>

      <td>
        pink_sweater
      </td>

      <td>
        The api_id of the add_on
      </td>

      <td>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="item_code">item_code</span>
      </td>

      <td>
        PS1234
      </td>

      <td>
        The Item Code maps to the user-specified unique ID of the item that was sold on this adjustment.
      </td>

      <td>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="product_type">product_type</span>
      </td>

      <td>
        enabled
      </td>

      <td>
        The type of product
      </td>

      <td>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="product_code">product_code</span>
      </td>

      <td>
        platinum
      </td>

      <td>
        The unique Recurly identifier of the saved product used to create the product.
      </td>

      <td>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="external_sku">external_sku</span>
      </td>

      <td>
        PS1234
      </td>

      <td>
        The optional external SKU of the saved item used to create this add-on.
      </td>

      <td>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="product_name">product_name</span>
      </td>

      <td>
        Pink Sweater
      </td>

      <td>
        The name of the saved product. This is also the name displayed on the invoice.
      </td>

      <td>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="product_description">product_description</span>
      </td>

      <td>
        Sweater, color pink
      </td>

      <td>
        The description of the product.
      </td>

      <td>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="plan_code">plan_code</span>
      </td>

      <td>
        Gold
      </td>

      <td>
        If the product is associated with a plan or is a plan this is the code of the plan.
      </td>

      <td>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="plan_name">plan_name</span>
      </td>

      <td>
        Gold Plan
      </td>

      <td>
        If the product is associated with a plan or is a plan this is the name of the plan.
      </td>

      <td>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="plan_interval_unit">plan_interval_unit</span>
      </td>

      <td>
        months, weeks, days, years

      </td>

      <td>
        The interval type at which that plan is billed.
      </td>

      <td>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="plan_interval_length">plan_interval_length</span>
      </td>

      <td>
        30

      </td>

      <td>
        The length of the interval type at which the plan is billed at.
      </td>

      <td>
        int64
      </td>
    </tr>

    <tr>
      <td>
        <span id="plan_total_billing_cycles">plan_total_billing_cycles</span>
      </td>

      <td>
        12
      </td>

      <td>
        The total number of bill cycles that the plan will bill for 1 term.
      </td>

      <td>
        int64
      </td>
    </tr>

    <tr>
      <td>
        <span id="plan_trial_interval_unit">plan_trial_interval_unit</span>
      </td>

      <td>
        months, weeks, days, years
      </td>

      <td>
        The interval type that indicates the duration of the trial.
      </td>

      <td>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="plan_trial_interval_length">plan_trial_interval_length</span>
      </td>

      <td>
        12
      </td>

      <td>
        The length of the interval type that sets the duration of the trial.
      </td>

      <td>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="trial_requires_billing_info">trial_requires_billing_info</span>
      </td>

      <td>
        false
      </td>

      <td>
        Indicates if the trial requires billing info.
      </td>

      <td>
        boolean
      </td>
    </tr>

    <tr>
      <td>
        <span id="recurring">recurring</span>
      </td>

      <td>
        true/false
      </td>

      <td>
        Indicates if this charge will be recurring
      </td>

      <td>
        boolean
      </td>
    </tr>

    <tr>
      <td>
        <span id="optional">optional</span>
      </td>

      <td>
        true/false
      </td>

      <td>
        Indicates if this is required as part of a plan.
      </td>

      <td>
        boolean
      </td>
    </tr>

    <tr>
      <td>
        <span id="tax_exempt">tax_exempt</span>
      </td>

      <td>
        true/false
      </td>

      <td>
        Indicates if the product is tax exempt.
      </td>

      <td>
        boolean
      </td>
    </tr>

    <tr>
      <td>
        <span id="tax_code">tax_code</span>
      </td>

      <td>
        P0000000, physical
      </td>

      <td>
        Tax code is a field associated with the product that we send to Avalara for tax calculations. If you are using Recurly's EU VAT feature, you can use values of 'unknown', 'physical', or 'digital'. If you have your own Avalara AvaTax account configured, you can use Avalara tax codes to assign custom tax rules.
      </td>

      <td>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="general_ledger_liability_code">general_ledger_liability_code</span>
      </td>

      <td>
        default_liability

      </td>

      <td>
        Revenue Recognition general ledger liability code
      </td>

      <td>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="general_ledger_revenue_code">general_ledger_revenue_code</span>
      </td>

      <td>
        default_revenue

      </td>

      <td>
        Revenue Recognition general ledger revenue code
      </td>

      <td>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="performance_obligation_name">performance_obligation_name</span>
      </td>

      <td>
        Over Time (Daily)
      </td>

      <td>
        Revenue Recognition performance obligation assigned to the product.
      </td>

      <td>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="accounting_code">accounting_code</span>
      </td>

      <td>
        jr_accounting_code

      </td>

      <td>
        Optional accounting_code assigned to the product.
      </td>

      <td>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="default_quantity">default_quantity</span>
      </td>

      <td>
        1
      </td>

      <td>
        Default quantity assigned to the product (default is 1)
      </td>

      <td>
        int64
      </td>
    </tr>

    <tr>
      <td>
        <span id="pricing_model">pricing_model</span>
      </td>

      <td>
        fixed
      </td>

      <td>
        This is the method the product is billed. Values include fixed, usage, tiered, ramp, volume, stairstep, percentage
      </td>

      <td>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="currencies">currencies</span>
      </td>

      <td>

      </td>

      <td>
        Json object of the currencies and associated prices
      </td>

      <td>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="custom_fields">custom_fields</span>
      </td>

      <td>

      </td>

      <td>
        Json object of any custom fields that are assigned to the product
      </td>

      <td>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="state">state</span>
      </td>

      <td>
        active, inactive
      </td>

      <td>
        If the product is available in Recurly the state will be “active”, if the product has been deleted and is no longer available in Recurly then the state will be “inactive”.  It is possible for subscribers to have “inactive” products on their subscription
      </td>

      <td>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="created_at">created_at</span>
      </td>

      <td>
        2025-11-12 08:23:34 UTC
      </td>

      <td>
        Timestamp when the product was created
      </td>

      <td>
        timestamp
      </td>
    </tr>

    <tr>
      <td>
        <span id="modified_at">modified_at</span>
      </td>

      <td>
        2025-11-12 08:23:34 UTC
      </td>

      <td>
        Timestamp when the product was last modified
      </td>

      <td>
        timestamp
      </td>
    </tr>

    <tr>
      <td>
        <span id="deleted_at">deleted_at</span>
      </td>

      <td>
        2025-11-12 08:23:34 UTC
      </td>

      <td>
        Timestamp when the product was deleted
      </td>

      <td>
        timestamp
      </td>
    </tr>
  </tbody>
</Table>

# Version changelog

<br />
