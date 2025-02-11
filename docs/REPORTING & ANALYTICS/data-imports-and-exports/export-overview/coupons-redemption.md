---
title: Coupons redemption - export
excerpt: Dive into detailed insights with the Coupon Redemptions export section.
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

To access this export feature, ensure that the "Multiple Coupons Per Account" option is activated in your Coupon Settings; otherwise, it won't appear on the Exports page.

# Definition

The "Coupon Redemptions" export in Recurly provides a comprehensive list of all coupon redemptions that have taken place in your account. This export function is a vital tool for tracking the utilization of coupons on your platform. Understanding when and how coupons were redeemed can offer deep insights into customer behavior and the effectiveness of your discount strategies.

# Filters

As of now, the export does not offer filters to isolate data based on specific coupons before downloading. Users can only filter the data by the time range, focusing on the '**applied\_at**' column to understand when the redemption occurred.

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
        Id
      </th>

      <th>
        Example
      </th>

      <th>
        Description
      </th>

      <th style={{ textAlign: "left" }}>
        Data Type (max size)
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
        The code used by the customer to redeem the coupon.
      </td>

      <td style={{ textAlign: "left" }}>
        String
      </td>
    </tr>

    <tr>
      <td>
        <span id="account_code">account\_code</span>
      </td>

      <td>
        123456789, [janedoe@gmail.com](mailto:janedoe@gmail.com)
      </td>

      <td>
        Identifies the account on which the coupon was redeemed.
      </td>

      <td style={{ textAlign: "left" }}>
        String
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
        The fixed amount discounted by the coupon, reflected in the corresponding currency column. A value of 0 indicates a percentage discount coupon.
      </td>

      <td style={{ textAlign: "left" }}>
        Numeric
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
        The percentage amount discounted by the coupon; will be 0 for fixed amount discount coupons.
      </td>

      <td style={{ textAlign: "left" }}>
        Numeric
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
        Total amount discounted to date from the coupon redemption.
      </td>

      <td style={{ textAlign: "left" }}>
        Numeric
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
        The exact date and time the coupon was redeemed; vital for date range filters.
      </td>

      <td style={{ textAlign: "left" }}>
        Timestamp
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
        Date and time the redemption expires post its valid duration.
      </td>

      <td style={{ textAlign: "left" }}>
        Timestamp
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
        The validity duration of the coupon.
      </td>

      <td style={{ textAlign: "left" }}>
        String
      </td>
    </tr>

    <tr>
      <td>
        <span id="uuid">uuid</span>
      </td>

      <td>
        306f7937d86f088f046dd945a1a24df2
      </td>

      <td>
        Unique identifier for each coupon redemption.
      </td>

      <td style={{ textAlign: "left" }}>
        Varchar (32)
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
        Currency applicable to the total\_discount and discount columns.
      </td>

      <td style={{ textAlign: "left" }}>
        Varchar (3)
      </td>
    </tr>

    <tr>
      <td>
        <span id="coupon_id">coupon\_id</span>
      </td>

      <td>
        1313528357303980000
      </td>

      <td>
        Unique identifier for the coupon, beneficial when correlating data from the Coupons export.
      </td>

      <td style={{ textAlign: "left" }}>
        String
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
        Unique identifier for the subscription linked to the redemption; only available for subscription-level coupons.
      </td>

      <td style={{ textAlign: "left" }}>
        Varchar (32)
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
        Distinguishes between single code coupons and bulk coupons with multiple unique codes.
      </td>

      <td style={{ textAlign: "left" }}>
        String
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
        The coupon's discount nature – percentage, fixed amount, or a custom trial period.
      </td>

      <td style={{ textAlign: "left" }}>
        String
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
        For free\_trial discount types, it represents the number correlated with the trial period unit.
      </td>

      <td style={{ textAlign: "left" }}>
        Numeric
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
        Specifies the unit period for free\_trial type coupons.
      </td>

      <td style={{ textAlign: "left" }}>
        String
      </td>
    </tr>

    <tr>
      <td>
        coupon\_redemption\_api\_id
      </td>

      <td>
        e28zov4fw0v2
      </td>

      <td>
        Coupon Redemption API ID
      </td>

      <td style={{ textAlign: "left" }}>
        String
      </td>
    </tr>
  </tbody>
</Table>

# Version changelog

### Version 2 - 2/5/2025

* Addition of `coupon_redemption_api_id`.
