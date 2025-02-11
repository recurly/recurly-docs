---
title: Coupons — bulk unique codes - export
excerpt: >-
  Uncover intricate details of your bulk unique coupons with this exclusive
  Coupons - Bulk Unique Codes export.
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

### Prerequisites

This export will only appear on the Exports page if you have created a bulk coupon on your site.

# Definition

The Coupons - Bulk Unique Codes export section allows users to export and analyze all the unique codes pertaining to a specific bulk coupon. This includes redemption details for each code. This export option becomes available on the Exports page once a bulk coupon is created on your site. It enables a meticulous breakdown of each code's performance and status, providing insights that can aid in optimizing coupon strategies.

# Filters

### **Coupon Filter**

To utilize this export, select all or the desired bulk coupon from a dropdown menu that enumerates the internal name of the coupon and the prefix of the codes, enclosed in parentheses. This list is alphabetically arranged according to the internal names of the coupons.

### **Date Range Filters**

#### **Created**

Defines the date range according to the 'created\_at' column in the export. Leveraging the "All Time" option with "Created" will showcase the entire compilation of your unique codes. To zero in on a subset of codes crafted during a specific span of the campaign, simply filter the dates accordingly.

#### **Modified**

Establishes the date range based on the most recent modification date, aligned with the 'modified\_at' column in the export. A unique code experiences modification upon its redemption (tracked in 'applied\_at') or premature expiration (noted in 'deactivated\_at'). The expiration date ('expired\_at') does not constitute a modification event.

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
        **<span id="Id">Id</span>**
      </th>

      <th>
        **Example**
      </th>

      <th>
        **Description**
      </th>

      <th style={{ textAlign: "left" }}>

      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        <span id="bulk_coupon_id">bulk\_coupon\_id</span>
      </td>

      <td>
        769158967603640335
      </td>

      <td>
        UUID identifying the bulk coupon campaign, referential to the id in the Coupons export.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="bulk_coupon_prefix">bulk\_coupon\_prefix</span>
      </td>

      <td>
        save
      </td>

      <td>
        Prefix common to all unique codes, mapped to the coupon\_code of the bulk coupon in the Coupons export.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="unique_coupon_code">unique\_coupon\_code</span>
      </td>

      <td>
        save-012478
      </td>

      <td>
        Specific code for the bulk coupon, displayed as the coupon\_code in the Coupon Redemptions export where the customer applied it at redemption.
      </td>

      <td style={{ textAlign: "left" }}>

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
        Details of the fixed amount discount, which is applicable post-redemption, with the associated currency being showcased in the currency column. Maintains a null value for percentage discounts.
      </td>

      <td style={{ textAlign: "left" }}>

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
        Represents the percentage discount, remaining visible irrespective of the redemption status. Assumes a null value for fixed amount discounts.
      </td>

      <td style={{ textAlign: "left" }}>

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
        Stipulates the active duration of the coupon.
      </td>

      <td style={{ textAlign: "left" }}>

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
        Defines the expiration date and time post which the code becomes non-redeemable. Always set at 11:59:59 PST of the designated day.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="created_at">created\_at</span>
      </td>

      <td>
        2015-09-07 19:23:03 PST
      </td>

      <td>
        Marks the creation date and time of the unique code.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="modified_at">modified\_at</span>
      </td>

      <td>
        2015-09-07 19:23:03 PST
      </td>

      <td>
        Logs the most recent modification date and time, aligning with redemption ('applied\_at') or early expiration ('deactivated\_at').
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="deactivated_at">deactivated\_at</span>
      </td>

      <td>
        2015-09-07 19:23:03 PST
      </td>

      <td>
        Registers the early expiration date and time, if applicable.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="applied_at">applied\_at</span>
      </td>

      <td>
        2013-01-02 06:21:14 PST
      </td>

      <td>
        Records the date and time of the code's redemption on an account.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="expires_at">expires\_at</span>
      </td>

      <td>
        2014-01-02 06:21:14 PST
      </td>

      <td>
        Signifies the automatic expiration date and time of the code after the preset duration concludes.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="redemption_uuid">redemption\_uuid</span>
      </td>

      <td>
        306f7937d86f088f046dd945a1a24df2
      </td>

      <td>
        The unique ID representing each unique code's redemption.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="account_code">account\_code</span>
      </td>

      <td>
        306f7937d86f088f046dd945a1a24df2
      </td>

      <td>
        The unique identifier for the account where the code was redeemed.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="subscription_id">subscription\_id</span>
      </td>

      <td>
        306f7937d86f088f046dd945a1a24df2
      </td>

      <td>
        UUID of the subscription linked to the unique code's redemption on a customer account, displayed only for subscription-level redemptions.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="total_discount">total\_discount</span>
      </td>

      <td>
        100.50
      </td>

      <td>
        The aggregated discount applied on the account from the unique code's redemption till date.
      </td>

      <td style={{ textAlign: "left" }}>

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
        The currency assigned to the 'total\_discount' and 'discount' columns.
      </td>

      <td style={{ textAlign: "left" }}>

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
        The category of the coupon — percentage discount, fixed amount discount, or a custom trial period.
      </td>

      <td style={{ textAlign: "left" }}>

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
        For 'free\_trial' discount type, it defines the period number corresponding to the unit period (like 14 for a 14-day trial).
      </td>

      <td style={{ textAlign: "left" }}>

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
        For 'free\_trial' discount type, it specifies the unit of the trial period (day/week/month corresponding to the trial period).
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        unique\_coupon\_code\_api\_id
      </td>

      <td>
        e28zov4fw0v2
      </td>

      <td>
        Unique Coupon Code API ID
      </td>

      <td style={{ textAlign: "left" }}>
        String
      </td>
    </tr>
  </tbody>
</Table>

# Version changelog

### Version 2 - 2/5/2025

* Addition of `unique_coupon_code_api_id`.
