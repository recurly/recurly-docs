---
title: Coupons - export
excerpt: Master your promotions with the detailed Coupons export section.
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

The "Coupons" export section is designed to offer comprehensive details on all the coupons created on your site, facilitating a streamlined analysis and management of your promotional strategies. Coupons with a fixed amount discount that support multiple currencies will be displayed in separate rows for each currency. 

# Filters

### **Date Range Filters**

#### **Created**

Filter the data to only include the coupons that were created within a selected time frame.

#### **Modified**

This filter allows you to zero in on the coupons modified within a chosen time range. A modification occurs due to an increment in redemption\_count, when a coupon hits its max\_redemptions limit, or is deactivated prematurely, which is reflected in the "deactivated\_at" column.

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

<Table align={[null,null,null,"left"]}>
  <thead>
    <tr>
      <th>
        <span id="id">

        Id

        </span>
      </th>

      <th>
        Example
      </th>

      <th>
        Description
      </th>

      <th style={{ textAlign: "left" }}>
        Data type (max size)
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        <span id="coupon_code">coupon\_code</span>
      </td>

      <td>
        5off
      </td>

      <td>
        The code to be inputted by customers to avail the discount.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(50)
      </td>
    </tr>

    <tr>
      <td>
        <span id="name">name</span>
      </td>

      <td>
        5% Off
      </td>

      <td>
        Internal nomenclature for the coupon.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(255)
      </td>
    </tr>

    <tr>
      <td>
        <span id="discount">discount</span>
      </td>

      <td>
        5
      </td>

      <td>
        Value of the fixed amount discount, depicted in the currency column; 0 for percentage discounts.
      </td>

      <td style={{ textAlign: "left" }}>
        numeric
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
        Denotes the currency for the fixed discount amount; blank for percentage discounts.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(3)
      </td>
    </tr>

    <tr>
      <td>
        <span id="discount_percent">discount\_percent</span>
      </td>

      <td>
        5
      </td>

      <td>
        Indicates the percentage discount; blank for fixed amount discounts.
      </td>

      <td style={{ textAlign: "left" }}>
        numeric
      </td>
    </tr>

    <tr>
      <td>
        <span id="redeem_by_date">redeem\_by\_date</span>
      </td>

      <td>
        2015-10-10 11:59:59 PST
      </td>

      <td>
        The expiration date and time post which the coupon cannot be redeemed.
      </td>

      <td style={{ textAlign: "left" }}>
        timestamp
      </td>
    </tr>

    <tr>
      <td>
        <span id="redemptions_count">redemptions\_count</span>
      </td>

      <td>
        7
      </td>

      <td>
        The total number of redemptions to date.
      </td>

      <td style={{ textAlign: "left" }}>
        numeric
      </td>
    </tr>

    <tr>
      <td>
        <span id="max_redemptions">max\_redemptions</span>
      </td>

      <td>
        100
      </td>

      <td>
        The upper limit on the allowable number of redemptions.
      </td>

      <td style={{ textAlign: "left" }}>
        numeric
      </td>
    </tr>

    <tr>
      <td>
        <span id="applies_to_plans">applies\_to\_plans</span>
      </td>

      <td>
        all plans
      </td>

      <td>
        Specifies the plans that can be discounted through the coupon redemptions.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="timeframe">timeframe</span>
      </td>

      <td>
        forever
      </td>

      <td>
        The lifespan of the coupon.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="created_at">created\_at</span>
      </td>

      <td>
        2012-01-02 06:20:41 PST
      </td>

      <td>
        Date and time of coupon creation; employed in created date range filter.
      </td>

      <td style={{ textAlign: "left" }}>
        timestamp
      </td>
    </tr>

    <tr>
      <td>
        <span id="deactivated_at">deactivated\_at</span>
      </td>

      <td>
        2013-02-02 06:20:41 PST
      </td>

      <td>
        Marks the date and time when the coupon was either expired early or when the max\_redemptions were achieved.
      </td>

      <td style={{ textAlign: "left" }}>
        timestamp
      </td>
    </tr>

    <tr>
      <td>
        <span id="modified">modified</span>
      </td>

      <td>
        2012-01-02 06:20:41 PST
      </td>

      <td>
        Records the most recent modification time, relevant for the modified date range filter.
      </td>

      <td style={{ textAlign: "left" }}>
        timestamp
      </td>
    </tr>

    <tr>
      <td>
        <span id="applies_to_non_plan_charges">applies\_to\_non\_plan\_charges</span>
      </td>

      <td>
        TRUE
      </td>

      <td>
        Dictates whether the coupon redemptions can offer discounts on one-time charges on customer invoices.
      </td>

      <td style={{ textAlign: "left" }}>
        boolean
      </td>
    </tr>

    <tr>
      <td>
        <span id="redemptions_per_account">redemptions\_per\_account</span>
      </td>

      <td>
        1
      </td>

      <td>
        The maximum redemption limit per account; "unlimited" if left blank.
      </td>

      <td style={{ textAlign: "left" }}>
        numeric
      </td>
    </tr>

    <tr>
      <td>
        <span id="redemption_resource">redemption\_resource</span>
      </td>

      <td>
        account, subscription
      </td>

      <td>
        The scope of the discount, whether at the account or subscription level.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="coupon_type">coupon\_type</span>
      </td>

      <td>
        single code, bulk
      </td>

      <td>
        Categorizes the coupon as a single code or a bulk code with several unique codes.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="discount_type">discount\_type</span>
      </td>

      <td>
        percent, fixed\_amount, free\_trial
      </td>

      <td>
        Specifies the nature of the discount — percentage, fixed amount, or free trial.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="free_trial_coupon_amount">free\_trial\_coupon\_amount</span>
      </td>

      <td>
        14
      </td>

      <td>
        For "free\_trial" discount types, it signifies the number associated with the trial period unit.
      </td>

      <td style={{ textAlign: "left" }}>
        numeric
      </td>
    </tr>

    <tr>
      <td>
        <span id="free_trial_coupon_unit">free\_trial\_coupon\_unit</span>
      </td>

      <td>
        day, week, month
      </td>

      <td>
        Relates to the "free\_trial" discount type, indicating the period of the trial.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="applies_to_items">applies\_to\_items</span>
      </td>

      <td>
        item1, item2
      </td>

      <td>
        Identifies whether a coupon is applicable to all items or specific items.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td>
        coupon\_api\_id
      </td>

      <td>
        e28zov4fw0v2
      </td>

      <td>
        Coupon API ID
      </td>

      <td style={{ textAlign: "left" }}>
        String
      </td>
    </tr>
  </tbody>
</Table>

# Version Changelog

### Version 3 - 2/5/2025

* Addition of `coupon_api_id`.

### Version 2 - 10/15/20

* Introduction of the applies\_to\_items column to highlight if a coupon is applicable to all items or select items. In case a given coupon is only applicable to select items, the item code will be aggregated with a comma as delimiter.

Recurly offers 3 exports relevant to coupons: Coupons, Coupon Redemptions, and Coupons- Bulk Unique Coupons
