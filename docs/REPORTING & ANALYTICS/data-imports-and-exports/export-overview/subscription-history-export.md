---
title: Subscriptions — history - export
excerpt: >-
  Unlock a detailed record of subscription alterations with the Subscriptions -
  History export.
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

Please reach out to your Recurly account manager or [support@recurly.com](mailto:support@recurly.com) to have this feature activated in your account.

# Definition

The “Subscriptions - History” section enables users to view the history of each subscription including all versions created following any change to a subscription. This includes monitoring various movements such as upgrades, downgrades, cancellations, trial conversions, and more, facilitating in-depth tracking of a subscriber's lifecycle. It is essential to note that the subscription history export only tracks the changes post the activation of a subscription.

# Filters

### Subscription Status Filter

* **All**: Displays all subscription history status.
* **Trial**: Displays all subscription history respective to trial status.
* **Open**: Displays all subscription history respective to open status.
* **Canceled**: Displays all subscription history respective to canceled status.
* **Expired**: Displays all subscription history respective to expired status.

### Date Range Filters

#### **Activated**

Use this filter to view past versions of activated or reactivated subscriptions within a specified timeframe, utilizing the *subscription\_activated\_at* column.

#### **Created**

View recent creations to all subscriptions within a chosen time range, referring to the *version\_created\_at* column.

#### **Modified**

View recent alterations to all subscriptions within a chosen time range, referring to a combination of *version\_state* and *version\_created\_at* columns.

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

      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        <span id="subscription_uuid">subscription\_uuid</span>
      </td>

      <td>
        434f11do8b297982eb
      </td>

      <td>
        Unique internal identifier for the subscription. Even if a subscription is modified, this identifier is maintained.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="version_uuid">version\_uuid</span>
      </td>

      <td>
        43509049eb30fb
      </td>

      <td>
        Unique internal identifier for the version of a subscription\_uuid. A new version is created when a change is made to a subscription.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="account_code">account\_code</span>
      </td>

      <td>
        123456789, [test@example.com](mailto:test@example.com)
      </td>

      <td>
        Account associated with a given subscription\_uuid.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="subscription_activated_at">subscription\_activated\_at</span>
      </td>

      <td>
        2018-03-24 17:18:46 PDT
      </td>

      <td>
        Date and time the subscription became active (or reactivated) on an account.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="subscription_expires_at">subscription\_expires\_at</span>
      </td>

      <td>
        2018-09-24 17:18:46 PDT
      </td>

      <td>
        Date and time the subscription was/will churn. This field is populated when a subscription cancels with the expected expiration date.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="subscription_state">subscription\_state</span>
      </td>

      <td>
        active, canceled, paused, expired
      </td>

      <td>
        State of the subscription at the time the version was active.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="version_started_at">version\_started\_at</span>
      </td>

      <td>
        2018-03-20 03:22:25 EST
      </td>

      <td>
        The date a change was made to the subscription and thus the new version was created.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="version_ended_at">version\_ended\_at</span>
      </td>

      <td>
        2018-07-20 03:22:25 EST
      </td>

      <td>
        The date a version is no longer active because another change to the subscription is made and a newer version is created.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="version_state">version\_state</span>
      </td>

      <td>
        inactive or active
      </td>

      <td>
        Versions reflecting the current attributes of the subscription (i.e., are currently in use) are "active." All expired versions are "inactive".
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="plan_code">plan\_code</span>
      </td>

      <td>
        bronze\_1
      </td>

      <td>
        The plan that the subscription was actively on while that version was active. Codes are used internally only.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="plan_name">plan\_name</span>
      </td>

      <td>
        Bronze Plan # 1
      </td>

      <td>
        The name of the plan the subscriber was actively on while that version was active.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="subscription_currency">subscription\_currency</span>
      </td>

      <td>
        USD, GBP, CAD
      </td>

      <td>
        The currency associated with that subscription at the time that version was active.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="version_plan_interval_unit">version\_plan\_interval\_unit</span>
      </td>

      <td>
        months, weeks, days, years
      </td>

      <td>
        The interval type at which that subscription is billed while that version was active.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="version_plan_interval_length">version\_plan\_interval\_length</span>
      </td>

      <td>
        any number
      </td>

      <td>
        The length of the interval type at which the subscription is billed at while the version was active.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="version_collection_method">version\_collection\_method</span>
      </td>

      <td>
        automatic, manual
      </td>

      <td>
        Identifies whether the subscription fees are collected via manual or automatic invoicing.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="version_total_billing_cycles">version\_total\_billing\_cycles</span>
      </td>

      <td>
        1
      </td>

      <td>
        The total number of bill cycles that the subscription will bill at the time the version was active.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="version_subscription_quantity">version\_subscription\_quantity</span>
      </td>

      <td>
        1, 2
      </td>

      <td>
        Identifies the quantity of the subscription purchase at the time the version was active.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="version_subscription_unit_amount">version\_subscription\_unit\_amount</span>
      </td>

      <td>
        100
      </td>

      <td>
        Identifies the base price of 1 quantity of the subscription at the time the version was active.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="version_add_on_codes">version\_add\_on\_codes</span>
      </td>

      <td>
        add\_on1, add\_on1, add\_on2
      </td>

      <td>
        A list of add-ons that were active on the subscription at the time the version was active.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="version_add_on_types">version\_add\_on\_types</span>
      </td>

      <td>
        fixed, fixed, usage
      </td>

      <td>
        Lists the type of add-on in corresponding order to the listed add\_on\_codes on the subscription at the time the version was active.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="version_add_on_unit_amounts">version\_add\_on\_unit\_amounts</span>
      </td>

      <td>
        10, 10, 5%
      </td>

      <td>
        Lists the unit amount of the add-on in corresponding order to the listed add\_on\_codes and listed add\_on\_types.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="version_add_ons_total">version\_add\_ons\_total</span>
      </td>

      <td>
        20
      </td>

      <td>
        Sums the add\_on\_unit\_amounts on the subscription at the time the version was active. Does not include usage-based add-ons.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="version_total_recurring_amount">version\_total\_recurring\_amount</span>
      </td>

      <td>
        120
      </td>

      <td>
        (version\_unit\_amount) \* (version\_subscription\_quantity) + version\_add\_on\_total
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="version_in_trial">version\_in\_trial</span>
      </td>

      <td>
        Y, N
      </td>

      <td>
        Indicates whether or not the subscription was in trial while the version was active.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="version_auto_renew">version\_auto\_renew</span>
      </td>

      <td>
        Y, N
      </td>

      <td>
        Indicates whether or not the subscription was set to auto renew while the version was active.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="version_renewal_billing_cycles">version\_renewal\_billing\_cycles</span>
      </td>

      <td>
        1
      </td>

      <td>

      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="version_shipping_method_name">version\_shipping\_method\_name</span>
      </td>

      <td>
        USPS Overnight
      </td>

      <td>
        The shipping method name used at the time when the version was active.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="version_shipping_amount">version\_shipping\_amount</span>
      </td>

      <td>
        5
      </td>

      <td>
        Identifies the shipping price on the subscription at the time the version was active.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="pricing_model">pricing\_model</span>
      </td>

      <td>
        ramp
      </td>

      <td>
        Pricing model of the subscription. Will be either fixed or ramp.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="current_ramp_id">current\_ramp\_id</span>
      </td>

      <td>
        pz82514rbd3s
      </td>

      <td>
        The id of the current ramp interval.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="tax_inclusive">tax\_inclusive</span>
      </td>

      <td>
        false
      </td>

      <td>
        Boolean (TRUE/FALSE) flag to indicate whether subscription is tax inclusive.
      </td>

      <td style={{ textAlign: "left" }}>

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
        string
      </td>
    </tr>
  </tbody>
</Table>

# Version changelog

### Version 7 - 2/5/2025

* Addition of `subscription_api_id`.

### Version 6 - 1/28/2022

* Added columns for tax\_inclusive.

### Version 5 - 12/7/2021

* Added columns for pricing\_model and current\_ramp\_id.

### Version 4 - 5/12/2021

* Removed concatenation in columns: version\_add\_on\_codes, version\_add\_on\_types, version\_add\_on\_unit\_amounts.

### Version 3 - 3/25/2020

* Introduced a new column: version\_add\_on\_tier\_types.

### Version 2 - 1/9/2020

* Incorporated columns for shipping method and amount.
