---
title: Subscriptions — ramp pricing - export
excerpt: >-
  Explore the detailed ramp interval data with the Subscriptions - Ramp Pricing
  export.
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

The ramp pricing export function returns comprehensive data on each subscription operating under a ramp priced billing model. This allows for detailed tracking and analysis of various subscription attributes and statuses at different intervals of the ramp pricing lifecycle.

# Filters

### Subscription Status Filter

This filter helps in sorting the subscriptions based on their current status. The different statuses are explained below:

* **Live**: All active subscriptions.
* **Open**: **Live** subscriptions that will renew after the current term.
* **Trial**: **Live** subscriptions that are in a trial period.
* **Paused**: **Live** subscriptions that are currently paused.
* **Canceled**: **Live** subscriptions that will not renew after the current term.
* **Past Due**: **Live** subscriptions with a past-due invoice.
* **Future**: Subscriptions that will become active when the start date arrives.
* **Expired**: Inactive subscriptions.

### Date Range Filters

Under this filter, the subscriptions can be filtered based on the modifications and creations in a selected date range. The details are as follows:

* **Modified**: It includes the subscriptions that were modified in the selected time range. This utilizes the "modified\_at" column in the export, showing only the modified subscriptions while the original ones do not appear.
* **Created**: This includes the subscriptions that were created within the selected timeframe, referring to the "created\_at" column in the export. It also includes those created with a future activation date.

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
        Column Name
      </th>

      <th>
        Example
      </th>

      <th>
        Description
      </th>

      <th style={{ textAlign: "left" }}>
        Type
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        <span id="uuid">uuid</span>
      </td>

      <td>
        b964b5439c2548a489
      </td>

      <td>
        Unique identifier for each subscription, retained despite modifications and aligns with identifiers in other exports like the Subscriptions export.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="ramp_id">ramp\_id</span>
      </td>

      <td>
        101112
      </td>

      <td>
        Unique identifier for ramp pricing, aligning with the current\_ramp\_id value in the subscriptions export.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="unit_amount">unit\_amount</span>
      </td>

      <td>
        14.99
      </td>

      <td>
        Unit amount charged at each ramp interval.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="starting_billing_cycle">starting\_billing\_cycle</span>
      </td>

      <td>
        2
      </td>

      <td>
        The billing cycle at which the ramp interval initiates.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="elapsed_billing_cycles">elapsed\_billing\_cycles</span>
      </td>

      <td>
        2
      </td>

      <td>
        The count of completed billing cycles in the current ramp interval.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="total_billing_cycles">total\_billing\_cycles</span>
      </td>

      <td>
        3
      </td>

      <td>
        The overall billing cycles that a ramp interval encompasses.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="started_at">started\_at</span>
      </td>

      <td>
        2021-05-08 12:53:10 MDT
      </td>

      <td>
        Marks the initiation date of the ramp interval.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="ended_at">ended\_at</span>
      </td>

      <td>
        2021-05-09 12:53:10 MDT
      </td>

      <td>
        Denotes the closure date of the ramp interval.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="estimated_start_date">estimated\_start\_date</span>
      </td>

      <td>
        2021-05-11 12:53:10 MDT
      </td>

      <td>
        The anticipated commencement date for the forthcoming ramp interval.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        subscription\_ramp\_api\_id
      </td>

      <td>
        e28zov4fw0v2
      </td>

      <td>
        Ramp API ID
      </td>

      <td style={{ textAlign: "left" }}>
        String
      </td>
    </tr>

    <tr>
      <td>
        subscription\_api\_id
      </td>

      <td>
        e28zov4fw0v2
      </td>

      <td>
        Subscription API ID
      </td>

      <td style={{ textAlign: "left" }}>
        String
      </td>
    </tr>
  </tbody>
</Table>

# Version changelog

### Version 2 - 2/5/2025

* Addition of `subscription_ramp_api_id` and `subscription_api_id`.
