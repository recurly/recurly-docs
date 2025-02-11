---
title: Prepaid account balance
excerpt: >-
  Discover the power of the Prepaid Account Balance, a feature that
  revolutionizes cash flow management by allowing your subscribers to prepay for
  their future purchases and avail discounts.
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

<Embed url="https://www.youtube.com/watch?v=nVnGfZmoTRE" title="Prepayments: Demo" favicon="https://www.google.com/favicon.ico" image="https://i.ytimg.com/vi/nVnGfZmoTRE/hqdefault.jpg" provider="youtube.com" href="https://www.youtube.com/watch?v=nVnGfZmoTRE" typeOfEmbed="default" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Fsrc%3Dhttps%253A%252F%252Fwww.youtube.com%252Fembed%252FnVnGfZmoTRE%253Ffeature%253Doembed%26display_name%3DYouTube%26url%3Dhttps%253A%252F%252Fwww.youtube.com%252Fwatch%253Fv%253DnVnGfZmoTRE%26image%3Dhttps%253A%252F%252Fi.ytimg.com%252Fvi%252FnVnGfZmoTRE%252Fhqdefault.jpg%26key%3D7788cb384c9f4d5dbbdbeffd9fe4b92f%26type%3Dtext%252Fhtml%26schema%3Dyoutube%22%20width%3D%22854%22%20height%3D%22480%22%20scrolling%3D%22no%22%20title%3D%22YouTube%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%3B%20encrypted-media%3B%20picture-in-picture%3B%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" />

### Required plan

This feature is available to all customers on any Recurly subscription plan.

### Prerequisites

Features **'Credit Invoices'** and **'Only Bill What Changed'** must be enabled to use the prepaid account balance.

# Definition

Prepaid Account Balance is a feature that enables customers to pay in advance, contributing to an account balance that can be used to settle future subscription and one-time purchase invoices.

# Key benefits

* **Immediate cash flow:** Benefit from immediate cash flow generated through prepayments, enhancing your financial stability.
* **Boosted customer acquisition:** Enhance customer acquisition and conversion rates by offering discounts for prepaid amounts, making your offerings more attractive.
* **Reduced transaction costs:** Achieve a significant reduction in transaction costs as there are no transaction fees or interchange charges when subscribers pay for purchases from their account balance, promoting cost-efficiency.

# Key details

## Setting up a prepaid account balance

This feature can be established using API V2, API V3, or through the Admin Console.

* For the V3 API, generate a <a href="https://developers.recurly.com/api/v2019-10-10/index.html#operation/create_purchase" target="_blank">Purchase</a> request for a line\_item with an "origin" = "prepayment".
* For the V2 API, formulate a <a href="https://dev.recurly.com/docs/create-purchase" target="_blank">Purchase</a> for a charge adjustment with an "origin" = "prepayment".
* In the Recurly Admin Console, you can create a charge with an immediate time frame. Choose Prepaid Account Balance, specify an amount, and preview the charge before creation.

<Image align="center" className="border" width="50% " border={true} src="https://files.readme.io/0de698f-2021-03-04_1351.png" />

When the purchase request is successfully processed, the transaction amount is added to the Account Balance. Future subscriptions and one-time purchases will be deducted from this balance until it's depleted. If the purchase transaction fails, the invoice will be marked as failed and will undergo a dunning process for collection.

<Image title="Image 2020-09-15 at 3.33.44 PM.png" alt={1970} align="center" width="50% " border={true} src="https://files.readme.io/267de5a-Image_2020-09-15_at_3.33.44_PM.png">
  The Hosted Account Management page will display the account balance, active subscriptions and all associated invoices to provide clarity for subscribers.
</Image>

## Considerations for prepaid account balances

* Prepaid balances should be tax-exempt. Taxes will be applied on an invoice when necessary when the actual product/service is sold.
* Do not mix purchase requests to add to the prepaid account balance with other line items.
* Purchase requests for the prepaid account balance must be invoiced immediately, not at renewal.
* Prepaid account balances cannot fund additional account balances. Subsequent prepaid account balance purchases will not use these balances.
* Revenue Recognition for account balance must be managed by the merchant.
* Refer to [Adjustments](https://docs.recurly.com/docs/adjustments#section-invoice-custom-credits) to understand how credits and account balance are applied on invoices.

## Manual invoices and prepaid account balance

For manual collection methods, the account balance remains in a processing state until the manual payment is collected.

## Asynchronous payment methods and prepaid account balance

Prepayments made through the UI, ACH, and other direct debit payment methods will not fund the prepaid balance until Recurly receives a successful transaction notification.

## Refunds

Refunds are possible for prepaid account balances that haven't been utilized. The refund will be directed back to the original payment method.
