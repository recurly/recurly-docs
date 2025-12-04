---
title: Change subscription
excerpt: >-
  Manage your subscription flexibly with Recurly's "Change Subscription"
  feature. Upgrade, downgrade, or alter your subscription settings seamlessly,
  ensuring a tailored experience throughout your subscription journey.
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

* Admin access to manage subscription settings.
* A clear understanding of your subscription model and billing cycle.

### Limitations

* Changes during a free trial period won't generate an invoice.
* Coupon redemption is limited to immediate changes with product alterations.
* Subscription modifications enforcement based on payment status.

# Definition

"Change Subscription" is a feature offered by Recurly that allows subscribers and administrators to modify subscription plans, quantities, add-ons, and other settings. These changes can be scheduled to take effect immediately, at the next bill date, or at the term renewal, offering a great deal of flexibility. The feature also extends to managing discounts, coupons, and trials during the subscription lifecycle.

# Key benefits

* **Flexible management:** Easily upgrade, downgrade, or modify your subscription settings to suit evolving needs.
* **Real-time billing adjustments:** Immediate invoicing for any changes ensures accurate billing and a clear transaction history.
* **Enhanced customer experience:** Empower customers with the ability to manage their subscriptions, fostering satisfaction and loyalty.

# How to modify a subscription

Modifying a subscription can be done through the Admin Console or the API.

In the Admin Console, navigate to the Subscription Details page by accessing the customer's account and clicking on the subscription name. On the top right corner of the page, you'll find a "Subscription Actions" dropdown menu. Here, select "Edit Subscription". In the Edit Subscription page, make the necessary adjustments and click "Save Changes".

For a comprehensive understanding of the options available while modifying a subscription, kindly refer to the documentation provided below.

Subscription modifications in Recurly, such as downgrades and upgrades, encompass changes in plan, quantity, price, or the addition/removal of add-ons. They also include other updates like altering the collection method or invoice notes. If there's a need to alter the current billing cycle of a subscription, refer to our [Postpone Subscription](https://docs.recurly.com/docs/postpone-subscription) feature.

> Recurly now bills only the difference during an immediate subscription modification if the underlying plan remains unchanged. This feature is automatically available for all Recurly sites created on or after June 30, 2017 UTC. For sites created before this date, the option to activate this feature is located at the bottom of the Invoice Settings page under Configuration in your Admin Console.
>
> This guide elaborates on Recurly's subscription modification functionality with the assumption that the Bill Only for Changes feature is enabled.
>
> To enable the Bill Only for Changes feature, or to learn more about its release, you can [learn more here](https://docs.recurly.com/docs/only-bill-what-changed).

# What can be changed

Product modifications can be executed immediately, at the next billing date, or upon term renewal. However, changes related to invoices will take effect immediately, even if the at renewal option is selected.

## Can be changed immediately

* Plan
* Price Segment
* Price
* Quantity
* Plan/Add-on Price
* Plan/Add-on Quantity
* Bill Date with Proration
* Add or Remove Add-on
* Collection Method
* Net-Terms
* PO Number
* Customer Notes
* Terms and Conditions

## Can be changed at bill date and term renewal

* Plan
* Price
* Price Segment
* Plan/Add-on Price
* Plan/Add-on Quantity
* Add or Remove Add-on

# Handling Immediate Subscription Changes

When making an immediate subscription change, as opposed to making a change that takes place at the start of the next billing period or term, there are a few different options available for how to handle the resulting credits and/or charges.

Your customer may have requested to upgrade their plan, or you want to change the quantity and/or price of their current plan, or adjust pricing or quantity of associated add-ons, and you wish to provide them access to these immediate changes right away. In these cases, Recurly allows you to handle the resulting credit and/or charge that reflects the time left in the current billing period, in the way that is most effective for your business and your customer. Because there is no one-size-fits-all approach for how much or little to charge or credit a customer for an immediate subscription change in a line of business or across varying industry verticals, Recurly leaves the flexibility to control proration behavior up to you and your organizations’ needs.

## Charges and credits

Why do credits and/or charges result? Think about the reasons for making an immediate subscription change… You can upgrade a customer by moving them to a higher tier plan, downgrade a customer to immediately provide them with a less expensive service, you could add more add-ons to a subscription, update the quantity of their subscription so their friends or family can receive your goods immediately as well- the list goes on. Sometimes you’ll want to charge your customers for those changes, sometimes you’ll want to credit them, sometimes you’ll want to issue both a credit and a charge. Sometimes, you’ll want to skip the credits and charges resulting from your change entirely. Recurly allows you to choose what you want to do, when you want to do it.

Options for how to apply a **credit** to an immediate subscription change are:

* Prorated Credit
* Full Credit
* No Credit

Options for how to apply a **charge** to an immediate subscription change are:

* Prorated Charge
* Full Charge
* No Charge

## Choose how to handle charges and credits from immediate subscription changes

There are two ways to choose how to handle the credits and/or charges resulting from immediate subscription changes.

The first way is by setting your preferences on the Invoice Settings page within the Configuration section in Recurly. The options you choose for Credits and Charges on the Invoice Settings page will serve as the default behavior for how to handle all credits/charge resulting from all immediate subscription changes made on your site. You can update your settings at any time. All charges and credits resulting from  immediate subscription changes moving forward will assume the new settings. Previously executed charges and credits will remain unchanged. This site level setting is only supported in Recurly App’s user interface.

**Site-level setting**

<Image align="center" border={true} src="https://files.readme.io/c8e180b-Screenshot_2024-05-06_at_7.55.42_PM.png" className="border" />

The second way you can choose how to handle credits and/or charges resulting from immediate subscription changes is by setting your preferences during the immediate subscription change itself. You can set subscription-level overrides in the UI and both API V2 and V3. If you do not override the immediate subscription change charge and credit behavior when making the actual subscription change(s), then the credit/charge behavior used will reflect the settings from your site-level default settings on the Invoice Settings page.

**Subscription-level overrides**

<Image align="center" border={true} src="https://files.readme.io/6388d2b-Screenshot_2024-05-06_at_8.10.01_PM.png" className="border" />

### Rebills

During an immediate subscription change, if the plan has altered, credits will be generated for the old/current subscription version while charges will be generated for the new/updated subscription version. This process is referred to as “rebilling” the subscription. Rebills will also result if both the quantity and price of something on a subscription changes, and will also result if a merchant does not have “Only Bill What Changed” (OBWC) enabled on their site.

If the plan remains unchanged, Recurly will evaluate each product in the change, creating charges for the new items or price increases and credits for the removed items or price decreases. This is known as only billing what changed in the subscription, and is automatically supported on all Recurly sites created after June 30, 2017 UTC, by a feature called “Only Bill What Changed (OBWC).”

Merchants without OBWC on their site still have the same flexibility to handle credits and charges that result from an immediate subscription change. The differences in behavior will be called out where necessary in the scenarios and examples below.

Both a **credit and a charge** (a rebill) result when:

* Change in _both price and quantity_ on the subscription or an add-on
* Changing the _plan_ on the subscription regardless of upgrading or downgrading
* Any immediate subscription change is made when the _OBWC (only bill what changed) feature is not enabled on a site_

### Either charge or credit is created (no rebill)

**Only a credit** results when:

* Only Bill What Changed is enabled and
* Decrease in price on sub or add-on, no change in plan
* Decrease in quantity on sub or add-on, no change in plan

**Only a charge** results when:

* Only Bill What Changed is enabled and
* Increase in price of sub or add-on, no change in plan
* Increase in quantity of sub or add-on, no change in plan

## How each charge and credit option is calculated

As outlined above, you have three (3) options to choose from for handling both credits and charges that result from immediate subscription changes. Plans using ramp pricing will also follow these calculations and behaviors.

### If you choose a prorated credit/charge

Proration is a popular choice for handling credits and charge for immediate subscription changes amongst merchants who only wish to credit or charge a customer for how much value they were able to receive from the old/current state of their subscription before they made a change.
Proration is calculated as follows:

1. Determine the time remaining in the current billing period.
2. Divide this time by the total duration of the subscription's plan billing period.
3. Multiply the result by the per-unit price to calculate the prorated charge or credit.
   The formula is represented as:

<Image align="center" border={true} width="75% " src="https://files.readme.io/28bfa13-image.png" className="border" />

It's important to remember that the "plan billing period" in this formula refers to the set duration of the subscription plan, not the adjusted subscription's billing period. This is relevant when the billing date is changed. For example, if a subscription on an annual plan has its billing cycle end date adjusted, the denominator in the formula will still represent a full year, while the numerator will reflect the adjusted end date.

### If you choose a full credit/charge

**Credit**

Choosing full credit for a rebill scenario will always issue a full refund to the customer for the entire price of the old/current state of the subscription. For example, if you upgraded a customer from a $30/month plan to a $100/month plan, and chose “full credit,” the customer would receive a credit for $30 dollars.

Choosing full credit when no rebill is warranted, so in a scenario where you only make a change to either the price of the customer’s plan or an add-on, or the quantity of their subscription or add-on, will result in the customer being credited for the price difference of the change. For example, if you decrease the price of a customer’s plan from $50/month to $30/month, and choose “full credit,” the customer will receive a $20 credit.

**Charge**

Choosing full charge for a rebill scenario will always issue a full charge to the customer for the entire price of the new/updated state of the subscription. For example, if you upgraded a customer from a $30/month plan to a $100/month plan, and chose “full charge,” the customer would receive a charge for $100 dollars.

Choosing full charge when no rebill is warranted, so in a scenario where you only make a change to either the price of the customer’s plan or an add-on, or the quantity of their subscription or add-on, will result in the customer being charged for the price difference of the change. For example, if you increase the price of a customer’s plan from $30/month to $50/month, and choose “full charge,” the customer will receive a $20 charge.

<br />

### If you choose no credit/charge

Choosing no credit or charge for any scenario, rebill or otherwise, will result in no charge or credit being created as a result of an immediate subscription change.

One item to note is that when choosing to skip a “Credit,” no invoice will be sent to the customer as no invoice will be created for a zero dollar credit.

However, if you choose to skip a “Charge,” a zero dollar invoice will still be sent to the customer reflecting the change that was made.

> 👍 If you have chosen to not credit an immediate subscription change in the past, and you decide at a later point in time to provide a refund for that charge, you may do so.

## Types of subscription changes and practical examples

* [Plan change](#plan-change)
* [Quantity change](#quantity-change)
* [Price change](#price-change)
* [Change quantity and price](#change-quantity-and-price)
* [Add or remove add-on](#add-or-remove-add-on)
* [Change quantity-based add-on](#change-quantity-based-add-on)
* [Change usage-based add-on](#change-usage-based-add-on)
* [Terminate and refund subscription](https://docs.recurly.com/docs/change-subscription#terminate-and-refund-subscription)
* [Change plan period](#change-plan-period)

<br />

### Plan change

When there's a change in the subscription’s plan, Recurly will rebill the entire subscription. This occurs whether a merchant has the Only Bill What Changed (OBWC) feature enabled or not. A charge will result for the new version of the subscription, and a credit for the old version of the subscription.

In cases where add-ons with identical add-on codes are used across different plans, Recurly will rebill the add-on when the plan for the subscription changes. This occurs because Recurly cannot determine that the add-ons are identical. Even though they share the same add-on code, their underlying IDs differ.

#### Plan change examples

**Scenario:**
You downgrade your customer’s monthly subscription from a $100/month plan to a $60/month plan with 10 days left in their billing cycle. Because this requires a full rebill, both a credit and a charge will result. A rebill will occur as a result of a plan change regardless of if OBWC is enabled on your site or not.

* If you choose prorated credit:
  * By choosing “prorated credit,” you would credit your customer for the unused portion of the original plan that they will no longer receive value from for the remainder of the billing period. Your customer would receive a $33 credit to account for the decrease in price from moving to their new plan.
    * (10 days remaining/30 days in billing period)*100 as the per unit cost= $33
* If you choose full credit:
  * By choosing “full credit,” you would fully credit your customer $100 for the original state of the subscription.
* If you choose no credit:
  * By choosing “no credit,” you would not credit your customer anything for this subscription change and they would not receive a credit invoice
    > 👍 Tip:
    >
    > This is a **great** option for merchants who ship physical goods. This way, you can ensure your customer is not credited for the items they already received at the beginning of the billing period, since the full “value” of the plan’s offering is considered fulfilled by the merchant once the customer receives the shipment.

You will also need to handle the resulting charge to account for the new/updated state of the subscription.

* If you choose prorated charge:
  * By choosing “prorated charge,” you would charge your customer only for the portion of the new/updated plan that they will be able to receive value from for the remainder of the billing period. Your customer would receive a $19.80 charge to account for the prorated amount of 10 days remaining on a $60 plan.
    * (10 days remaining/30 days in billing period)*60 as the per unit cost= $19.80
* If you choose full charge:
  * By choosing “full charge,” you would fully charge your customer $60 for the new/updated state of the subscription.
* If you choose no charge:
  * By choosing “no charge,” you would not charge your customer anything for this subscription change and they would receive a zero dollar invoice showing them the new state of their subscription change, reflecting the new plan at a zero dollar cost to them.

### Quantity change

When there's a change in the quantity of a plan fee or add-on, a charge or credit will be generated for the difference in quantity.

* For quantity increases, the charge quantity will represent the additional quantity.
* For quantity decreases, the quantity will always be 1 and the price will reflect the total value of the removed quantity.

<br />

#### Quantity increase example

**Scenario:**
You increase your customer’s plan quantity priced at $30/month from a quantity of 1 to a quantity of 2 with 10 days left in their billing cycle. This will not result in a rebill if you have OBWC enabled on your site. If you do not have OBWC enabled, the change will follow standard rebill behavior (see plan change example above).

<br />

* If you choose prorated charge:
  * By choosing “prorated charge,” you would charge your customer only for the portion of the new quantity that they will be able to receive value from for the remainder of the billing period. Your customer would receive a $9.90 charge to account for the prorated amount of 10 days remaining on the additional $30 plan.
    * (10 days remaining/30 days in billing period)*30 as the per unit cost= $9.90
* If you choose full charge:
  * By choosing “full charge,” you would fully charge your customer $30 for the newly added quantity.
* If you choose no charge:
  * By choosing “no charge,” you would not charge your customer anything for this subscription change and they would receive a zero dollar invoice showing them the new state of their subscription change, reflecting the new plan quantity at a zero dollar cost to them.

#### Quantity decrease example

**Scenario:**
You decrease your customer’s add-on quantity priced at $15 per unit from a quantity of 2 to a quantity of 1 with 10 days left in their billing cycle. This will not result in a rebill if you have OBWC enabled on your site. If you do not have OBWC enabled, the change will follow standard rebill behavior (see plan change example above).

* If you choose prorated credit:
  * By choosing “prorated credit,” you would credit your customer only for the portion of the original add-on quantity count that they will no longer be able to receive value from for the remainder of the billing period. Your customer would receive a $9.90 credit to account for the prorated amount of 10 days remaining on one less $30 plan.
    * (10 days remaining/30 days in billing period)*15 as the per unit cost= $4.95
  * If you choose full credit:
    * By choosing “full credit,” you would fully credit your customer $15 for the decrease in quantity.
  * If you choose no credit:
    * By choosing “no credit,” you would not credit your customer anything for this subscription change and they would not receive a zero dollar invoice since Recurly does not issue zero dollar invoices for immediate subscription changes.

### Price change

When there's a change in the price of a plan fee or add-on, a charge or credit will be generated for the price difference.

* For price increases, the charge quantity will correspond to the current product's quantity in the subscription, and the price will be the difference between the previous price and the new price, then multiplied by the proration percentage.
* For price decreases, the quantity will always be 1, and the price will reflect the prorated price difference, multiplied by the current quantity of the product in the subscription.

#### Price increase example

**Scenario:**
You increase your customer’s monthly subscription from $80/month to $100/month because you are giving them immediate access to a new feature in your application that they could not previously utilize due to their monthly plan cost. They have 10 days left in their billing cycle.

* If you choose prorated charge:
  * By choosing “prorated charge,” you would charge your customer only for the remainder of the billing period where they would be able to access the new feature they received access to from the price increase. Your customer would receive a $33 dollar charge.
    * (10 days remaining/30 days in billing period)*100 as the per unit cost= $33
* If you choose full charge:
  * By choosing “full charge,” you would charge your customer the $20 price difference for the increase in plan price.
* If you choose no charge:
  * By choosing “no charge,” you would not charge your customer anything for this subscription change and they will receive a zero dollar invoice reflecting the new plan information resulting from the immediate change.

#### Price decrease example

**Scenario:**
You decrease the price of your customer’s subscription add-on from $20/month to $10/month because their add-on has become outdated and a newer more improved model of the add-on is available for $20/month. They have 10 days left in their billing cycle.

* If you choose prorated credit:
  * By choosing “prorated credit,” you would credit your customer only for the unused portion of the billing period for the $20 price. Your customer would receive a $6.60 dollar credit.
    * (10 days remaining/30 days in billing period)*20 as the per unit cost= $6.60
* If you choose full credit:
  * By choosing “full credit,” you would credit your customer the $10 price difference for the decrease in the add-on price.
* If you choose no credit:
  * By choosing “no credit,” you would not credit your customer anything for this subscription change and they would not receive a zero dollar invoice since Recurly does not issue zero dollar invoices for immediate subscription changes.

### Change quantity and price

When both quantity and price are changed at the same time for a plan fee or add-on, that product will be rebilled and have both a credit and a charge.

When there's a change in the subscription’s plan, Recurly will rebill the entire subscription. This occurs whether a merchant has the Only Bill What Changed (OBWC) feature enabled or not. A charge will result for the new version of the subscription, and a credit for the old version of the subscription.

#### Quantity and price change example

**Scenario:**
You increase the per-unit price of your customer’s subscription add-on from $15 to $20 because their add-on has become more updated and advanced, and you also increase their add-on quantity from 1 item to 3 items. They have 10 days left in their billing cycle. Because both quantity and price on the subscription are changing, this will result in a rebill, regardless of if Only Bill What Changed (OBWC) is enabled on your site or not.

* If you choose prorated credit:
  * By choosing “prorated credit,” you would credit your customer for the unused portion of the original add-on total that they will no longer receive value from for the remainder of the billing period. Your customer would receive a $4.95 credit to account for the decrease in price from moving to their new plan.
    * (10 days remaining/30 days in billing period)*15 as the per unit cost= $4.95
* If you choose full credit:
  * By choosing “full credit,” you would fully credit your customer $15 for the original cost of their 1 add-on
* If you choose no credit:
  * By choosing “no credit,” you would not credit your customer anything for this subscription change and they would not receive a credit invoice
    > 👍 Tip:
    >
    > This is a **great** option for merchants who ship physical goods. This way, you can ensure your customer is not credited for the items they already received at the beginning of the billing period, since the full “value” of the plan’s offering is considered fulfilled by the merchant once the customer receives the shipment.

You will also need to handle the resulting charge to the account for the new/updated state of the subscription.

* If you choose prorated charge:
  * By choosing “prorated charge,” you would charge your customer only for the portion of the new add-ons that they will be able to receive value from for the remainder of the billing period. Your customer would receive a $60 charge to account for the prorated amount of 10 days remaining on a $60 plan.
    * (10 days remaining/30 days in billing period)*60 as the total cost= $19.80
* If you choose full charge:
  * By choosing “full charge,” you would fully charge your customer $60 for the new/updated state of the subscription.
* If you choose no charge:
  * By choosing “no charge,” you would not charge your customer anything for this subscription change and they would receive a zero dollar invoice showing them the new state of their subscription change, reflecting the new plan at a zero dollar cost to them.

#### Change quantity-based add-on

For any add-ons with Tiered, Volume, or Stair Step Pricing Models, all mid-cycle changes will be credited/charged based on the site-level settings configured on the Invoice Settings page for handling credits and charges that result from immediate subscription changes. However, the flexibility in choosing how to issue a charge or credit for these types of add-ons is not supported with subscription-level overrides in the Recurly App UI. However, you are able to override the charge/credit behavior for these types of add-ons at the subscription level via the API.

Thus, Tiered, Volume, and Stair Step add-ons will either follow the charge/credit settings from the site-level configuration on the Invoice Settings page, or you can override their charge/credit options at the subscription level using the API, or else they will follow the custom options applied on the subscription change that were made as a result of changing the plan, price and/or quantity of the existing plan, or making a change to fixed-price add-ons. The invoices will display the charge/credit based on the subscription's tiers and prices.

#### Change usage-based add-on

In case of an immediate change that doesn't alter the subscription's plan, usage-based add-ons will generate charges and credits as follows:

* Unchanged usage-based add-ons will not appear on the change invoice, and any unbilled usage remains unbilled.
* If a usage-based add-on is removed, or its price or percentage is changed, a charge for any unbilled current usage will be created.
* Adding a usage-based add-on alone will not create an invoice for the immediate change, as usage-based add-ons are billed in arrears and do not appear on their first invoice.
* Unbilled corrections logged against a past cycle for a usage-based add-on will not be invoiced in the immediate change unless the add-on is altered. If unchanged, the corrections will be invoiced at the next billing date.

#### Terminate and refund subscription

Recurly allows for a refund when a subscription is terminated. This refund applies only to the last invoice of the subscription, which could be from the most recent billing date or an immediate change invoice from the current period. For merchants allowing immediate subscription changes, a refund due to termination can be perplexing since only the charges from the last subscription change are refunded, not the entire period's charges. If the last invoice was from an immediate subscription change where the plan remained unchanged, it might not include all subscription products, only the recently changed ones. Or, if the last invoice only had credits, it's not refundable, thus the refund request is disregarded.

#### Change plan period

Immediate subscription changes retaining the same plan period (e.g., monthly to monthly or yearly to yearly) will keep the current billing period and subscription term, following the usual proration rules. However, if the immediate subscription change alters the underlying period (e.g., monthly to yearly or yearly to monthly) and/or the term length (e.g., 12 periods to 6 periods), the subscription billing term will restart, and the new charges will not be prorated.

_**Example Change with Same Billing Period and Subscription Term**_

A customer subscribes to the Silver Plan, billed monthly with an annual term, on Jan 15, 2018, and upgrades to the Gold plan, also billed monthly with an annual term, on May 15, 2018.

* The subscription maintains the current billing period of May 15 - June 15, 2018.
* The change invoice presents a prorated charge for Gold covering May 15 - June 15, 2018.
* The change invoice also shows a prorated credit for Silver covering May 15 - June 15, 2018.
* The remaining number of billing periods in the term remains unaffected.

_**Example Change with Different Billing Period and Subscription Term**_

A customer subscribes to the Silver Plan, billed monthly with an annual term, on Jan 15, 2018, and upgrades to the Gold Plan, billed quarterly with a two-year term, on May 15, 2018.

* The subscription now has a new billing period of May 15, 2018 - Aug 15, 2018.
* The change invoice shows a full charge for the two-year Gold covering May 15, 2018 - Aug 15, 2018.
* The change invoice also includes a prorated credit for the monthly Silver covering May 15 - June 15, 2018.

### Credits

#### A credit's original charge

To identify the invoice containing the charge line item from which a credit line item originated, you'll need to refer to the credit's invoice. The display added on the invoice provides a reference to help you and your customers trace back the credit to its original charge.

<Image align="center" border={false} width="80%" src="https://files.readme.io/4c1998d-DOCS_-_credit_link.png" />

#### Multiple credits for one product

Each credit line item is linked to a single charge line item. This is crucial as reversing any discounts or taxes would muddle your reporting if a single large credit was linked to multiple charges. Due to this one-to-one credit-to-charge relationship, a subscription change invoice could present two credits for the same product. Each credit line item links back to a different charge line item on a different invoice, and the invoice display will showcase the different invoices, as illustrated in the above example of the invoice reference.

_**Multiple Credit Example**_

Initially, 5 users of Gold at $10/user/month are purchased. Later, 2 more users are added mid-cycle, making it 7 users. Then, with a quarter of the cycle remaining, 3 users are removed, bringing the total to 4 users.

<Image align="center" border={false} width="80%" src="https://files.readme.io/c93c957-DOCS_-_Multiple_Credits.jpg" />

In the last invoice, #3, the aim is to credit the customer for 3 users, which equates to 3 x $10 = $30. However, with only 25% of the cycle left, only 25% of $30, which is $7.50, should be credited back.

The charge on invoice #2 has $10.00 that can be credited, but since it only represents 2 users and 3 users are being credited, we need to locate the correct charges to credit before applying proration. The target is to credit $30 before proration, thus $30 worth of charges pre-proration need to be found. The charge on invoice #2 is $20 before proration, and the charge on invoice #1 is $50 without any proration. Working our way back, we require the full charge on invoice #2 and only $10 of the charge on invoice #1.

* Pre-proration credit remaining for Gold (from invoice #2): 1 x ($20)
* Pre-proration credit remaining for Gold (from invoice #1): 1 x ($10)
  Then, applying a 25% proration, we get:
* Post-proration credit remaining for Gold (from invoice #2): 1 x ($5)
* Post-proration credit remaining for Gold (from invoice #1): 1 x ($2.50)
  Accumulating to a total credit of ($7.50).

#### Credit quantity is 1

Credits generated during a subscription change event always carry a quantity of "1". However, custom credits and refunds can have varying quantities.

Recurly users have the liberty to alter the price and quantity of a subscription. When delving into more complex permutations of changes within a single billing cycle, it's possible to see two credits for the same product with unclear quantities and prices. To avoid the need for special rules for a credit's quantity and price based on the type of change, and to minimize confusion, it's decided that the quantity will always be marked as 1 on the invoice. This way, customers can focus on the amount credited, with their subscription accurately reflecting the current quantity and price, affirming any product changes made.

_**Why Quantity is 1 Example**_

Initially, 5 users of Gold at $10/user/month are purchased. Then, a quarter into the cycle, 2 more users are added, bringing the total to 7 users. At mid-cycle, the price per user is increased from $10 to $15. Lastly, with a quarter of the cycle remaining, 3 users are removed, leaving 4 users at $15/user.

<Image align="center" border={false} width="80%" src="https://files.readme.io/c5a6324-DOCS_-_Confusing_Quantity.jpg" />

Invoice #4A illustrates what the invoice would resemble if the quantity wasn't set to 1. The removal of 3 users shows a credit with a quantity of 7 and another with a quantity of 2, neither of which correspond to the 3 users. Invoice #4B, on the other hand, enforces a credit quantity of 1, directing the customer's attention to the amounts being credited from the two previous invoices for Gold in the billing cycle.

Breaking down the details, the goal is to credit 3 users at $15/user, totaling $45. But, with only 25% of the cycle remaining, the actual credit should be 25% x $45, or $11.25.

The quest begins by fetching the necessary charges before proration, in this case, $45 worth of charges. The charge on invoice #3 is $35 before proration, leaving $10 to be sourced from the charge on invoice #2, which holds $20 before proration.

From invoice #3, the "7 x $5.00" charge is taken and the price prorated by 25% to "7 x $1.25".

Then from invoice #2, the "2 x $10.00" charge is grabbed, but only $10.00 is needed before proration, **leading to a dilemma of whether to halve the price before prorating or reduce the quantity to 1**? In this scenario, the quantity remained at 2 while the price was halved before being prorated by 25% to yield "2 x $1.25".

**This highlights the ambiguity in deciding whether to adjust the charge by quantity or price, especially when a product price change vs. a product quantity change can introduce perplexing rules for your customers.** Hence, the decision to enforce a quantity of 1 on credits as seen in invoice #4B.

#### Taxes on credits

Credits issued during an immediate subscription change will invariably reverse any taxes collected on the referenced charge. The reversed tax amount corresponds to the portion related to the credited amount. If tax collection is activated for the first time, existing subscribers altering their subscription mid-billing period might encounter new charges with tax and credits devoid of tax reversal.

**Different tax rates**

In scenarios where quantity, add-on, or price alterations occur without changing the subscription's plan, credits on a change invoice from different charge invoices could arise. This might lead to varying tax rates and addresses impacting the tax reversals on the credits. For instance, if a customer relocates between subscription changes, one credit might link back to the old address and another to the new address. Recurly accurately calculates the tax reversal on the credit using the original address, despite the invoice displaying the customer's current address.

Should mixed tax rates appear on the invoice, Recurly will exhibit the tax rate at the line item level, while the invoice level display will merely state "Taxes". Below is an example of a customer initially based in Australia, relocating to Israel and upgrading, and finally downgrading, culminating in two credits with distinct tax rates.

# Timing of changes

Subscriptions can be altered either immediately, at the next billing date, or upon the renewal of the subscription term. Each choice has its own implications:

* **Immediate changes**: These changes are billed right away, ensuring any upgrades or modifications are reflected in the customer's billing without delay.
* **At next bill date**: Changes chosen to be effective at the next billing date will be reflected on the customer's next bill, ensuring the changes are accounted for in the upcoming billing cycle.
* **At term renewal**: If changes are selected to be effective at term renewal, they will reflect on the first bill date of the renewal term. This option does not allow an immediate change to a subscription with billing for that change at term renewal. For such functionality, it's advised to contact [Recurly Support](https://support.recurly.com/).

Often, merchants prefer immediate upgrades to allow customers access to higher value products promptly, while collecting additional revenue right away. Conversely, downgrades are usually set for the next bill date or at term renewal. This approach helps lock the customer into the agreed-upon, and already paid for, billing cycle, continuing to provide the customer with the higher value product until the commencement of the next billing period or term.
In instances where there are already pending changes on a subscription, there's flexibility to alter certain attributes of the subscription without affecting other pending changes. When preserving pending changes is desired, there's an option to keep them intact while updating values like shipping address, subscription terms, invoicing and payment, and custom fields, without any impacts on the existing pending changes.

<Image align="center" alt={865} border={false} caption="Subscriptions can be canceled at three different timeframes: immediately, next bill date, or term renewal." title="Edit Subscription Options.png" src="https://files.readme.io/90e7347-Edit_Subscription_Options.png" width="smart" />

The illustration above depicts the various options available for modifying subscriptions, with cancellation available at three different timeframes. This flexibility allows for better management and control over subscription modifications, aligning with both merchant and customer preferences.

### Immediate changes

Immediate subscription changes will bill for the difference in cost right away. This results in the creation of an invoice and, if using automatic collection, a transaction attempt on the payment method provided in the Billing Information on the customer's account. If the transaction fails, the invoice and subscription will enter the Dunning process. If you prefer to block immediate changes when the transaction fails or the account is past due, please refer to the <a href="#section-modification-enforcement">Modification Enforcement</a> section.

### At next bill date changes

When the timeframe for a subscription change is set to "next bill date", Recurly saves the changes to apply them when it next bills the subscription. Recurly only retains one change request. If you submit a change request to apply at renewal and then submit a second change request, the first request will be canceled. The second request will be applied at the time frame indicated by the time frame parameter. For "next bill date" change requests, there's no need to prorate the amounts. Recurly will adjust the subscription appropriately and then invoice the user at the new amount on the invoice.
If you wish to update a pending change, please submit the original change along with the updated information. Pending changes can be cleared by updating the subscription immediately with no other changes.

At next bill date change requests only apply to product changes. All other changes, like collection method and notes, will take effect immediately, even if the change request is for the next bill date. These types of changes can be saved and applied at next bill date:

* Change the subscription's plan
* Change the plan fee price
* Change the plan fee quantity
* Add or remove an add-on
* Change an add-on price
* Change an add-on quantity

### At term renewal changes

When the timeframe for a subscription change is set to "when term renews", Recurly saves the changes to apply them when it's time to renew the subscription. Recurly only retains one change request. If you submit a change request to apply at renewal and then submit a second change request before renewal, the first request will be canceled. The second request will be applied at the time frame indicated by the time frame parameter. For "At renewal" change requests, there's no need to prorate the amounts. Recurly will adjust the subscription appropriately and then invoice the user at the new amount on the renewal invoice.

If you want to update a pending change, please submit the original change along with the updated information. Pending changes can be cleared by updating the subscription **immediately** with no other changes.
At renewal change requests only apply to product changes. All other changes, like collection method and notes, will take effect immediately, even if the change request is for when the term renews. These types of changes can be saved and applied at renewal:

* Change the subscription's plan
* Change the plan fee price
* Change the plan fee quantity
* Add or remove an add-on
* Change an add-on price
* Change an add-on quantity

<Image align="center" border={true} width="80%" src="https://files.readme.io/0087b30-DOCS_-_mixed-tax-rates.png" className="border" />

# Changes to subscriptions with discounts

Discounts on immediate subscription change invoices adhere to two primary rules:

1. Credits will reverse any discounts on the referenced charges.
2. Charges will only be discounted by currently active coupon redemptions.

### Credit discounts

When discounts are reversed on a credit, Recurly will smooth the discounts in the proportion of the credit to the charge it is against.

_**Percentage Example:**_

Consider a subscription with quantity 10, priced at $1 per quantity and a 20% off forever coupon. The first invoice will be for $8 ($10 - $2 discount). A downgrade of quantity 3 will result in a credit for $3 and $0.60 discount, so ($2.40) after the discount reversal. The discount of $0.60 comes from $3/$10 x $2.

_**Fixed Amount Example:**_

Consider a subscription with quantity 10, priced at $1 per quantity and a $2 off forever coupon. The first invoice will be for $8 ($10 - $2 discount). A downgrade of quantity 3 will result in a credit for $3 and $0.60 discount, so ($2.40). The discount of $0.60 comes from $3/$10 x $2.

### Charge discounts

When active coupon redemptions are applied to new charges, Recurly will prorate any fixed amount discounts following the same proration rate of the charge. Recurly prorates fixed amount discounts in an immediate subscription change because the discount represents the time of the cycle. If the customer is 50% through their cycle and only going to be charged 50% of the plan price, we want to ensure that they only get 50% of the discount amount. Percentage discounts automatically represent a prorated portion because they are a percentage of an already prorated amount.

It is not possible to have a fixed amount coupon redemption not prorate when applied in an immediate change. If you require this use case, please look at custom credits as an alternative and write in to <a href="https://support.recurly.com/" target="_blank">Recurly Support</a> to express your interest in this feature.

### Single-use coupons

Single-use coupons only discount charges on one invoice. If a single-use coupon is used on a bill date invoice, it will not discount new charges on an immediate change invoice.

For instance, if your single-use coupon is for "all plans" and is used on the purchase of the Silver plan, but then the customer upgrades to Gold mid-cycle, the Gold charge will not be discounted and a portion of the single-use discount will be reversed on the credit for Silver. The customer ends up losing a portion of the discount they previously received.
If it's crucial that the customer never loses the discount due to immediate changes, you should use limited time or forever duration coupons, not single-use.

### Fixed amount and long duration coupons

Recurly's fixed-amount coupons that have a limited time or forever duration are intended to be a fixed amount off for the billing period. This is why we prorate fixed amount discounts in an immediate subscription change event. Recurly tracks what discount amount is remaining for a coupon redemption for the subscription's billing period. For example, if a $50 off coupon redemption is completely used on a bill date invoice, we will ensure no more of the discount is applied in an immediate change, even if the type of product in the change is eligible and the coupon redemption is still active.

Recurly's discounting does allow a remaining amount to be applied later in the billing period if it is not consumed on the bill date. This is more of an edge case. For instance, if only $40 of the $50 discount is used on the bill date, we will track that a $10 discount amount is still available in the billing period. But since the $50 is per period, we will prorate the $10 if applied in an upgrade to reflect that time has passed.

### Mid-cycle redemptions and upgrade discounts

Discounts will affect immediate changes differently if the subscription is being rebilled due to a plan change or only billing what changed due to a quantity, price, or add-on change.

If you redeem a new coupon on an account in the middle of the customer's subscription billing period and an immediate change rebills the subscription, the discount will apply to the new version of the subscription for the time remaining in the period.

If instead the immediate change only bills what changed, the discount will apply to only the additional quantities, price, or add-ons. For example, if quantity is increased from 7 to 10, the new charge is for 3 quantities and will therefore only discount the additional 3 quantities, instead of the full 10. Conceptually, if you are going to give someone a discount for upgrading, you are giving them the discount on just the upgraded portion, since they committed to the upgrade mid-cycle. At the bill date, the discount would have the ability to apply to all 10 quantities.

# Changes to subscriptions in free trial

### No change invoices

While an invoice is created when a subscription starts its free trial, Recurly will not create an invoice for an immediate change during a trial period. This means Recurly will not charge a customer for an upgrade while they are in trial. The customer is essentially trialing anything you allow them to have. If you would like to charge the customer for a subscription change while in trial, you will need to create a one-off invoice for the charge.

### Trials and plan changes

If a subscription change alters the underlying plan and the new plan has a different trial rule, the original plan's trial rules will hold.

_**Example: 7-day trial to no trial**_

If a subscription currently in a 7-day trial changes its plan to one without a trial, the subscription will stay in the current 7-day trial, but now have access to the new plan. For example, if the customer is 4 days into the trial and changes their plan, they will get the new plan free for 3 days.

_**Example: No trial to 7-day trial**_

If a subscription is currently not in a trial and changes its plan to one with a 7-day trial, the subscription will not receive a trial and will be charged for the new plan.

_**Example: 7-day trial to 14-day trial**_

If a subscription currently in a 7-day trial changes its plan to one with a 14-day trial, the subscription will stay in the current 7-day trial, but now with access to the new plan. For example, if the customer is 4 days into the trial and changes their plan, they will only get a 3-day trial of the new plan that normally has a 14-day trial.

### Convert trial

If you do not want the original trial to continue, you can submit a request to the Convert Trial API or use the Admin Console. This request will end the trial and transition the subscription to a new billing cycle on the new plan immediately. If the transaction is not successful, the trial will continue.

# Redeeming a coupon as part of a change

Coupons can only be redeemed in subscription changes that are immediate and include a product change.
Coupon redemption was added to subscription changes to support upgrades with subscription-level coupons. Since a subscription-level coupon must be tied to a subscription with an eligible plan at the time of redemption, upgrades present a scenario where the account does not necessarily have a subscription to the coupon's eligible plans. Therefore, redeeming the subscription-level coupon while the subscription's plan is changing to an eligible plan solves that problem.

While coupon redemption was added to subscription changes for subscription-level coupons, account-level coupons can be redeemed as well. Note that the subscription's new version has to have a plan that is eligible for the new coupon.
Recurly does not allow coupons to be redeemed at renewal requests because the coupon may have redemption limits for the campaign or the account and managing pending redemptions or immediate redemptions related to pending changes that might be canceled could lead to a poor user experience.

Coupon redemption requires a product change to avoid a subscription being changed only for the sake of redeeming a coupon. Coupons can always be redeemed directly on the account, outside of a subscription action. A product change includes a plan, price, quantity, or add-on change.

# Preview changes

When you are making an immediate change to a subscription, and would like to see what the resulting invoices will be, click on the 'Preview Invoice' button before saving the changes. This will give you a snapshot of what invoices, both charge and credit, will be created for the customer, and will provide information on what the billable amount to the customer, based on the proration calculation, will be.

When 'Save Changes' is selected, the final amounts will be created and applied to the customer account. This amount may be slightly different than the amount seen on the preview invoice(s), since the final amount is calculated down to the exact second the change is made.

<Image align="center" border={true} src="https://files.readme.io/6776efd99af877a51a54be06a5fda062aab4948204e0528ae1573aeecd5a1460-image.png" className="border" />

# Email communications

Both automatic and manually collected subscriptions will issue the Subscription Change email, if enabled, to the customer at the time of the change. This means an immediate change will issue the email immediately and an at renewal change will issue the email when the subscription renews.

* Manually collected subscriptions will additionally send the New Invoice email, if enabled, to the customer.
* Automatically collected subscriptions will additionally send either the Payment Confirmation or Payment Declined email, if enabled, to the customer, depending on whether the transaction was successful or declined. If the immediate change was a downgrade, no "Payment" email will go out.

> **Note:** If Credit Invoices is enabled, the Subscription Change email will be sent immediately regardless of the time of change.

# Modification enforcement

Some merchants may prefer to have their customers current and up-to-date on all payments before allowing a subscription upgrade or downgrade. Recurly allows this to be configured on your Invoice Settings page through two different options.

### Require paid invoice and successful transaction on upgrades

When upgrading an existing subscription immediately, require that the account have no past due invoices and the payment information on file process successfully in order to complete the upgrade. If the payment information is declined, the subscription will be kept on the original plan.

### Require paid invoice to downgrade

When downgrading an existing subscription immediately, require that all invoices have been successfully paid in order to complete the downgrade. If any invoice is past due, the subscription will be kept on the original plan, and an error will be provided to the customer; "Your account is currently past due, please update your billing information before changing your subscription."

[Learn more about subscription modification enforcement.](https://docs.recurly.com/docs/invoice-settings#section-modification-enforcement)
