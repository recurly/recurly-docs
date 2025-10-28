---
title: Subscription add-ons — history  - export
excerpt: >-
  Delve into the rich history of your subscription add-ons and leverage valuable
  insights with our detailed export feature in the "Subscription Add-ons —
  History" section.
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

Explore the subscription add-on history feature that allows tracking all the changes made to a subscription add-on over time. Every time a change or multiple changes are made simultaneously, a new version of the subscription add-on history is created. This feature is vital for keeping historical versions of add-ons that change on subscriptions.

# Filters

### Subscription Status Filter

* **All**: Displays all subscription history status.
* **Trial**: Displays all subscription history respective to trial status.
* **Open**: Displays all subscription history respective to open status.
* **Canceled**: Displays all subscription history respective to canceled status.
* **Expired**: Displays all subscription history respective to expired status.

### Date Range Filters

#### **Activated**

Showcases the past versions of subscription add-ons that were activated or reactivated within the chosen time frame. It utilizes the `subscription_activated_at` column for data representation.

#### **Created**

Depicts the past versions of subscription add-ons generated during a specified time range, utilizing data from the `version_started_at` column.

#### **Modified**

View recent alterations to all subscriptions within a chosen time range, referring to a combination of *version\_state* and version\_started\_at columns.

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
        subscription\_uuid
      </td>

      <td style={{ textAlign: "left" }}>
        434f11do8b297982eb
      </td>

      <td style={{ textAlign: "left" }}>
        Unique internal identifier for the subscription. Even if a subscription is modified, this identifier is maintained.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(32)
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        version\_uuid
      </td>

      <td style={{ textAlign: "left" }}>
        43509049eb30fb
      </td>

      <td style={{ textAlign: "left" }}>
        Unique internal identifier for the version of a subscription\_uuid.\
        A new version if created when a change is made to a subscription. If multiple different changes are made at the same time,  all will be captured in the same new version.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        account\_code
      </td>

      <td style={{ textAlign: "left" }}>
        123456789,\
        [test@example.com](mailto:test@example.com)
      </td>

      <td style={{ textAlign: "left" }}>
        Account associated with a given subscription\_uuid.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(50)
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        subscription\_activated\_at
      </td>

      <td style={{ textAlign: "left" }}>
        2018-03-24 17:18:46 PDT
      </td>

      <td style={{ textAlign: "left" }}>
        Date and time the subscription became active (or reactivated) on an account. Note that this might not always match exactly with the subscription\_created\_At date if a subscription is created with a future start date.
      </td>

      <td style={{ textAlign: "left" }}>
        timestamp
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        subscription\_expires\_at
      </td>

      <td style={{ textAlign: "left" }}>
        2018-09-24 17:18:46 PDT
      </td>

      <td style={{ textAlign: "left" }}>
        Date and time the subscription was/ will churn.  

        This field is populated when a subscription cancels with the expected expiration date.
      </td>

      <td style={{ textAlign: "left" }}>
        timestamp
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        subscription\_state
      </td>

      <td style={{ textAlign: "left" }}>
        active, canceled, paused,\
        expired
      </td>

      <td style={{ textAlign: "left" }}>
        State of the subscription at the time the version was active.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        version\_started\_at
      </td>

      <td style={{ textAlign: "left" }}>
        2018-03-20 03:22:25 EST
      </td>

      <td style={{ textAlign: "left" }}>
        The date a change was made to the subscription and thus the new version was created.
      </td>

      <td style={{ textAlign: "left" }}>
        timestamp
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        version\_ended\_at
      </td>

      <td style={{ textAlign: "left" }}>
        2018-07-20 03:22:25 EST
      </td>

      <td style={{ textAlign: "left" }}>
        The date a version is no longer active because another change to the subscription is a made and a newer version is created.\
        All versions with the version\_state of "inactive" will have a version\_expired\_at date.
      </td>

      <td style={{ textAlign: "left" }}>
        timestamp
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        version\_state
      </td>

      <td style={{ textAlign: "left" }}>
        inactive or active
      </td>

      <td style={{ textAlign: "left" }}>
        the versions of a subscription that reflect the current attributes of that subscription (i.e are currently in use) are "active." All expired versions are "inactive"
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        plan\_code
      </td>

      <td style={{ textAlign: "left" }}>
        bronze\_1
      </td>

      <td style={{ textAlign: "left" }}>
        the plan that the subscription was actively on while that version was active. Codes are used internally only.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(50)
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        plan\_name
      </td>

      <td style={{ textAlign: "left" }}>
        Bronze Plan # 1
      </td>

      <td style={{ textAlign: "left" }}>
        The name of the plan the subscriber was actively on while that version was active.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(25)
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        subscription\_currency
      </td>

      <td style={{ textAlign: "left" }}>
        USD, GBP, CAD
      </td>

      <td style={{ textAlign: "left" }}>
        The currency associated with that subscription at the time that version was active
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(3)
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        version\_plan\_interval\_unit
      </td>

      <td style={{ textAlign: "left" }}>
        months, weeks, days, years
      </td>

      <td style={{ textAlign: "left" }}>
        The interval type at which that subscription is billed while that version was active.  Combined with the version\_plan\_internval\_length, you can understand how often your customer is billed\
        example: 1 month, 2 months, 1 year, etc.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(10)
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        version\_plan\_interval\_length
      </td>

      <td style={{ textAlign: "left" }}>
        any number
      </td>

      <td style={{ textAlign: "left" }}>
        The length of the interval type at which the subscription is billed at while the version was active.\
        Example: 1 month, 2 months, 1 year ,etc
      </td>

      <td style={{ textAlign: "left" }}>
        numeric(10)
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        version\_collection\_method
      </td>

      <td style={{ textAlign: "left" }}>
        automatic, manual
      </td>

      <td style={{ textAlign: "left" }}>
        Identifies whether the subscription fees are collected via manual or automatic invoicing.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        version\_total\_billing\_cycles
      </td>

      <td style={{ textAlign: "left" }}>
        1
      </td>

      <td style={{ textAlign: "left" }}>
        If configured on the plan, the total number of bill cycles that the subscription will bill at the time the version was active.\
         If not specifically configured, the subscription will auto renew and this field will be blank.
      </td>

      <td style={{ textAlign: "left" }}>
        numeric
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        version\_subscription\_quantity
      </td>

      <td style={{ textAlign: "left" }}>
        1, 2
      </td>

      <td style={{ textAlign: "left" }}>
        Identifies the quantity of the subscription purchase at the time the version was active.
      </td>

      <td style={{ textAlign: "left" }}>
        numeric
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        version\_subscription\_unit\_amount
      </td>

      <td style={{ textAlign: "left" }}>
        100
      </td>

      <td style={{ textAlign: "left" }}>
        Identifies the base price of 1 quantity of the subscription at the time the version was active.
      </td>

      <td style={{ textAlign: "left" }}>
        numeric
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        version\_add\_on\_code
      </td>

      <td style={{ textAlign: "left" }}>
        add\_on1, add\_on1,  add\_on2
      </td>

      <td style={{ textAlign: "left" }}>
        A list of add ons that were active on the subscription at the time the version was active.\
        If there is more than one of the same add\_on, it will be listed the same number of times as the quantity.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(50)
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        version\_add\_on\_quantity
      </td>

      <td style={{ textAlign: "left" }}>
        1
      </td>

      <td style={{ textAlign: "left" }}>
        Identifies the quantity of the add-on at the time the version was active.
      </td>

      <td style={{ textAlign: "left" }}>
        numeric
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        version\_add\_on\_type
      </td>

      <td style={{ textAlign: "left" }}>
        fixed, fixed, usage
      </td>

      <td style={{ textAlign: "left" }}>
        Lists the type of add\_on in corresponding order to the listed add\_on\_codes on the subscription at the time the version was active.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        version\_add\_on\_unit\_amount
      </td>

      <td style={{ textAlign: "left" }}>
        10, 10, 5%
      </td>

      <td style={{ textAlign: "left" }}>
        Lists the unit amount of the add\_on in corresponding order to the listed add\_on\_codes and listed add\_on\_types.\
        If the add\_on\_type is "usage" the "%" will be listed
      </td>

      <td style={{ textAlign: "left" }}>
        numeric
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        version\_add\_ons\_total
      </td>

      <td style={{ textAlign: "left" }}>
        20
      </td>

      <td style={{ textAlign: "left" }}>
        Sums the add\_on\_unit\_amounts on the subscription at the time the version was active.\
        Does not include usage based add ons.
      </td>

      <td style={{ textAlign: "left" }}>
        numeric
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        version\_total\_recurring\_amount
      </td>

      <td style={{ textAlign: "left" }}>
        120
      </td>

      <td style={{ textAlign: "left" }}>
        (version\_unit\_amount) \* (version\_subscription\_quantity) + version\_add\_on\_total
      </td>

      <td style={{ textAlign: "left" }}>
        numeric
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        version\_in\_trial
      </td>

      <td style={{ textAlign: "left" }}>
        Y, N
      </td>

      <td style={{ textAlign: "left" }}>
        Indicates whether or not the subscription was in trial while the version was active.
      </td>

      <td style={{ textAlign: "left" }}>
        boolean
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        version\_auto\_renew
      </td>

      <td style={{ textAlign: "left" }}>
        Y, N
      </td>

      <td style={{ textAlign: "left" }}>
        Indicates whether or not the subscription was set to auto renew while the version was active.
      </td>

      <td style={{ textAlign: "left" }}>
        boolean
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        version\_renewal\_billing\_cycles
      </td>

      <td style={{ textAlign: "left" }}>
        1
      </td>

      <td style={{ textAlign: "left" }}>
        Indicated the number of billing cycles a subscription will have after the end of the subscription term.
      </td>

      <td style={{ textAlign: "left" }}>
        numeric
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        external\_sku
      </td>

      <td style={{ textAlign: "left" }}>
        093094f0420
      </td>

      <td style={{ textAlign: "left" }}>
        *
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(50)
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        version\_add\_on\_tier\_type
      </td>

      <td style={{ textAlign: "left" }}>
        flat, tiered, volume, stairstep
      </td>

      <td style={{ textAlign: "left" }}>
        The pricing model used to calculate the costs for the subscriptions based on the quantity purchased.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        version\_add\_on\_source
      </td>

      <td style={{ textAlign: "left" }}>
        *
      </td>

      <td style={{ textAlign: "left" }}>
        *
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        version\_add\_on\_unit\_amount\_decimal
      </td>

      <td style={{ textAlign: "left" }}>
        *
      </td>

      <td style={{ textAlign: "left" }}>
        *
      </td>

      <td style={{ textAlign: "left" }}>
        numeric
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        version\_add\_on\_billing\_model
      </td>

      <td style={{ textAlign: "left" }}>
        *
      </td>

      <td style={{ textAlign: "left" }}>
        *
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        subscription\_api\_id
      </td>

      <td style={{ textAlign: "left" }}>
        e28zov4fw0v2
      </td>

      <td style={{ textAlign: "left" }}>
        Subscription API ID
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        subscription\_add\_on\_api\_id
      </td>

      <td style={{ textAlign: "left" }}>
        e28zov4fw0v2
      </td>

      <td style={{ textAlign: "left" }}>
        Add on API ID
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>
  </tbody>
</Table>

# Version changelog

### Version 6 - 2/5/2025

* Addition of `subscription_api_id` and `subscription_add_on_api_id`.

### **Version 5 - 3/9/2022**

* Introduced a new column version\_add\_on\_billing\_model.

### **Version 4 - 1/22/2021**

* Introduced a new column version\_add\_on\_unit\_amount\_decimal.

### **Version 3 - 6/23/2020**

* Introduced a new column version\_add\_on\_source.

### **Version 2 - 4/2/2020**

* Introduced a new column for external SKU concerning saved item add-ons.
* Introduced a new column version\_add\_on\_tier\_type.
