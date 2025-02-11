---
title: Subscriptions  - export
excerpt: >-
  Discover the ins and outs of your subscriptions with the detailed
  Subscriptions export section in Recurly's user guide.
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

The Subscriptions export helps you identify accounts that have stored subscriptions along with all the pertinent details of those subscriptions.

# Filters

Distinguish between different subscription statuses using these filters:

* **Live**: All active subscriptions
* **Renewing**: Live subscriptions set to renew post the present term 
* **Trial**: Subscriptions currently in a trial phase
* **Paused**: Subscriptions that are presently on a pause 
* **Canceled**: Subscriptions that will not renew after the present term concludes 
* **Past Due**: Live subscriptions associated with a past-due invoice 
* **Future**: Subscriptions that will activate on reaching the start date 
* **Expired**: Inactive subscriptions 
* **Last Billing**: Refers to subscription is in its last billing period within the selected timeframe. 

### Date Range Filters

Understand your subscriptions' timelines with the following filters:

* **Activated**: Focuses on subscriptions activated in a chosen time range 
* **Modified**: Shows subscriptions altered in the chosen time frame, excluding the original subscription 
* **Created**: Displays subscriptions created within a selected time frame, including those with future activation dates.

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
        <span id="Column Name">

        Column Name

        </span>
      </th>

      <th>
        Example
      </th>

      <th>
        Description
      </th>

      <th style={{ textAlign: "left" }}>
        Datatype (max size)
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
        Unique internal identifier for the subscription. Even if a subscription is modified, this identifier is maintained.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(32)
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
        Account associated with a given subscription UUID.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(50)
      </td>
    </tr>

    <tr>
      <td>
        <span id="email">email</span>
      </td>

      <td>
        [test@example.com](mailto:test@example.com)
      </td>

      <td>
        Email address associated with a given subscription UUID.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(255)
      </td>
    </tr>

    <tr>
      <td>
        <span id="plan_code">plan\_code</span>
      </td>

      <td>
        basic
      </td>

      <td>
        Plan that the customer is subscribed to with this UUID.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(50)
      </td>
    </tr>

    <tr>
      <td>
        <span id="state">state</span>
      </td>

      <td>
        pending,  active, canceled, expired
      </td>

      <td>
        Current state of the subscription.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="auto_renew">auto\_renew</span>
      </td>

      <td>
        TRUE, FALSE
      </td>

      <td>
        Defaults to TRUE for auto-renewing subscriptions. FALSE if subscription configured to expire at the end of the current term.
      </td>

      <td style={{ textAlign: "left" }}>
        boolean
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
        Identifies the currency being charged with this subscription.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(3)
      </td>
    </tr>

    <tr>
      <td>
        <span id="quantity">quantity</span>
      </td>

      <td>
        1
      </td>

      <td>
        Identifies the quantity of the subscription purchase.
      </td>

      <td style={{ textAlign: "left" }}>
        numeric
      </td>
    </tr>

    <tr>
      <td>
        <span id="unit_amount">unit\_amount</span>
      </td>

      <td>
        99
      </td>

      <td>
        Identifies the base price of 1 quantity of the subscription
      </td>

      <td style={{ textAlign: "left" }}>
        numeric
      </td>
    </tr>

    <tr>
      <td>
        <span id="add_on_amount">add\_on\_amount</span>
      </td>

      <td>
        15
      </td>

      <td>
        Identifies any additional charges to the subscription base fee from add\_ons.
      </td>

      <td style={{ textAlign: "left" }}>
        numeric
      </td>
    </tr>

    <tr>
      <td>
        <span id="total_recurring_amount">total\_recurring\_amount</span>
      </td>

      <td>
        114
      </td>

      <td>
        Identifies total recurring charges - unit\_amount x quantity + add\_on\_amount.
      </td>

      <td style={{ textAlign: "left" }}>
        numeric
      </td>
    </tr>

    <tr>
      <td>
        <span id="current_period_started_at">current\_period\_started\_at</span>
      </td>

      <td>
        2009-12-04 00:46:59 PST
      </td>

      <td>
        Date and time that the current billing period starts at.
      </td>

      <td style={{ textAlign: "left" }}>
        timestamp
      </td>
    </tr>

    <tr>
      <td>
        <span id="current_period_ends_at">current\_period\_ends\_at</span>
      </td>

      <td>
        2009-01-04 00:46:59 PST
      </td>

      <td>
        Date and time that the current billing period ends at
      </td>

      <td style={{ textAlign: "left" }}>
        timestamp
      </td>
    </tr>

    <tr>
      <td>
        <span id="trial_started_at">trial\_started\_at</span>
      </td>

      <td>
        2010-03-24 17:18:46 PDT
      </td>

      <td>
        Date and time that a trial period began on the subscription.
      </td>

      <td style={{ textAlign: "left" }}>
        timestamp
      </td>
    </tr>

    <tr>
      <td>
        <span id="trial_ends_at">trial\_ends\_at</span>
      </td>

      <td>
        2010-04-23 17:18:46 PDT
      </td>

      <td>
        Date and time that a trial period ends on the subscription.
      </td>

      <td style={{ textAlign: "left" }}>
        timestamp
      </td>
    </tr>

    <tr>
      <td>
        <span id="total_billing_cycles">total\_billing\_cycles</span>
      </td>

      <td>
        1
      </td>

      <td>
        This is the total number of billing periods in the current term.
      </td>

      <td style={{ textAlign: "left" }}>
        numeric
      </td>
    </tr>

    <tr>
      <td>
        <span id="remaining_billing_cycles">remaining\_billing\_cycles</span>
      </td>

      <td>
        0
      </td>

      <td>
        This is the remaining number of billing periods remaining in the subscription term that will bill. Always 0 for subscriptions with a single billing period term set to auto\_renew=true
      </td>

      <td style={{ textAlign: "left" }}>
        numeric
      </td>
    </tr>

    <tr>
      <td>
        <span id="activated_at">activated\_at</span>
      </td>

      <td>
        2010-03-24 17:18:46 PDT
      </td>

      <td>
        Date and time the subscription became active on an account. This might not match to the subscription\_created\_at date if the subscription is added with a future start date.
      </td>

      <td style={{ textAlign: "left" }}>
        timestamp
      </td>
    </tr>

    <tr>
      <td>
        <span id="modified_at">modified\_at</span>
      </td>

      <td>
        2010-03-24 17:18:44 PDT
      </td>

      <td>
        Date and time the subscription was last updated.
      </td>

      <td style={{ textAlign: "left" }}>
        timestamp
      </td>
    </tr>

    <tr>
      <td>
        <span id="canceled_at">canceled\_at</span>
      </td>

      <td>
        2010-03-28 22:54:46 PDT
      </td>

      <td>
        Date and time the subscription was canceled.
      </td>

      <td style={{ textAlign: "left" }}>
        timestamp
      </td>
    </tr>

    <tr>
      <td>
        <span id="expires_at">expires\_at</span>
      </td>

      <td>
        2010-04-23 22:51:53 PDT
      </td>

      <td>
        Date and time the subscription was/ will churn. This field is populated when a subscription cancels with the expected expiration date.
      </td>

      <td style={{ textAlign: "left" }}>
        timestamp
      </td>
    </tr>

    <tr>
      <td>
        <span id="maintenance_url">maintenance\_url</span>
      </td>

      <td>
        app.recurly.com/account/test
      </td>

      <td>
        Link to the customer's hosted account maintenance URL.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="net_terms">net\_terms</span>
      </td>

      <td>
        102
      </td>

      <td>
        Identifies the net\_terms agreement associated with the subscription.
      </td>

      <td style={{ textAlign: "left" }}>
        numeric
      </td>
    </tr>

    <tr>
      <td>
        <span id="po_number">po\_number</span>
      </td>

      <td>
        213123
      </td>

      <td>
        For manual invoicing, this identifies the PO number associated with the subscription.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(50)
      </td>
    </tr>

    <tr>
      <td>
        <span id="collection_method">collection\_method</span>
      </td>

      <td>
        automatic/manual
      </td>

      <td>
        Identifies whether the subscription fees are collected via manual or automatic invoicing.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="plan_name">plan\_name</span>
      </td>

      <td>
        Gold
      </td>

      <td>
        The name of the plan associated with the subscription. This is the current name of the plan.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(255)
      </td>
    </tr>

    <tr>
      <td>
        <span id="started_with_gift">started\_with\_gift</span>
      </td>

      <td>
        TRUE, FALSE
      </td>

      <td>
        TRUE if the subscription was started with a gift card, whether or not billing information was collected.
      </td>

      <td style={{ textAlign: "left" }}>
        boolean
      </td>
    </tr>

    <tr>
      <td>
        <span id="no_billing_info_reason">no\_billing\_info\_reason</span>
      </td>

      <td>
        plan\_free\_trial
      </td>

      <td>
        Identifies the reason why a subscription did not have billing information at time of renewal/activation.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="converted_at">converted\_at</span>
      </td>

      <td>
        2016-09-02 15:53:18 UTC
      </td>

      <td>
        Date of the first successful transaction for the subscription. This field is only used for gifts cards and cardless free trial conversions. In other words, it will only have a value if started\_with\_gift is `TRUE` OR no\_billing\_info\_reason is "plan\_free" trial. " Converted\_at compared to the subscription's activated\_at will give you the time to conversion.
      </td>

      <td style={{ textAlign: "left" }}>
        timestamp
      </td>
    </tr>

    <tr>
      <td>
        <span id="paused_at">paused\_at</span>
      </td>

      <td>
        2018-05-13 00:00:12 MDT
      </td>

      <td>
        Date of subscription pause initiation.
      </td>

      <td style={{ textAlign: "left" }}>
        timestamp
      </td>
    </tr>

    <tr>
      <td>
        <span id="remaining_pause_cycles">remaining\_pause\_cycles</span>
      </td>

      <td>
        9
      </td>

      <td>
        Identifies the number of remaining billing cycles for the subscription that is either currently paused or scheduled to pause.
      </td>

      <td style={{ textAlign: "left" }}>
        numeric
      </td>
    </tr>

    <tr>
      <td>
        <span id="current_term_started_at">current\_term\_started\_at</span>
      </td>

      <td>
        2018-12-04 00:46:59 PST
      </td>

      <td>
        Date and time that the current term started at.  This currently is an unpopulated field relating to an upcoming feature which will be released later this year.
      </td>

      <td style={{ textAlign: "left" }}>
        timestamp
      </td>
    </tr>

    <tr>
      <td>
        <span id="current_term_ends_at">current\_term\_ends\_at</span>
      </td>

      <td>
        2019-12-04 00:46:59 PST
      </td>

      <td>
        Date and time that the current term ends at.  This currently is an unpopulated field relating to an upcoming feature which will be released later this year.
      </td>

      <td style={{ textAlign: "left" }}>
        timestamp
      </td>
    </tr>

    <tr>
      <td>
        <span id="renewal_billing_cycles">renewal\_billing\_cycles</span>
      </td>

      <td>
        1
      </td>

      <td>
        The length of a subscription's next term, if auto\_renew = true,  NIL if subscription auto\_renew = false
      </td>

      <td style={{ textAlign: "left" }}>
        numeric
      </td>
    </tr>

    <tr>
      <td>
        <span id="shipping_amount_in_cents">shipping\_amount\_in\_cents</span>
      </td>

      <td>
        500
      </td>

      <td>
        The shipping fee on the subscription, in cents.
      </td>

      <td style={{ textAlign: "left" }}>
        numeric
      </td>
    </tr>

    <tr>
      <td>
        <span id="shipping_method_code">shipping\_method\_code</span>
      </td>

      <td>
        usps-overnight
      </td>

      <td>
        The code from the shipping method (created through the UI).
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(50)
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
        string
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
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="tax_inclusive">tax\_inclusive</span>
      </td>

      <td>
        true
      </td>

      <td>
        Indicates whether the subscription is billed inclusively or exclusively of tax.
      </td>

      <td style={{ textAlign: "left" }}>
        boolean
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

    <tr>
      <td>
        gateway\_code
      </td>

      <td>
        e28zov4fw0v2
      </td>

      <td>
        Gateway Code
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>
  </tbody>
</Table>

# Version changelog

#### Version 6 - 2/5/2025

* Addition of `subscription_api_id` and `gateway_code`.

#### Version 5 - 1/10/2022

* Added a column to indicate tax inclusive. 

#### Version 4 - 12/7/2021

* Added a column for the pricing model
* Introduced a column for current\_ramp\_id

#### Version 3 - 5/2/2019

* A new column was added to show the Shipping Cost
* Added a column for indicating the Shipping Method

#### Version 2 - 9/6/2018

* Introduced column additions for Custom Fields 
* Custom fields will now be the last column in the export and will only appear if exports are enabled in the custom field definition
