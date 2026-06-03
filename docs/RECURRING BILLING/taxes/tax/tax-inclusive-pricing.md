---
title: Tax inclusive pricing
excerpt: >-
  Seamlessly integrate tax-inclusive pricing into your Recurly subscriptions,
  ensuring transparent and accurate billing for your customers.
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

- Subscription to Recurly's out-of-box tax solution or direct integration with Avatax and Vertex

### Limitations

- **Once enabled, the Tax Inclusive Pricing feature cannot be disabled on your Recurly site.**
- Inclusivity status of a subscription cannot be altered post-creation.

# Definition

Recurly's "Tax Inclusive Pricing" feature allows merchants to set prices that already include any applicable taxes. This ensures that customers see a consistent, all-inclusive price, whether taxes are itemized separately or included in the listed price.

# Key benefits

- **Transparent pricing**: Offer clarity to customers by displaying prices inclusive of taxes.
- **Flexibility**: Set tax inclusivity at subscription creation, catering to diverse customer preferences.
- **Efficient tax handling**: Seamlessly integrate with Recurly's tax solutions or other direct integrations like Avatax and Vertex.

# Introduction to tax inclusive pricing

Recurly introduces the "Tax Inclusive Pricing" feature, enabling merchants to display prices that already account for any applicable taxes. Whether you're setting up subscriptions, items, fees, or add-ons, you can choose to display prices as tax-inclusive or exclusive.


<Image src="https://files.readme.io/7f758cf-Screen_Shot_2022-04-22_at_12.12.14_PM.png" align="center" border={true} />


## How it works

When creating a subscription plan, you can configure it as usual. At the point of subscription creation, you can select the tax status. For instance, if you have a plan priced at $10.00 and you subscribe two different customers with different tax inclusivity preferences, their final prices might differ based on the tax rate applied.


<Image src="https://files.readme.io/6195d9b-Screen_Shot_2022-04-22_at_12.23.30_PM.png" align="center" border={true} />



<Image src="https://files.readme.io/8de7238-Screen_Shot_2022-04-22_at_12.23.19_PM.png" align="center" border={true} />


Items created outside of the plan page will inherit the tax inclusivity status of the associated subscription. For one-time purchases, you can add a charge to an account and select the tax inclusivity preference.

## Discounts and tax inclusivity

Discounts can be applied to purchases with tax inclusivity. Here's how they work:

**Percentage Discount**

Original Price (Tax Inclusive): $300.00<br />Tax Rate: 10.250%
Discount: 20%
Final Price: $240.00
Breakdown: $217.69 (subtotal) + $22.32 (tax)

**Fixed Amount Discount**

Original Price (Tax Inclusive): $300.00<br />Tax Rate: 10.250%
Discount: $60.00
Final Price: $240.00
Breakdown: $217.69 (subtotal) + $22.32 (tax)

## Invoicing

If your site has Tax Inclusive Pricing feature enabled, you have the ability to hide or show taxes on your invoices.  This setting can be found when creating or editing an invoice template, and is disabled by default.


<Image src="https://files.readme.io/6f2a0458032a3cc9c32c9a790d8135969cbb31651fd13cb303922f7c53b90fce-Screenshot_2026-06-03_at_5.33.26_PM.png" border={true} />


<br />

## Integration with Recurly.js

For accurate tax estimates on Recurly.js, follow these steps:

1. Generate a token in Recurly.js without specifying a tax inclusive flag.
2. Use API V2/V3 to establish a purchase or subscription, referencing the token from the previous step in `billing_info.token_id` and the `tax_inclusive` flag.
3. Utilize the preview route to display estimated taxes to your subscriber before finalizing the purchase.

## Setting up tax inclusive pricing

1. Navigate to your Recurly dashboard.
2. Access the pricing settings for subscriptions, items, fees, or add-ons.
3. Configure the desired price and select the "Tax Inclusive" option.

## Applying discounts to tax inclusive prices

1. Choose the subscription or item you wish to apply a discount to.
2. Select the type of discount (percentage or fixed amount).
3. Apply the discount, and the system will automatically adjust the price, keeping tax inclusivity in mind.

<br />
