---
title: Usage-based billing
excerpt: >-
  Explore the dynamic and flexible Usage-Based Billing model offered by Recurly.
  Discover how to structure your subscription plans in alignment with your
  customers' usage, fostering value and customer satisfaction.
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

The Usage-Based Billing Model from Recurly empowers businesses to establish a “pay for what you use” strategy, ideal for aligning price directly with value. Under this model, you bill your customers at the end of each billing cycle or subscription term based on their specific usage, ensuring fairness and flexibility. This model is perfect for businesses whose customers' consumption levels vary, as it prevents overcharging, charges the customer for what they have used, and encourages customer satisfaction and loyalty.

# Key benefits

* **Value-aligned pricing**: Enables pricing strategies that reflect customer usage for a fair, value-focused model.
* **Versatile plan creation**: Offers a range of options combining usage-based billing with base fees and add-ons.
* **Enhanced transparency and reporting**: Automates billing calculations and provides customers and finance teams with clear, actionable usage data.

# Example

To better illustrate the functionality of usage-based billing, we’ve provided a few examples across different industries:

| Industry      | Example                                                                                                                                                                                                            |
| :------------ | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Digital Media | ACME, a movie streaming platform, charges $20 per subscription + additional fees for their “Currently In Theaters” service, based on the amount of videos the user streams a month that are currently in theaters. |

# Usage-based add-on pricing strategies

Recurly equips you with two pricing strategies for usage-based add-ons, namely "Cumulative" and "Last recorded". 

The "Cumulative" strategy aggregates the total usage logged throughout the billing period, then multiplies the unit price to compute the subtotal. Conversely, the "Last recorded" strategy considers only the most recent usage logged during the billing period and multiplies it by the unit price to calculate the subtotal.

For instance, with "Cumulative" pricing, logging 1 GB per day for 30 days results in a charge for 30 GB of usage. On the other hand, "Last recorded" pricing could log 3 GB daily for 29 days and 2 GB on the 30th, resulting in a charge for 2 GB of usage at the end of the billing period.

### Pricing strategy selection

A usage-based plan can follow one pricing strategy at a time. You can switch the pricing strategy of a usage-based add-on whenever needed. However, the new strategy will only apply to subscriptions created after the change. To modify the pricing strategy of an existing usage-based add-on on an account, modify the pricing directly on the subscription. 

## Accumulation and billing of usage

Usage can be gathered and billed per billing cycle or over the entire term of the subscription.

## Measured units

Measured units describe the usage for a usage-based add-on, enabling tracking and reporting across multiple add-ons and plans.

* Measured units can be created while forming a usage-based add-on in a plan or by visiting the "Measured Units" page under the Configuration section of your Admin Console.
* Any changes to the measured unit will instantly update your plan and any subscriptions.
* A measured unit can be deleted only if it isn't used in a plan. It should be removed from all plans before deletion on the Measured Units page.
* Measured units are mandatory for all usage add-ons. They will only be visible to subscribers for price per unit usage add-ons.

## Setting up a usage-based subscription

### Methods

Subscriptions to your usage-based plans can be made through the API, Checkout, Hosted Payment Page, or Admin Console. The details specific to usage-based plans for the Hosted Pages and Admin Console are detailed below.

### Checkout and Hosted payment pages

* Usage-based add-ons appear automatically on your Checkout or Hosted Payment Page for the plan, but their cost isn't included in the Order Total as all usage fees are billed at the end of the billing cycle.
* Fixed price usage-based add-ons will display the price and measured unit to the right of the add-on name.

### Support for decimal usage quantities

Integration partners, including Xero, QuickBooks Online, Salesforce, NetSuite, Avalara, Vertex, and Kount, offer varying degrees of support for quantity decimal data. 

# Integration partners & support for decimal usage quantities

**Xero** Xero will receive the quantity data and round the quantity to the nearest 4th decimal place. Xero is the end destination, so the original quantity logged in Recurly will remain unaltered, reflecting the original amount of decimal places.

**QuickBooks Online** QuickBooks will receive the quantity data and round the quantity to the nearest 7th decimal place. QuickBooks is the end destination, so the quantity logged in Recurly will remain unaltered, reflecting the original amount of decimal places.

**Salesforce** Salesforce will receive the quantity decimal data and round to the 2nd decimal place for quantity. It can also be altered in Salesforce during order submission but only up to two decimal places.

**NetSuite** Netsuite will receive the quantity data and round the quantity to the nearest 8th decimal place. NetSuite is the end destination, so the original quantity logged in Recurly will remain unaltered, reflecting the original amount of decimal places.

**Avalara**Avalara will receive the quantity data and round the quantity to the nearest 9th decimal place, thus will support the same amount of decimal places logged via Recurly.

**Vertex** Vertex does not receive quantity data, only the price sent from Recurly, thus, no impact in existing experience will be present with the Vertex integration.

**Kount** Recurly sends line-item data to Kount, which includes the Quantity field, where Kount then evaluates this data and sends back a fraud assessment score. As long as the score is above a certain threshold, Recurly deems it does not qualify as fraud. The line item data we pass through is sent as an integer, which will not be impacted by quantities logged in decimals and will not impact the decimal number shown within Recurly.

## Reporting and data export

### Reporting

* The transactions report will include your usage-based add-on revenue.
* The MRR report will not account for usage-based add-on revenue.
* There are currently no additional reports dedicated to usage-based add-ons.

### Data export

For simple analysis, you can export data about usage add-ons and usage records. Two key exports are the Subscriptions Add-Ons Export and Subscriptions Usage Export.

The export called "Subscriptions Usage Records" provides the individual usage records logged for your customer's usage-based subscription add-ons. This data is useful for financial reporting, as well as product and marketing analysis.

### Quantity-based pricing and exports

The exports will include tier\_type but not detailed tiers pricing information. For access to specific tiers for a plan, subscription, or usage record, consider using the API responses.

## Updates to email templates

These templates offer complete support for usage-based add-ons:

* New Subscription
* New Invoice
* Invoice Past Due
* Subscription Change
* Subscription Canceled
* Payment Confirmation
* Payment Declined

Invoices contain a quantity (Qty) column, and subscription pricing displays include additional usage-based add-on fees. If you've customized these templates, you can reset them to view the changes, or update your customized version to include our add-on email parameters:

```
{#subscription_add_ons}} 
  {{#add_on_usage_based?}} add_on_name: {{{add_on_name}}}<br />
    add_on_price: {{{add_on_price}}}<br /> 
    Add_on_measured_unit_display_name:   
 {{{add_on_measured_unit_display_name}}}<br /> 
{{/add_on_usage_based?}} {{/subscription_add_ons}}.
```

## Proration on usage-based subscription

Proration is the adjustment of a cost based on the proportion of a billing period that has already been used at the time of the billing cycle. 

> **Note:**
>
> When changing a usage-based subscription, proration is only applicable to line items that represent fees paid up front. Usage-based add-ons never prorate, as they are charged at the end of the billing cycle.

* **Add a usage-based add-on:** You will not see the new add-on on the change invoice. You will see it show up on the next bill date. Since usage-based add-ons never show on the first invoice where they exist for the subscription, and Recurly always creates an invoice for a subscription change, you could get in a scenario where the change invoice nets to 0 because the rest of the subscription didn't change.
* **Remove a usage-based add-on:** You will see the add-on on the change invoice with any unbilled usage.
* **Change a usage-based add-on price or percentage:** You will see the add-on on the change invoice with any unbilled usage charged at the old price or percentage. From that moment on, new usage will be recorded at the new price or percentage. You will see the price and percentage change on the following bill date.
* **Change plans that both have usage-base add-ons:** If you are changing the subscription's plan and both the old and the new plan have usage-based add-ons, you will see the equivalent of removing the old usage-based add-on and adding the new usage-based add-on. This means the old plan's usage-based add-ons will show up on the invoice and bill for any unbilled usage. The new plan's usage-based add-ons will not show on the change invoice because no usage has been logged yet. The next bill date's invoice after the change invoice will start showing usage for the new plan's usage-based add-ons.

## Offer free trials for usage-based subscriptions

If you want to offer a free trial period for your usage-based subscription, there are a couple of things to note:

* The usage incurred during the free trial period will not be billed until the end of the billing cycle, which is typically after the trial period has ended. 
* The customer will not be charged for any usage that occurs during the trial period.

## Applying coupons to usage-based subscriptions

If you offer coupons or discounts, they can also be applied to usage-based subscriptions. However, there are a few things to note:

* Coupons are applied to usage-based add-ons in the same way as they are applied to other add-ons. 
* Usage correction line items are not eligible for discounts, as they represent a period in the past that may or may not have had an active discount. 
* Limited time duration coupons will not discount the usage-based add-on fees from the final period of the coupon redemption duration.

In addition, if you want to offer a specific number of free units as part of a coupon or promotion, you can do so by setting up a tiered pricing model. The first tier would be set to $0 per unit for the first X units, and the additional tiers would include charges for each additional unit.

## Manage notifications for usage-based subscriptions

You will receive notifications in certain scenarios:

* When you zero-out the usage for a current cycle, a new\_usage\_notification webhook will be sent to update your usage records.
* When you refund a usage-based add-on, a new\_usage\_notification webhook will be sent to let you know what usage record was created.
* If Recurly creates usage on your behalf in a refund, a new\_usage\_notification will be sent. 

These notifications help you stay updated on changes made to your usage records.

# Creating a usage-based plan

To create a usage-based plan, you can create a new plan, or edit an existing plan. Add-ons are separated into Add Ons and Usage-Based Add Ons.

* Add-ons are charged at the beginning of the billing cycle before the product or service has been provided. 
* Usage-based add-ons charge at the end of the billing cycle after the product or service has been provided. All usage is logged using the [Usage API](https://developers.recurly.com/api/v2021-02-25/index.html#operation/create_usage) 

<Image title="Image 2020-07-06 at 2.34.44 PM.png" alt={831} align="center" width="75% " border={true} src="https://files.readme.io/3799415-Image_2020-07-06_at_2.34.44_PM.png">
  New Plan Page - Add-On Choices
</Image>

You can create a plan with any mix of Usage Based Add-Ons, Item Add-Ons, and Add-Ons. Recurly always requires a plan fee, the "recurring charge", but you can always set that to 0 if you want a strictly usage plan.

<Table align={["left","left","left"]}>
  <thead>
    <tr>
      <th style={{ textAlign: "left" }}>
        Attribute
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
        Add-On Name
      </td>

      <td style={{ textAlign: "left" }}>
        Video Streaming
      </td>

      <td style={{ textAlign: "left" }}>
        The name of your add-on, seen on Checkout, the Hosted Payment Page and invoice line item
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Add-On Code
      </td>

      <td style={{ textAlign: "left" }}>
        video\_streaming
      </td>

      <td style={{ textAlign: "left" }}>
        The product code for your add-on, seen in exports and used in the API
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Accounting Code
      </td>

      <td style={{ textAlign: "left" }}>
        VS1000239
      </td>

      <td style={{ textAlign: "left" }}>
        Optional accounting code to help your finance team account for the revenue in the right ledger
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Tax Type / Tax Code
      </td>

      <td style={{ textAlign: "left" }}>
        "Digital Product" or "D0000000"
      </td>

      <td style={{ textAlign: "left" }}>
        Those collecting EU VAT or using the AvaTax integration can define their usage product for appropriate taxation
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Charge Model
      </td>

      <td style={{ textAlign: "left" }}>
        "Price per Unit" or "Percentage of an Amount"
      </td>

      <td style={{ textAlign: "left" }}>
        Whether you want to define a price or percentage. Once you set a model, you cannot change it on the Edit Plan page. You will need to remove the add-on and add a new one.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Measured Unit
      </td>

      <td style={{ textAlign: "left" }}>
        Bandwidth (GB)
      </td>

      <td style={{ textAlign: "left" }}>
        The unit of measure. Provides a display for Checkout or Hosted Payment Page pricing and allows you to track the same unit type across multiple add-ons and plans.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Pricing Model (Tier Type)
      </td>

      <td style={{ textAlign: "left" }}>
        Fixed, Tiered, Volume, Stairstep
      </td>

      <td style={{ textAlign: "left" }}>
        The pricing model to use for charges. For more info, [click here](https://docs.recurly.com/docs/billing-models#section-quantity-based).  

        Referred to as Tier Type in developer docs and cannot be  used when Charge Model is Percentage.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Price
      </td>

      <td style={{ textAlign: "left" }}>
        $0.50 USD, €0.45 EUR
      </td>

      <td style={{ textAlign: "left" }}>
        The price per unit charged. This can be up to 9 decimal places.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Tiers
      </td>

      <td style={{ textAlign: "left" }}>
        An array of tiers and prices to be used in combination with the Tier Type
      </td>

      <td style={{ textAlign: "left" }}>
        The tiers and currencies that are used to charge for the usage logged.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Percentage
      </td>

      <td style={{ textAlign: "left" }}>
        2.36%
      </td>

      <td style={{ textAlign: "left" }}>
        The percentage taken of the monetary amount of usage tracked. This can be up to 4 decimal places. Percentage tiers and volume are supported.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Make this add-on optional to the customer
      </td>

      <td style={{ textAlign: "left" }}>
        Boolean checkbox
      </td>

      <td style={{ textAlign: "left" }}>
        Whether the add-on is optional to the customer on Checkout or the Hosted Payment Page. Usage-based add-ons default to required.
      </td>
    </tr>
  </tbody>
</Table>

# Usage-based add-on calculation methods

Recurly App allows you to charge customers for usage-based add-ons using one of two calculation methods. The "Cumulative" calculation method takes each individual amount of usage recorded throughout the duration of a given billing period and multiplies the aggregated total usage by unit price to calculate the subtotal charge. The "Last recorded" calculation method applies only the most recently recorded amount of usage in a given billing period and multiplies that individual usage amount by unit price to compute the subtotal charge.

<Image align="center" className="border" border={true} src="https://files.readme.io/6c02444-Screen_Shot_2022-11-09_at_9.28.44_AM.png" />

1. Navigate to the Usage-Based Add-On you just created.
2. Select one of two calculation methods: "Cumulative" or "Last Recorded". 

* "**Cumulative**" method takes each individual amount of usage recorded throughout the duration of a given billing period and multiplies the aggregated total usage by unit price to calculate the subtotal charge. 
  * Log 1 GB per day for 30 days and charge for 30 GB of usage
* "**Last Recorded**" method applies only the most recently recorded amount of usage in a given billing period and multiplies that individual usage amount by unit price to compute the subtotal charge.
  * Log 3 GB per day for 29 days and 2 GB on the 30th day, charge for 2 GB of usage at billing period close.
  * Log 5 GB per day for 15 days and 7 GB per day for the next 5 days with no additional usage logged for rest of billing period, charge for 7 GB of usage at billing period close.

> **Notes:**
>
> * You can change the calculation type of a usage-based add-on at any time, but the newly assigned calculation type will only apply to subscriptions created after the change.
> * To change the usage calculation method for a usage-based add-on that already exists on an account, you must remove the associated subscription from the account, make the modifications to the plan add-on, and then re-assign the modified plan to the account to create a new subscription that reflects the changes.

## Usage accumulation and billing

Usage can be accumulated and billed at each billing cycle, or over the entire subscription term.

<Image align="center" className="border" border={true} src="https://files.readme.io/0c47dea-Screen_Shot_2023-04-10_at_8.58.37_PM.png" />

## Managing measured units

Measured units provide a description of the usage measured for a usage-based add-on and allow you to track and report on the same type of usage across multiple add-ons and plans.

* You can create a measured unit when creating a usage-based add-on in a plan, or you can visit the "Measured Units" page under the Configuration section of your Admin Console. Measured Units can also be managed from the API. 
* Any edit to the measured unit will update your plan and any subscriptions immediately.
* You can only delete a measured unit if it is not being used in a plan. Remove the measured unit from all plans before you delete it on the Measured Units page.
* Measured units must be specified for all usage add ons. Measured units will only display to subscribers for price per unit usage add ons. Percentage usage add ons will always charge based on the monetary amount of usage logged. 

<Image title="mu-creation-in-plan.png" alt="1384" align="center" width="75% " border={true} src="https://files.readme.io/7SUwP0NQNiDQ8K4fQ2bB_mu-creation-in-plan.png">
  Create a Measured Unit when Creating an Add-on
</Image>

<Image title="mu-page.png" alt="1908" align="center" width="75% " border={true} src="https://files.readme.io/AHQbvJl2RfWr5SLPzhxV_mu-page.png">
  Create, View, Edit and Delete Measured Units from the Measured Units Page
</Image>

## Create a usage-based subscription

### Methods

You can subscribe customers to your usage-based plans through the API, Checkout, Hosted Payment Pages, or Admin Console. All API and Recurly.js details are mentioned in <a href="#API-Integrations">API Integrations</a> lower on this page. Here are details specific to usage-based plans for the Hosted Pages and Admin Console. 

#### Checkout and Hosted payment pages

* Usage-based add-ons will automatically show up on your Checkout or Hosted Payment Page for the plan, but their cost will not be included in the Order Total because all usage fees are charged at the end of the billing cycle.
* The price and measured unit display name are displayed for fixed price usage-based add-on to the right of the add-on name in parenthesis. Tiered, Volume, and Stairstep usage based add-ons will not have the prices displayed on checkout or hosted payment pages given pricing can vary based on the usage logged.
* Add-ons selected as optional on the plan will have checkboxes on Checkout and the Hosted Payment Page. Required add-ons will not have checkboxes and will show up above the optional add-ons.

<Image title="Image 2020-07-08 at 11.52.49 AM.png" alt={560} align="center" width="50% " border={true} src="https://files.readme.io/d29709f-Image_2020-07-08_at_11.52.49_AM.png">
  Example Hosted Payment Page for a Usage-Based Plan
</Image>

#### Administrator console

* Select your usage-based plan on the New Subscription page and you will see the associated usage-based add-ons appear.
* Required add-ons will be included, checked, by default, but you can always uncheck them.
* You can enter in a custom price or percentage any of the add-ons.
* For Quantity-Based add-ons, both tiers and prices can be custom for the subscription by clicking Edit Tiers. The pricing model cannot be changed. Create a new add on on the plan if you want to use a different pricing model. 

<Image title="Image 2020-07-08 at 12.18.35 PM.png" alt={1059} align="center" width="50% " border={true} src="https://files.readme.io/6ec95e6-Image_2020-07-08_at_12.18.35_PM.png">
  New Subscription with Usage-Based Add-Ons and Add-ons
</Image>

### First invoice

When a subscription starts, there are three possible first invoice experiences depending on the state of the subscription.

#### Active subscription

If your plan does not include a trial and the subscription starts immediately, the customer will see an invoice that does not include their usage-based add-ons. 

* Because we bill usage in arrears, it would be inaccurate to show the usage-based add-ons on the invoice with dates in the past, before the subscription or usage-based add-on existed.
* Usage-based add-ons will be included on all other invoices moving forward, even if usage is 0.
* The New Subscription email template will mention usage-based pricing in the plan information section so that customers can be assured they did purchase usage-based add-ons, they just aren't billed for them initially. You can reset the New Subscription email template to get this update, or review our add-on email parameters to create your own display.
* Additionally, our Hosted Account Management and API can be used to show customers their current plan, included add-ons, and current unbilled usage.

<Image title="normal-first-invoice.png" alt="1244" align="center" width="50% " border={true} src="https://files.readme.io/gbic9xnES6G4I1DMlNND_normal-first-invoice.png">
  Example First Invoice without Usage-Based Add-ons
</Image>

#### Trial subscription

Subscriptions that do start with a trial period always create a trial invoice at sign-up. Usage-based add-ons are included on trial invoices to market to your potential customer that they are trialing a usage-based product.

* Usage-based add-on line items will show the trial period dates, which are forward looking.
* Usage can be logged while in trial and displayed to your customer, but that usage will not be included on their first payment invoice at the end of the trial, and your customer will not be charged for usage incurred during their trial period.
* The first payment invoice after the trial will match the first invoice of the active subscription mentioned above.

<Image title="trial-invoice.png" alt="1236" align="center" width="50% " border={true} src="https://files.readme.io/3LZb3lqTF2YGpISQi3Yd_trial-invoice.png">
  Example Trial Invoice with Usage-Based Add-ons
</Image>

#### Future subscription

If you are starting a subscription for a date in the future, you won't have an invoice until the subscription starts. In most cases the first invoice will match the active subscription example above and will not show usage-based add-ons.

If you need to transition a customer's billing from a different system into Recurly, and you want to include usage on the first invoice because it is not a first invoice to the customer, you can do so by creating a future subscription and logging usage between the creation date and the future start date.

* Usage logged between subscription creation and start will appear on the invoice like a normal invoice for a new billing period.
* The line item dates will reflect the creation to start, so if you want to align the dates with your other system, we suggest a lazy migration where at the next bill date in the other system, you create the future subscription in Recurly with a future start date of the next bill date. Then start logging usage to Recurly and stop logging usage to the other system. Set the subscription in the other system to expire at its bill date and not send a final bill.
* We do not allow you to log usage for a date before the usage-based add-on existed on the subscription.
* Future usage subscriptions should not include trials given the differences in how future and trial usage is billed.

# Manage usage for subscriptions

## Understanding how to log usage

All usage is logged through our Usage API. Usage cannot be logged using the Admin Console.

* For percentage of an amount usage-based add-ons, usage will be logged "in cents", which we will convert to a proper currency display depending on the currency of the subscription. For example, if send "500" for a subscription in USD, we will format that as $5.00 USD.
* Usage amounts can be positive or negative. See our section on <a href="#section-usage-corrections">Usage Corrections</a> below.
* Each usage record has an optional custom field called "merchant\_tag" where you can store the usage event's ID in your own system, or whatever you like. Storing your own ID will allow you to use our API to provide auditable statements to your customers through your own UI.

## Logging and displaying usage amounts in decimal quantities

* Usage amounts can be logged in whole integers or decimal quantities. To enable logging usage amounts in decimal numbers, you will need to have Recurly Support  enable this feature on your Recurly instance. Support for decimal usage logging is available in [V2 and V3 API](https://docs.recurly.com/docs/usage-based-billing). 
* Please note, support for decimal quantities is only available for usage-based add-ons. Charges made outside of usage-based billing will need to reflect whole-number quantities. 
* Usage quantities logged in decimals will be supported up to 9 digits before the decimal point, and 9 digits after the decimal point, so long as the overall number does not round up to 1 billion. 
* Usage quantities logged in whole numbers leveraging the standard quantity field in the API will support up to 9 digits in total (ex: 999,999,999). 
* Simultaneously logging usage in whole numbers in one add-on, while logging in decimal numbers in a separate add-on is not supported. If the feature flag for decimal usage logging is enabled, all usage-based add ons will be measured and displayed in decimal form.
* The subtotal price on the invoice for each line item representing a usage-based add-on will reflect the total quantity logged throughout the duration of a billing period, multiplied by the add-on price-per-unit. (E.g. 10.57874 GB of usage in a billing period, at $10.00/GB, will result in a line item charge of $105.79). 
* Tax will be added separately as usual when tax-inclusive-pricing is enabled. 
* Charge-amounts do not support decimal places past the standard hundredth-place. For example, a quantity charge logged $10.505 will be rounded to $10.51 on the invoice. 
* If at any time a plan’s usage-based add-on pricing strategy is changed, or you decide to change tracking quantity in whole numbers instead of decimals, or vice versa, any forward-moving subscriptions with that impacted add-on will be processed to reflect the new modifications. 

## When to log usage?

We recommend setting up your integration to send Recurly usage in real-time, or aggregated into hourly or daily records based on what works best with your systems. The closer to real-time you get with logging your usage, the cleaner your invoices will look. We do not rate limit our Usage API endpoints in order to support real-time usage logging. 

The [Subscription Prerenewal webhook](https://developers.recurly.com/reference/webhooks/index.html#subscription-prerenewal) is sent 1 day in advance of a subscription renewal. This can be used as a trigger to log usage or update the usage that has been logged ahead of when the subscription renews and usage in invoiced. 

Each subscription bill date, immediate change, or expiration will generate an invoice and bill any unbilled usage. If you are logging usage later in the day for a past usage date in the billing cycle that was billed earlier that morning, the new usage will not be included in the bill date invoice. Instead we will pick up the unbilled usage on the next invoice. 

## Editing usage

You can edit usage records that haven't been billed yet. If the usage has been billed, consider issuing a refund, credit, or creating a Usage Correction. Note that once the usage is billed, you can only edit the "merchant\_tag" field. 

## Deleting usage

You're allowed to delete a usage record if it hasn't been billed yet. If the usage is billed, you can only issue a refund or create a Usage Correction.

## Correcting usage

Usage corrections are new usage records for a usage date in a past, already billed, billing cycle. They appear on the invoice grouped by billing cycle and will get picked up by the next subscription invoice. 

Depending on whether the net sum of a correction line item is positive or negative, it will be a charge or a credit. For logging usage programmatically at set times that are after some of your customer's subscription bill dates, you might see consistent usage corrections on those invoices. We recommend issuing refunds or adding a one time charge over corrections.

* Usage corrections appear on the invoice grouped by billing cycle. If you have multiple positive and negative corrections from the same past billing cycle, you will see the net sum on the invoice line item.
* If the net sum of a correction line item is positive, it will be a charge. If the result is negative, we will treat the line item as a credit.
* If you are programmatically logging usage at set times that are after some of your customer's subscription bill dates, you will consistently see usage corrections showing up on those invoices.
* Usage corrections will not pick up any coupon discounts on an invoice, they are not discountable. See DISCOUNTS ON USAGE-BASED ADD-ONS to learn more.
* Usage corrections are accepted when the pricing model is Fixed or Tiered. The usage will be charged based on the tiers that were already billed for that billing period. This enables you to charge your customer the correct price per tier for each billing period.
* Usage corrections will not be accepted if the Pricing Model is Volume or Stairstep. Use Line Item Refunds or create a new charge for corrections.
* Usage records cannot be updated for term-based billing add-ons.

#### Integration partners & support for decimal usage quantities

* **Xero**- Xero will receive the quantity data and round the quantity to the nearest 4th decimal place. Xero is the end destination, so the original quantity logged in Recurly will remain unaltered, reflecting the original amount of decimal places.
* **QuickBooks Online**- QuickBooks will receive the quantity data and round the quantity to the nearest 7th decimal place. QuickBooks is the end destination, so the quantity logged in Recurly will remain unaltered, reflecting the original amount of decimal places.
* **Salesforce**- Salesforce will receive the quantity decimal data and round to the 2nd decimal place for quantity. It can also be altered in Salesforce during order submission but only up to two decimal places.
* **NetSuite**- Netsuite will receive the quantity data and round the quantity to the nearest 8th decimal place. NetSuite is the end destination, so the original quantity logged in Recurly will remain unaltered, reflecting the original amount of decimal places.
* **Avalara**- Avalara will receive the quantity data and round the quantity to the nearest 9th decimal place, thus will support the same amount of decimal places logged via Recurly.
* **Vertex**- Vertex does not receive quantity data, only the price sent from Recurly, thus, no impact in existing experience will be present with the Vertex integration.
* **Kount**- Recurly sends line-item data to Kount, which includes the Quantity field, where Kount then evaluates this data and sends back a fraud assessment score. As long as the score is above a certain threshold, Recurly deems it does not qualify as fraud. The line item data we pass through is sent as an integer, which will not be impacted by quantities logged in decimals and will not impact the decimal number shown within Recurly. 

## Change a usage-based subscription

When you change a subscription with usage-based add-ons, we will always charge for any unbilled usage at the old state of the subscription. Note that usage-based add-ons never prorate. Only line items that represent fees paid up front will be prorated in an immediate change. Since usage-based add-ons charge at the end of the billing cycle, proration never applies.

* **Add a usage-based add-on:** You will not see the new add-on on the change invoice. You will see it show up on the next bill date. Since usage-based add-ons never show on the first invoice where they exist for the subscription, and Recurly always creates an invoice for a subscription change, you could get in a scenario where the change invoice nets to 0 because the rest of the subscription didn't change.
* **Remove a usage-based add-on:** You will see the add-on on the change invoice with any unbilled usage.
* **Change a usage-based add-on price or percentage:** You will see the add-on on the change invoice with any unbilled usage charged at the old price or percentage. From that moment on, new usage will be recorded at the new price or percentage. You will see the price and percentage change on the following bill date.
* **Change plans that both have usage-base add-ons:** If you are changing the subscription's plan and both the old and the new plan have usage-based add-ons, you will see the equivalent of removing the old usage-based add-on and adding the new usage-based add-on. This means the old plan's usage-based add-ons will show up on the invoice and bill for any unbilled usage. The new plan's usage-based add-ons will not show on the change invoice because no usage has been logged yet. The next bill date's invoice after the change invoice will start showing usage for the new plan's usage-based add-ons.

## Cancel or terminate a usage-based subscription

Subscriptions with usage-based add-ons that expire will always issue a final invoice with only the usage-based add-ons. Even if usage is 0, we will send a final invoice.

If there is positive usage for the current cycle, you have the option to zero-out the usage. This is useful if you have an upset customer and you don't want to collect on their final usage. If you choose to not charge for current usage, we will create a negative usage record that zeros out the resulting line item on the invoice. We will also send you a new\_usage\_notification webhook so you can update your own usage records.

* Note: If you have <a href="#section-usage-corrections">Usage Corrections</a> at the time of terminating, we will not zero those out for you and they will be charged on the invoice.

When refunding in a terminate action, we filter out usage-based fees from the previous invoice in the refund total, as those reflect the previous billing cycle, not money paid for the current billing cycle where products or services may not have been received.

## Refund a usage-based invoice

To refund a usage-based add-on, go through our normal refund flows, but we recommend using our Line Item Refunds instead of our Open (Specific) Amount Refunds.

* When doing a line item refund, we will create a negative usage record for the usage-based add-on for the usage amount you are refunding. This usage record will get marked as billed immediately in the refund and we will issue a new\_usage\_notification webhook to let you know what usage record was created in case you want to update your own records. The new usage record will have a usage\_timestamp of the last second of the refunded line items date range.
* Fixed price per unit usage-based add-ons allow you to refund all or a specific quantity (usage) amount.
* Quantity-Based usage-based add-ons can only be refunded using Line Item Refunds. Open amount refunds are not allowed. 
* Refund performance work with decimal-based quantities the same as they do for whole-integer quantities. Both full and partial refunds are supported with decimal quantities. 
* Percentage of an amount usage-based add-ons can only be fully refunded. If you want to do a partial refund, we recommend using our <a href="#section-usage-corrections">Usage Corrections</a>, or doing an Open Amount Refund and accounting for the usage record change on your own.
* If Recurly creates usage on your behalf in a refund , you will receive a new\_usage\_notification. 

## Discounts on usage-based add-ons

Discounts are applied to usage-based add-ons the same way as add-ons, except any <a href="#section-usage-corrections">usage correction</a> line items will not be discountable.

#### Example

*Given*

* "All Plans" coupon redemption for 10% off currently active on the account
* Customer is currently subscribed to a plan that is $5.00/month and $0.02/email/month
* Merchant logged a usage correction to charge the customer for 3 emails that were incorrectly left out of last month's invoice
* Customer used 15 emails this month

*The next invoice would show*

* Charge for $5.00 with a 10% discount
* Charge for 15 emails at $0.02/email with a 10% discount
* Charge for 3 emails at $0.02/email (no discount)

We do not discount usage correction line items because they represent a period in the past that may or may not have had an active discount at that time, so we do not want to assume they receive the current period's discount. We always recommend refunding a usage line item if you need to credit usage before you consider logging a usage correction through the API. Refunds will properly include any discounts included at the time the usage billing cycle was invoiced. Unfortunately, if you need to charge a usage correction from a past billing cycle, this can only be done through the API and will not pick up any discounts on invoice that bills the correction.

#### Limited time duration

Since usage-based add-ons are billed in arrears, it is important to understand that limited time duration coupons will not discount the usage-based add-on fees from the final period of the coupon redemption duration.

#### One Month Coupon

*Given*

* Coupon has a duration of 1 month and is for 10% off of all plans
* Plan is $5.00/month and $0.02/email/month
* Customer subscribes and redeems the coupon at the time of sign-up

*The invoice discounts will follow as*

* First invoice will discount the plan fee only, since usage add-ons are not billed on the first invoice
* The coupon redemption will expire right before the first bill date.
* The invoice will not discount the plan fee or usage add-on, since the coupon redemption has expired

#### Two Month Coupon

*Given*

* Coupon has a duration of 2 months and is for 10% off of all plans
* Plan is $5.00/month and $0.02/email/month
* Customer subscribes and redeems the coupon at the time of sign-up

*The invoice discounts will follow as*

* First invoice will discount the plan fee only, since usage add-ons are not billed on the first invoice
* The second invoice, which is the first bill date, will discount the plan fee and the usage add-on fee
* The coupon redemption will expire right before the third invoice, which is the second bill date
* The third invoice will not discount the plan fee or usage add-on, since the coupon redemption has expired

#### Coupons for free units

If you want to have an included quantity where the first X units are free, use a Tiered pricing model and set the first tier to a $0 per unit. Then create another tier with the charge for each additional unit. If you still want to use coupons, coupons can be a fixed amount or percentage off of the usage add-on subtotal.

## API integrations

#### Usage API and Client Libraries

In our API, all functionality for the Usage feature and Quantity-based pricing is on **[version 2019-10-10][10]** and above. Here is a link to the docs and a link to our Developer Guide. 

* Ruby Client version is [3.10.0](https://github.com/recurly/recurly-client-ruby/releases/tag/3.10.0)
* Node Client version is [3.11.0](https://github.com/recurly/recurly-client-node/releases/tag/3.11.0)
* Python Client version is [3.9.0](https://github.com/recurly/recurly-client-python/releases/tag/3.9.0)
* Dotnet Client version is [3.11.0](https://github.com/recurly/recurly-client-dotnet/releases/tag/3.11.0)
* Go Client version is [3.5.0](https://github.com/recurly/recurly-client-go/releases/tag/v3.5.0)
* Java Client version is [3.10.0](https://github.com/recurly/recurly-client-java/releases/tag/3.10.0)
* PHP Client version is [3.5.0](https://github.com/recurly/recurly-client-php/releases/tag/3.5.0)

For sites using our older v2 API, functionality for creating Usage Add Ons is on version 2.2 and Quantity Based Pricing is **[version 2.26][11]** and above. 

* Ruby Client version is [2.18.8](https://github.com/recurly/recurly-client-ruby/releases/tag/2.18.8)
* Python Client version is [2.9.16](https://github.com/recurly/recurly-client-python/releases/tag/2.9.16)
* PHP Client version is [2.12.13](https://github.com/recurly/recurly-client-php/releases/tag/2.12.13)
* Dotnet Client version is [1.17.3](https://github.com/recurly/recurly-client-dotnet/releases/tag/1.17.3)

However, we recommend always updating to the latest version of the API so that you have the most up-to-date functionality.

[10]: https://developers.recurly.com/api/v2019-10-10/index.html

[11]: https://dev.recurly.com/v2.24

[111]: https://dev.recurly.com/v2.25

[1111]: https://dev.recurly.com/v2.27

[12]: https://github.com/recurly/recurly-client-ruby/releases/tag/3.890

[13]: https://github.com/recurly/recurly-client-node/releases/tag/3.10.0

[14]: https://github.com/recurly/recurly-client-python/releases/tag/3.8.0

[15]: https://github.com/recurly/recurly-client-dotnet/releases/tag/3.10.0

[151]: https://github.com/recurly/recurly-client-go/releases/tag/v3.4.0

[16]: https://github.com/recurly/recurly-client-java/releases/tag/3.9.0

[161]: https://github.com/recurly/recurly-client-php/releases/tag/3.4.0

[17]: https://github.com/recurly/recurly-client-ruby/pull/237

[18]: https://github.com/recurly/recurly-client-python/pull/161

[19]: https://github.com/recurly/recurly-client-php/pull/227

#### Usage-based add-ons in plans

You can use the Plan Add-On API resource to create usage-based add-ons. Read our API documentation on <a href="https://developers.recurly.com/api/v2019-10-10/index.html#operation/create_plan_add_on" target="_blank">Plan Add-Ons</a>.

#### Usage-based add-ons in subscriptions

You can use the Subscription Add-On API resource to create usage-based add-ons in a subscription. Read our API documentation on <a href="https://developers.recurly.com/api/v2019-10-10/index.html#operation/create_subscription" target="_blank">Subscription Add-Ons</a>.

* Set custom prices for your subscription add-ons by using the normal `amount` attribute for "price per unit" add-ons and the new `usage_percentage` attribute for "percentage of an amount" add-ons.
* Usage-based add-ons can only have a `quantity` of 1. The custom purchases 1 quantity of the product, but is billed by measuring the units of usage, which can vary.

#### Recurly.js

Recurly.js version 4.0.5 pricing supports usage-based billing. Use Recurly.js to display the add-on price or percentage. Since usage-based fees are not billed up front and cannot be estimated for a next bill date, these add-on prices will not be included in the "\_now" or "\_next" pricing amounts.

#### Webhooks

Our [webhooks](https://developers.recurly.com/pages/webhooks.html#subscription-notifications) will include additional attributes about usage-based add-ons. This may break your integration, so be sure to update it accordingly. The webhooks include:

* new\_subscription\_notification
* renewed\_subscription\_notification
* updated\_subscription\_notification
* canceled\_subscription\_notification
* reactivated\_account
* expired\_subscription\_notification

## Reports and exports

#### Reports

* Your transactions report will reflect your usage-based add-on revenue, just like any other plan or add-on.
* Your MRR report will not include usage-based add-on revenue as variable fees are traditionally not included in MRR.
* There are not additional reports specific to usage-based add-ons at this time.

#### Exports

For easy analysis, you can pull information about usage add-ons and usage records from our Exports. 

Subscriptions Add Ons Export is version [2](https://docs.recurly.com/docs/subscription-add-ons-export)\
Subscriptions Usage Export is version [2](https://docs.recurly.com/docs/usages-records-export)

You will see an export called "Subscriptions Usage Records" that will export the individual usage records logged for your customer's usage-based subscription add-ons. This export is useful for your finance team trying to report on revenue earned before it is billed, as well as your product and marketing teams who may want to analyze customer usage.

For revenue recognition, be aware that the pricing information in this export is the customer's price and does not reflect any discounts factored in at the invoice level. Please review the Invoices - Line Items export for any discounts.

#### Quantity-based pricing and exports

The exports will include the tier\_type but will not include detailed tiers pricing information. Merchants can use the invoice line items for aggregate totals of the logged usage.  If you need access to specific tiers for a plan,  subscription, or usage record we recommend using the API responses. 

## Email template updates

These email templates have full support for usage-based add-ons:

* New Subscription
* New Invoice
* Invoice Past Due
* Subscription Change
* Subscription Canceled
* Payment Confirmation
* Payment Declined

The invoices in the body has it's own quantity (Qty) column, the subscription pricing displays to reflect additional usage-based add-on fees. If you have customized these templates, you can reset them to see the changes, or update your customized version to include our new add-on email parameters. For quantity-based pricing models, we do not recommend displaying an add\_on\_price, we recommend displaying the total price for the line item on the New Invoice. 

```text New Email Parameters
{#subscription_add_ons}}
  {{#add_on_usage_based?}}
    add_on_name: {{{add_on_name}}}<br />
    add_on_price: {{{add_on_price}}}<br />
    add_on_measured_unit_display_name: {{{add_on_measured_unit_display_name}}}<br />
 {{/add_on_usage_based?}}
{{/subscription_add_ons}}
```

<Image align="left" className="border" width="25% " border={true} src="https://files.readme.io/bc5468a-image.png" />

Usage-based billing was developed with support from Louisiana Economic Development’s Office of Entertainment Industry Development.
