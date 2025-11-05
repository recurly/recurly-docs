---
title: Products Catalog - export
excerpt: Unlock detailed insights into your product catalog with the products export.
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
        The Recurly unique identifier for the saved item, also denoting the add-on code.
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
        Optional external SKU of the saved item used in creating this add-on.
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
        The status of the item in your Recurly catalog, being either "enabled" or "disabled".
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
        The Recurly unique identifier for the plan affiliated with this subscription.
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
        Platinum Plan
      </td>

      <td>
        The contemporary name of the plan corresponding to this subscription.
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
        3c42a34d1442f840
      </td>

      <td>
        Unique system-generated identifier for the subscription housing this item as an add-on.
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
        1
      </td>

      <td>
        The count of add-ons integrated into the subscription for this item.
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
        600
      </td>

      <td>
        The unit cost of the add-on in the subscription, denominated in cents; it may differ from the plan's or item's default pricing.
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
        USD
      </td>

      <td>
        The currency utilized for billing in this subscription.
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
        2020-02-07 10:18:34 MST
      </td>

      <td>
        The date and time when the add-on was created, a critical filter for defining the date range.
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
        2020-02-07 10:18:34 MST
      </td>

      <td>
        The latest modification date and time for the add-on.
      </td>

      <td>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="plan_total_billing_cycles">plan_total_billing_cycles</span>
      </td>

      <td>
        flat
      </td>

      <td>
        The subscription add-on tier type.
      </td>

      <td>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="plan_trial_interval_unit">plan_trial_interval_unit</span>
      </td>

      <td>
        12345
      </td>

      <td>
        Subscription add-on total amount in cents.
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
        source1
      </td>

      <td>
        Subscription add-on source.
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
        Boolean flag to indicate whether the subscription add-on is tax inclusive.
      </td>

      <td>
        string
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
        Indicates if this charge will be recurring
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
        Indicates if this charge will be recurring
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
        Indicates if this charge will be recurring
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
        <span id="performance_obligation_name">performance_obligation_name</span>
      </td>

      <td>

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
        <span id="accounting_code">accounting_code</span>
      </td>

      <td>

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
