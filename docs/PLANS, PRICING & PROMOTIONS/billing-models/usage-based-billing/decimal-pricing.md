---
title: Decimal pricing
excerpt: >-
  This document details the concept of Decimal Pricing, its implementation in
  various business models, and the benefits it brings. It is a comprehensive
  guide designed to help businesses understand and utilize decimal pricing
  efficiently.
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

Decimal pricing is a pricing method that is ideal for businesses which require non-integer pricing models. For instance, a company providing video streaming services might charge $0.005 per GB of data consumed monthly, then calculate the total charge by multiplying the overall data usage with this unit price and rounding it to the closest cent.

# Key benefits

* **Precise & flexible pricing**: This model caters to diverse consumption patterns, ensuring every user finds a suitable pricing plan.
* **Efficient service charge calculation**: The clarity in service charge calculations ensures transparency and accuracy.
* **Diverse integration support**: The platform is compatible with various pricing models and services, enhancing its adaptability to business needs.

# A new standard for business: decimal pricing

Decimal pricing provides a strategic advantage for enterprises needing to formulate pricing values that aren't integers. It is perfect for situations where the cost per unit of consumption is a decimal figure. For instance, if a video streaming company charges $0.005 for every GB of data used monthly, the total bill is calculated by multiplying the usage with $0.005, and rounding off the result to the nearest cent.

## Decimal pricing application in plans and subscriptions

Decimal pricing can be employed via the creation of a usage add-on through the Admin Console, V3 API (<a href="https://developers.recurly.com/api/v2021-02-25/index.html" target="_blank">2021-02-25</a>), or V2 API (<a href="https://recurly.com/developers/api-v2/v2.29/#tag/subscription-usage-records" target="_blank">here</a>). When indicating pricing in the API, use unit\_amount\_decimal. Decimal pricing caters for up to 9 decimal places in fixed, tiered, volume, and stair step pricing models. When unit\_amount\_decimal is provided, the unit\_amount field is automatically set to null. The plan's predefined prices are used by default when creating a subscription, but you can alter these prices if needed.

## Invoices and decimal pricing

Invoice line item totals are rounded to the decimal values supported by the currency, and the unit\_amount\_decimal value is displayed on the invoices. For API responses, the decimal pricing is stored in the unit\_amount\_decimal field, while the unit\_amount field remains null.

## Refunding decimal pricing

Recurly limits refunds to the invoice amount, preventing over-refunding customers. The recommended method is to use line-item refunds for clarity on refunded products. In an open amount refund with decimal pricing, Recurly rounds the amount and refundable quantity to be equivalent to the remaining refundable amount. This might cause minor discrepancies in the refund price, but it will prevent over-refunding. 

## Emails

The unit\_amount\_decimal values are automatically filled into the unit\_amount parameter in emails. If you display invoice line items in your emails, they will automatically work when you start using decimal pricing.  

## Exports

Subscription Add-Ons, Subscription Add Ons History, and Subscription Add Ons Usage exports include a unit\_amount\_decimal column to be used when decimal pricing is applied.

## Webhooks

Subscription notifications will include a unit\_amount\_in\_decimal\_cents value when decimal pricing is used. The unit\_amount will be null when decimal pricing is used.

## Guide to activate decimal pricing

1. **Enable Required Features**: Merchants with sites created on or before May 7th, 2018 need to make sure they enable Credit Invoices and Only Bill What Changed to leverage decimal pricing. You can turn these on via the Invoice Settings page.
2. **Access the Admin Console**: Go to the Admin Console or use V3 API.
3. **Create Usage Add-on**: Create a usage add-on where you need to apply decimal pricing.
4. **Specify Pricing in API**: When setting the pricing in the API, use the 'unit\_amount\_decimal' parameter.
5. **Confirm Changes**: Check the plan's predefined prices and adjust them if necessary.
6. **Start Using Decimal Pricing**: After successful setup, you can start using decimal pricing in your plans and subscriptions.
7. **Track and Refine**: Monitor the performance and make necessary changes based on the feedback and analytics.

# Integration support

* The Xero integration supports up to 4 decimal places for the unit\_price. Some prices in Xero will round to two decimal places. The line item total charge will always be correct but the price is limited by the decimals Xero supports.
* The Quickbooks Online integration supports up to 7 decimal places. The line item total charge will always be correct but the price is limited by the decimals Quickbooks Online supports.
* Netsuite integration does not currently support decimal pricing. Reach out to [support@recurly.com](mailto:support@recurly.com) if this is a need for your business
