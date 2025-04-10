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

The "Coupons Redemptions" export in Recurly provides a detailed list of all coupon redemptions in your account. This export is essential for use cases such as determining your most popular coupon this week or analyzing redemptions broken down by coupon code over a specific period. By leveraging these insights, you can evaluate the effectiveness of your discount strategies and gain a deeper understanding of customer engagement.

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

| Id                                                                     | Example                                                  | Description                                                                                                                                     | Data Type (max size) |
| ---------------------------------------------------------------------- | -------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- | :------------------- |
| <span id="coupon_code">coupon\_code</span>                             | 5off                                                     | The code used by the customer to redeem the coupon.                                                                                             | String               |
| <span id="account_code">account\_code</span>                           | 123456789, [janedoe@gmail.com](mailto:janedoe@gmail.com) | Identifies the account on which the coupon was redeemed.                                                                                        | String               |
| <span id="discount">discount</span>                                    | 5                                                        | The fixed amount discounted by the coupon, reflected in the corresponding currency column. A value of 0 indicates a percentage discount coupon. | Numeric              |
| <span id="discount_percent">discount\_percent</span>                   | 5                                                        | The percentage amount discounted by the coupon; will be 0 for fixed amount discount coupons.                                                    | Numeric              |
| <span id="total_discount">total\_discount</span>                       | 100.50                                                   | Total amount discounted to date from the coupon redemption.                                                                                     | Numeric              |
| <span id="applied_at">applied\_at</span>                               | 2013-01-02 06:21:14 PST                                  | The exact date and time the coupon was redeemed; vital for date range filters.                                                                  | Timestamp            |
| <span id="expires_at">expires\_at</span>                               | 2014-01-02 06:21:14 PST                                  | Date and time the redemption expires post its valid duration.                                                                                   | Timestamp            |
| <span id="timeframe">timeframe</span>                                  | forever                                                  | The validity duration of the coupon.                                                                                                            | String               |
| <span id="uuid">uuid</span>                                            | 306f7937d86f088f046dd945a1a24df2                         | Unique identifier for each coupon redemption.                                                                                                   | Varchar (32)         |
| <span id="currency">currency</span>                                    | USD                                                      | Currency applicable to the total\_discount and discount columns.                                                                                | Varchar (3)          |
| <span id="coupon_id">coupon\_id</span>                                 | 1313528357303980000                                      | Unique identifier for the coupon, beneficial when correlating data from the Coupons export.                                                     | String               |
| <span id="subscription_id">subscription\_id</span>                     | 306f7937d86f088f046dd945a1a24df2                         | Unique identifier for the subscription linked to the redemption; only available for subscription-level coupons.                                 | Varchar (32)         |
| <span id="coupon_type">coupon\_type</span>                             | single code, bulk                                        | Distinguishes between single code coupons and bulk coupons with multiple unique codes.                                                          | String               |
| <span id="discount_type">discount\_type</span>                         | percent, fixed\_amount, free\_trial                      | The coupon's discount nature – percentage, fixed amount, or a custom trial period.                                                              | String               |
| <span id="free_trial_coupon_amount">free\_trial\_coupon\_amount</span> | 14                                                       | For free\_trial discount types, it represents the number correlated with the trial period unit.                                                 | Numeric              |
| <span id="free_trial_coupon_unit">free\_trial\_coupon\_unit</span>     | day, week, month                                         | Specifies the unit period for free\_trial type coupons.                                                                                         | String               |
| coupon\_redemption\_api\_id                                            | e28zov4fw0v2                                             | Coupon Redemption API ID                                                                                                                        | String               |

# Version changelog

### Version 2 - 2/5/2025

* Addition of `coupon_redemption_api_id`.