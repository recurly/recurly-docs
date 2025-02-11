---
title: Subscriptions — churned - export
excerpt: Track and export data on churned Recurly subscriptions with ease.
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

In the Recurly platform, a "Churned Subscription" refers to subscriptions that have churned and are no longer active. This information is vital in understanding subscription lifecycles and trends in user retention.

# Filters

### Time Range Filter

To get specific data, use the Time Range Filter which exports all the subscriptions that expired during a selected time frame. This filter uses the "expired\_at" column in the export. Note that a subscription does not churn until it has expired, and the "canceled\_at" and "expired\_at" dates are not the same.

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

<Table align={["left","left","left"]}>
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
    </tr>
  </thead>

  <tbody>
    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="uuid">uuid</span>
      </td>

      <td style={{ textAlign: "left" }}>
        5eg5bcc7ef8211e0a908005056b00005
      </td>

      <td style={{ textAlign: "left" }}>
        Unique identifier for a specific subscription plan.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="account_code">account\_code</span>
      </td>

      <td style={{ textAlign: "left" }}>
        123456789, [test@example.com](mailto:test@example.com)
      </td>

      <td style={{ textAlign: "left" }}>
        Account associated with a given subscription UUID.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="email">email</span>
      </td>

      <td style={{ textAlign: "left" }}>
        [test@example.com](mailto:test@example.com)
      </td>

      <td style={{ textAlign: "left" }}>
        Email address associated with a given subscription UUID.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="plan_code">plan\_code</span>
      </td>

      <td style={{ textAlign: "left" }}>
        basic
      </td>

      <td style={{ textAlign: "left" }}>
        Plan that the customer is subscribed to with this UUID.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="state">state</span>
      </td>

      <td style={{ textAlign: "left" }}>
        pending, modified, converted, active, canceled, expired
      </td>

      <td style={{ textAlign: "left" }}>
        Current state of the subscription. Modified and converted are depreciated states
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="auto_renew">auto\_renew</span>
      </td>

      <td style={{ textAlign: "left" }}>
        TRUE
      </td>

      <td style={{ textAlign: "left" }}>
        Defaults to TRUE for auto-renewing subscriptions. FALSE if subscription set to expire at end of current term.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="currency">currency</span>
      </td>

      <td style={{ textAlign: "left" }}>
        USD
      </td>

      <td style={{ textAlign: "left" }}>
        Identifies the currency being charged with this subscription.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="quantity">quantity</span>
      </td>

      <td style={{ textAlign: "left" }}>
        1
      </td>

      <td style={{ textAlign: "left" }}>
        Identifies the quantity of the subscription purchase.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="unit_amount">unit\_amount</span>
      </td>

      <td style={{ textAlign: "left" }}>
        99
      </td>

      <td style={{ textAlign: "left" }}>
        Identifies the base price of 1 quantity of the subscription.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="add_on_amount">add\_on\_amount</span>
      </td>

      <td style={{ textAlign: "left" }}>
        15
      </td>

      <td style={{ textAlign: "left" }}>
        Identifies any additional charges to the subscription base fee from add\_ons.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="total_recurring_amount">total\_recurring\_amount</span>
      </td>

      <td style={{ textAlign: "left" }}>
        114
      </td>

      <td style={{ textAlign: "left" }}>
        Identifies total recurring charges - unit\_amount x quantity + add\_on\_amount.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="current_period_started_at">current\_period\_started\_at</span>
      </td>

      <td style={{ textAlign: "left" }}>
        2009-12-04 00:46:59 PST
      </td>

      <td style={{ textAlign: "left" }}>
        Date and time that the current billing period started. \*
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="current_period_ends_at">current\_period\_ends\_at</span>
      </td>

      <td style={{ textAlign: "left" }}>
        2009-12-04 00:46:59 PST
      </td>

      <td style={{ textAlign: "left" }}>
        Date and time that the current billing period ends at.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="trial_started_at">trial\_started\_at</span>
      </td>

      <td style={{ textAlign: "left" }}>
        2010-03-24 17:18:46 PDT
      </td>

      <td style={{ textAlign: "left" }}>
        Date and time that a trial period began on the subscription.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="trial_ends_at">trial\_ends\_at</span>
      </td>

      <td style={{ textAlign: "left" }}>
        2010-04-23 17:18:46 PDT
      </td>

      <td style={{ textAlign: "left" }}>
        Date and time that a trial period ends on the subscription.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="total_billing_cycles">total\_billing\_cycles</span>
      </td>

      <td style={{ textAlign: "left" }}>
        1
      </td>

      <td style={{ textAlign: "left" }}>
        This is the total number billing periods in the subscription term.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="remaining_billing_cycles">remaining\_billing\_cycles</span>
      </td>

      <td style={{ textAlign: "left" }}>
        0
      </td>

      <td style={{ textAlign: "left" }}>
        Number of remaining billing periods in the subscription’s current term. Will always be 0 if subscription term has 1 billing period
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="renewal_billing_cycles">renewal\_billing\_cycles</span>
      </td>

      <td style={{ textAlign: "left" }}>
        1
      </td>

      <td style={{ textAlign: "left" }}>
        Number of billing periods in the subscription’s next term. Will default to plan’s total\_billing\_cycles unless customized. Nil if auto\_renew = false
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="current_term_started_at">current\_term\_started\_at</span>
      </td>

      <td style={{ textAlign: "left" }}>
        2018-09-02 15:53:18 UTC
      </td>

      <td style={{ textAlign: "left" }}>
        Start date of the subscription’s current term
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="current_term_ends_at">current\_term\_ends\_at</span>
      </td>

      <td style={{ textAlign: "left" }}>
        2018-10-02 15:53:18 UTC
      </td>

      <td style={{ textAlign: "left" }}>
        End date of the subscription’s current term.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="activated_at">activated\_at</span>
      </td>

      <td style={{ textAlign: "left" }}>
        2010-03-24 17:18:46 PDT
      </td>

      <td style={{ textAlign: "left" }}>
        Date and time the subscription was added to the account.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="modified_at">modified\_at</span>
      </td>

      <td style={{ textAlign: "left" }}>
        2010-03-24 17:18:44 PDT
      </td>

      <td style={{ textAlign: "left" }}>
        Date and time the subscription was last updated.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="canceled_at">canceled\_at</span>
      </td>

      <td style={{ textAlign: "left" }}>
        2010-03-28 22:54:46 PDT
      </td>

      <td style={{ textAlign: "left" }}>
        Date and time the subscription was canceled.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="expires_at">expires\_at</span>
      </td>

      <td style={{ textAlign: "left" }}>
        2010-04-23 22:51:53 PDT
      </td>

      <td style={{ textAlign: "left" }}>
        Date and time the subscription was terminated. **Used for date range filter** 
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="maintenance_url">maintenance\_url</span>
      </td>

      <td style={{ textAlign: "left" }}>
        app.recurly.com/account/sdasdasdad213525asdad
      </td>

      <td style={{ textAlign: "left" }}>
        Link to the customer's hosted account maintenance URL.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="net_terms">net\_terms</span>
      </td>

      <td style={{ textAlign: "left" }}>
        on-receipt
      </td>

      <td style={{ textAlign: "left" }}>
        Identifies the net\_terms agreement associated with the subscription.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="po_number">po\_number</span>
      </td>

      <td style={{ textAlign: "left" }}>
        213123
      </td>

      <td style={{ textAlign: "left" }}>
        For manual invoicing, this identifies the PO number associated with the subscription.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="collection_method">collection\_method</span>
      </td>

      <td style={{ textAlign: "left" }}>
        automatic/manual
      </td>

      <td style={{ textAlign: "left" }}>
        Identifies whether the subscription fees are collected via manual or automatic invoicing
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="plan_name">plan\_name</span>
      </td>

      <td style={{ textAlign: "left" }}>
        Basic Plan
      </td>

      <td style={{ textAlign: "left" }}>
        The plan name of the subscription at the time the subscription expired
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="expiration_reason">expiration\_reason</span>
      </td>

      <td style={{ textAlign: "left" }}>
        Canceled, Non-payment, Fixed billing cycles, Tax Location Invalid, Nonpayment\_gift, Nonpayment\_trial
      </td>

      <td style={{ textAlign: "left" }}>
        The reason that the subscription expired. Note that nonpayment\_Trial only relates to cardless subscriptions trials
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="ship_address_id">ship\_address\_id</span>
      </td>

      <td style={{ textAlign: "left" }}>
        2019760433389770000
      </td>

      <td style={{ textAlign: "left" }}>
        The unique ID assigned to the shipping address
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="ship_address_nickname">ship\_address\_nickname</span>
      </td>

      <td style={{ textAlign: "left" }}>
        Julie
      </td>

      <td style={{ textAlign: "left" }}>
        The nickname given to the shipping address
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="ship_address_firstname">ship\_address\_firstname</span>
      </td>

      <td style={{ textAlign: "left" }}>
        Julie
      </td>

      <td style={{ textAlign: "left" }}>
        The first name associated with the shipping address
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="ship_address_lastname">ship\_address\_lastname</span>
      </td>

      <td style={{ textAlign: "left" }}>
        Smith
      </td>

      <td style={{ textAlign: "left" }}>
        The last name associated with the shipping address
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="ship_address_company_name">ship\_address\_company\_name</span>
      </td>

      <td style={{ textAlign: "left" }}>
        Big Company
      </td>

      <td style={{ textAlign: "left" }}>
        The company name associated with the shipping address
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="ship_address_street1">ship\_address\_street1</span>
      </td>

      <td style={{ textAlign: "left" }}>
        321 Michigan Street
      </td>

      <td style={{ textAlign: "left" }}>
        The first line of the street address for the shipping address
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="ship_address_street2">ship\_address\_street2</span>
      </td>

      <td style={{ textAlign: "left" }}>
        Apt 1
      </td>

      <td style={{ textAlign: "left" }}>
        The second line of the street address for the shipping address
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="ship_address_city">ship\_address\_city</span>
      </td>

      <td style={{ textAlign: "left" }}>
        West Bloomfield
      </td>

      <td style={{ textAlign: "left" }}>
        The city for the shipping address
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="ship_address_state">ship\_address\_state</span>
      </td>

      <td style={{ textAlign: "left" }}>
        MI
      </td>

      <td style={{ textAlign: "left" }}>
        The state for the shipping address
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="ship_address_zip">ship\_address\_zip</span>
      </td>

      <td style={{ textAlign: "left" }}>
        48322
      </td>

      <td style={{ textAlign: "left" }}>
        The zip or postal code for the shipping address
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="ship_address_country">ship\_address\_country</span>
      </td>

      <td style={{ textAlign: "left" }}>
        US
      </td>

      <td style={{ textAlign: "left" }}>
        The country for the shipping address
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="ship_address_vat">ship\_address\_vat</span>
      </td>

      <td style={{ textAlign: "left" }}>
        123456789
      </td>

      <td style={{ textAlign: "left" }}>
        The VAT number associated with the shipping address
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="ship_address_email">ship\_address\_email</span>
      </td>

      <td style={{ textAlign: "left" }}>
        [jsmith@example.com](mailto:jsmith@example.com)
      </td>

      <td style={{ textAlign: "left" }}>
        The email address associated with the shipping address
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="ship_address_phone">ship\_address\_phone</span>
      </td>

      <td style={{ textAlign: "left" }}>
        248-555-1212
      </td>

      <td style={{ textAlign: "left" }}>
        The phone number associated with the shipping address
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="started_with_gift">started\_with\_gift</span>
      </td>

      <td style={{ textAlign: "left" }}>
        TRUE, FALSE
      </td>

      <td style={{ textAlign: "left" }}>
        `TRUE` if the subscription was started with a gift card, whether or not billing information was collected.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="converted_at">converted\_at</span>
      </td>

      <td style={{ textAlign: "left" }}>
        2016-09-02 15:53:18 UTC
      </td>

      <td style={{ textAlign: "left" }}>
        Date of the first successful transaction for the subscription.\
        This field is only used for gifts cards and cardless free trial conversions.\
        In other words, it will only have a value if started\_with\_gift is `TRUE` OR no\_billing\_info\_reason is "plan\_free"trial." Converted\_at compared to the subscription's activated\_at will give you the time to conversion.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="no_billing_info_reason">no\_billing\_info\_reason</span>
      </td>

      <td style={{ textAlign: "left" }}>
        plan\_free\_trial
      </td>

      <td style={{ textAlign: "left" }}>
        Identifies the reason why a subscription did not have billing information at time of renewal/activation.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="shipping_amount_in_cents">shipping\_amount\_in\_cents</span>
      </td>

      <td style={{ textAlign: "left" }}>
        500
      </td>

      <td style={{ textAlign: "left" }}>
        The amount of the shipping fee on the subscription, in cents.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="shipping_method_code">shipping\_method\_code</span>
      </td>

      <td style={{ textAlign: "left" }}>
        usps\_overnight
      </td>

      <td style={{ textAlign: "left" }}>
        The code of the Shipping Method from configuration.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="pricing_model">pricing\_model</span>
      </td>

      <td style={{ textAlign: "left" }}>
        ramp
      </td>

      <td style={{ textAlign: "left" }}>
        Pricing model of the subscription. Will be either fixed or ramp.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="current_ramp_id">current\_ramp\_id</span>
      </td>

      <td style={{ textAlign: "left" }}>
        pz82514rbd3s
      </td>

      <td style={{ textAlign: "left" }}>
        The id of the current ramp interval.
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
    </tr>
  </tbody>
</Table>

# Version changelog

### Version 4 - 2/5/2025

* Addition of `subscription_api_id`.

### Version 3 - 12/7/2021

* Column added for pricing\_model 
* Column added for current\_ramp\_id

### Version 2 - 5/2/2019

* Column added for Shipping Cost
* Column added for Shipping Method
