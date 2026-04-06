---
title: Coupons & discounts
excerpt: >-
  Streamline your promotional campaigns, boost customer engagement, reward loyal
  customers, and drive revenue growth. Understand, create, manage, and analyze
  coupon strategies with ease.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  image: https://files.readme.io/e9ce049-Screenshot_2.png
  robots: index
next:
  description: ''
---
# Overview

### Required plan

This feature or setting is available to all customers on any Recurly subscription plan.

### Prerequisites

* A Recurly account with access to the Configuration section
* At least one subscription plan configured in your Recurly site
* Coupons enabled in your Checkout or Hosted Page Settings if you plan to allow redemption on hosted payment pages

### Limitations

* Once created, the following coupon attributes cannot be edited: coupon code, discount type, duration, eligible plans, eligible items, and discount level
* Free trial coupons cannot be applied directly to an existing account — they must be used at the time of subscription creation
* Coupons cannot be applied alongside "On next renewal" subscription changes
* A fixed amount discount that exceeds eligible charges on an invoice will not carry over to future invoices
* Percentage discounts never apply to plan setup fees
* Coupons cannot retroactively discount an existing invoice

***

# Definition

Coupons and discounts give you a flexible way to offer price reductions to your subscribers — whether automatically applied at checkout or redeemed manually via a code. Together, they help you run targeted promotions, reward loyal customers, and drive new signups.

It's worth understanding the distinction between the two:

* **Discount:** A price reduction applied automatically by you to a product or service — no action required from the subscriber. For example, 20% off all plans during a promotional weekend.
* **Coupon:** A code that subscribers can enter at checkout to receive a price reduction. For example, a $10 off code usable on any purchase over $50.

Throughout this guide, "apply the discount" refers to both scenarios — whether the reduction is applied automatically or triggered by a subscriber entering a coupon code.

***

# Key benefits

* **Revenue enhancement:** Attract and retain subscribers with targeted promotions that drive conversions and increase revenue.
* **Customer loyalty and engagement:** Reward your most valuable customers with exclusive discounts that foster long-term loyalty and interaction.
* **Strategic flexibility and insights:** Tailor promotions to specific plans, items, or billing cycles — then analyze redemption data to stay informed and agile.

***

# Key details

## Creating a coupon

Before you build a coupon, it helps to understand what each field in the creation form does. Here's a breakdown:

### Coupon fields

**Internal name**
Used to identify the coupon campaign internally. It's not shown to subscribers unless you intentionally expose it via API or email. Use a descriptive, distinctive name to make it easy to reference later.

**Code type and code**
This determines how subscribers redeem the coupon. You have two options:

* **Single code:** One code that can be used multiple times, based on your redemption settings. Simple to create and distribute.
* **Bulk unique codes:** A set of one-time-use codes generated in bulk — ideal for personalized offers and preventing code sharing. See the [bulk unique codes documentation](https://docs.recurly.com/docs/bulk-unique-coupons) to learn more.

Coupon codes support alphanumeric characters, dashes (-), underscores (_), and plus signs (+). A code can be reused only after the previous coupon using that code has expired or reached its maximum redemption limit.

**Type of discount**
Choose from a fixed amount, percentage, or free trial. Fixed amount coupons support multi-currency — you can specify different amounts for each currency you support.

**Duration**
Determines how long the discount applies after redemption. Options are forever, single use, or limited time (defined in days, weeks, or months).

**Maximum redemptions**
The total number of times the coupon can be redeemed across all accounts. Leave unlimited or set a specific cap to control reach.

**Redemptions per account**
Limits how many times a single account can redeem the coupon — once, unlimited, or a specific number. This prevents subscribers from applying the same discount multiple times.

**Redeem by date**
An optional expiration date. After this date, the coupon can no longer be redeemed.

**Eligible charges**
Specifies which charge types the coupon can discount: recurring charges (plan fees, add-ons, and setup fees), one-time charges only, or both.

**Eligible plans**
Defines which subscription plans qualify for the discount. Defaults to all plans but can be restricted to specific ones.

**Eligible items**
Defines which catalog items qualify for the discount. Defaults to all items but can be restricted to specific ones.

**Discount level**
Determines whether the discount applies at the account level (across all eligible subscriptions) or at the subscription level (tied to a specific subscription only).

**Payment page description**
Shown to subscribers when they redeem the coupon on your checkout page, hosted payment page, or via the API. Can be up to 255 characters.

**Invoice description**
A short description that appears in the "Discounts applied" section on the invoice. Not applicable to free trial coupons, since they don't offer a monetary discount.

***

### Step-by-step: create a new coupon

1. Navigate to **Configuration** and click **Coupons**.

<Image align="center" border={true} width="30% " src="https://files.readme.io/8d4e1fda7827d03b8f9d95d4ab67e4911db8cc092db4072c44c08d0f83f7607a-image.png" className="border" />

2. Click **New Coupon**.

<Image align="center" border={true} width="75%" src="https://files.readme.io/6eb6423097ca5013a67c2465b02c775705143514fb838a48b056ade1f7eb33a8-image.png" className="border" />

3. Enter a unique internal name for the coupon.

<Image align="center" border={true} width="75%" src="https://files.readme.io/2fef3df53f39b9e4fa4010ab5f7558d34ea3d236ba085162288d6b364d7c1ece-image.png" className="border" />

4. Select a code type — single code or bulk unique codes.

<Image align="center" border={true} width="75%" src="https://files.readme.io/319f342ec6bdb8fbe9d15e4d3ae1fa1ab46ffc1b43bba9e5dd664a8662b4f8a5-image.png" className="border" />

5. Choose a discount type — percentage, fixed amount, or free trial.

<Image align="center" border={true} width="75%" src="https://files.readme.io/4adaab2597af8e79038a3fbe21b7523378bf990bf8d463e6629204fa46991452-image.png" className="border" />

6. Set the coupon duration — single use, forever, or a limited number of days, weeks, or months.

<Image align="center" border={true} width="75%" src="https://files.readme.io/552c773229720e3d71d8d5ebff6867ba6faadb03b86946d7c560a88745ec95a5-image.png" className="border" />

7. Configure redemption rules.

<Image align="center" border={true} width="75%" src="https://files.readme.io/e301291244dce72198845b003186c2a73dcd1051f15e07d4c086fc98c1908af8-image.png" className="border" />

8. Define eligible charges, plans, and items.

<Image align="center" border={true} width="75%" src="https://files.readme.io/75fef086e8d7aee54cd6470171ed8a5d706899f64a1fdfbeaa47f1e7a93cb551-image.png" className="border" />

9. Optionally, add a payment page description and/or invoice description.

10. Click **Create coupon** to finalize.

> **Note:** The discount will automatically appear on the invoice when it's generated.

***

## Editing an existing coupon

To update a coupon, navigate to **Configuration > Coupons**, select the coupon you want to update, and click **Edit**.

The following fields can be modified after a coupon is created:

* Internal name
* Maximum redemptions
* Redeem by date
* Redemptions per account
* Payment page description
* Invoice description (not applicable to free trial coupons)

> **Note:** Changes only affect coupons redeemed after the update is saved. Existing redemptions are not impacted.

***

## Types of discounts

### Percentage discounts

A percentage discount applies the same rate to each eligible charge on the invoice. One important note: percentage discounts never apply to plan setup fees. This makes them useful when you want to discount recurring plan fees and add-ons specifically.

**Example:** A 10% discount on Plan A (setup fee: $50, plan fee: $15, add-on: $7)

* Setup fee ($50): not discounted
* Plan fee ($15): discounted by 10% = ($1.50)
* Add-on ($7): discounted by 10% = ($0.70)
* **Total discount: ($2.20) — final payable amount: $69.80**

### Fixed amount discounts

A fixed amount discount is distributed across all eligible charges starting with the first subscription line item, which is typically the setup fee. If the discount exceeds the total eligible charges, the remaining balance is not returned or carried over to future invoices.

To target only a plan's setup fee, create a single-use coupon with a fixed amount equal to or less than the setup fee. Since the setup fee is always the first subscription line item, the discount will apply there before reaching other charges.

Also worth noting: one-time charges appear on the invoice before subscription charges, but are discounted _after_ subscription charges. If your fixed amount discount is less than the total subscription charges, one-time charges will not receive a discount.

**Example:** A $20 discount on Plan A (plan fee: $15, add-on: $7)

* Plan fee ($15): fully discounted = ($15.00)
* Add-on ($7): partially discounted with remaining $5 = ($5.00)
* **Total discount: ($20.00) — final payable amount: $2.00**

### Free trial coupons

Free trial coupons let you offer a custom trial length that differs from your standard trial period. The trial starts on the day the subscription is created. Because free trial coupons don't provide a monetary discount, they don't appear on any invoices.

***

## Discount duration options

**Forever**
The discount applies indefinitely, for as long as the subscription remains active.

**Single use**
The discount applies to one invoice only.

**Limited time**
The discount applies for a defined period — a specified number of days, weeks, months, or years. Any invoices generated within that period will receive the discount. We recommend setting the period to match the billing cycle of the eligible plans.

> **Note:** Limited-time coupons expire automatically one hour before the anniversary of their redemption date.

***

## Redemption settings

### Number of redemptions

Define how many times the coupon can be redeemed across all accounts — unlimited or a specific number.

### Redemptions per account

Set how many times a single account can redeem the coupon — once, unlimited, or a specific number.

### Redeem by date

Set an expiration date for the coupon, or leave it open-ended so subscribers can redeem it at any time.

***

## Applying a coupon

### During a purchase

Subscribers can enter a coupon code at checkout via your hosted payment page, your own checkout page using Recurly.js or the API, or the Recurly UI when adding a subscription to an existing account.

A few things to keep in mind:

* The purchase must include charges eligible for the discount — a coupon for Plan B won't apply during signup for Plan A
* If the subscription creation fails due to a declined transaction, the coupon won't be applied
* If only one active coupon is allowed per account, a new coupon will replace any existing one
* If multiple active coupons are allowed, the new code is added to the list and applied after existing discounts
* Subscription-level coupons redeemed during subscription creation are automatically tied to that subscription
* Account-level coupons apply to the new subscription and any future subscriptions added to the account

To pre-populate a coupon code on your hosted payment page, use the URL parameter: `?subscription[coupon_code]=10off`

> **Note:** Coupons cannot currently be applied to existing accounts through hosted account management pages. To request this capability, submit a [support ticket](https://support.recurly.com/).

### During an upgrade or downgrade

You can apply a coupon when upgrading or downgrading a subscription so the discount applies to the updated invoice. Keep in mind:

* The eligible charges must include the new plan
* Coupons cannot be applied with "On next renewal" changes
* A plan, quantity, or price change must be part of the subscription update — the coupon cannot be the only change

### Directly on an account

To discount the next invoice for an existing subscription or a one-time charge, apply the coupon directly to the account via the Recurly UI (**Manage Coupons** on the account page) or through the API.

***

## Removing a coupon

To remove a coupon from a subscriber's account:

1. Navigate to the **Coupon Redemptions** page for the account
2. In the "Redeemed on account" table, locate the coupon you want to remove
3. Select the coupon and follow the prompts to complete the removal

Removing a coupon stops the discount from applying to future invoices. Invoices already issued are not affected. The subscriber will be charged the regular price on their next billing cycle.

***

## Expiration and restoration

### Expiring a coupon early

To manually expire a coupon, go to the coupon's overview page and select **Expire early**. The coupon will expire immediately. Subscribers who have already redeemed it are not affected.

### Automatic expiration

Coupons expire automatically when they reach their redeem by date or maximum redemptions limit.

### Reusing a coupon code

Once a coupon expires or reaches its redemption limit, the code can be reused when creating a new coupon.

### Restoring an expired coupon

You can restore an expired coupon to make it redeemable again. If it expired due to reaching its redemption limit or redeem by date, you'll need to update those fields before restoring.

***

## Reporting and analysis

You can track and analyze coupon performance from the **Exports** page under **Reports**.

| Export                              | What it shows                                                                                        |
| ----------------------------------- | ---------------------------------------------------------------------------------------------------- |
| **Coupons**                         | All coupons on your site, their rules, and creation or expiration dates                              |
| **Coupon Redemptions**              | Who redeemed coupons, when, and how much discount was applied                                        |
| **Invoices – Summary**              | Which coupons were applied to each invoice (see the `coupon_code` column)                            |
| **Invoices – Line Items**           | Which coupons were applied to each line item and the total discount                                  |
| **Invoices – Line Items – Coupons** | Specific discounts per coupon per line item (only visible with Multiple Coupons Per Account enabled) |

***

# FAQs

**What happens with discounts when a plan includes a free trial and a setup fee?**

Discounts are not applied to a free trial invoice unless there's a setup fee and the coupon is a fixed amount. In that case, we recommend setting the coupon duration to "Limited time" for one month rather than "Single use." This ensures both the setup fee and the first paid month receive the discount.

**How does coupon accounting work in Recurly?**

Both percentage and fixed amount coupons are applied to charge line items before tax is calculated. Credits are applied after coupons have already discounted the charges. Coupons apply to the next invoice created after redemption — they can't retroactively adjust an existing invoice. To correct an already-issued invoice, you can issue a partial refund equal to the discount amount, or do a full refund, redeem the coupon, and reissue the invoice. Free trial coupons don't offer a monetary discount and don't appear on any invoices.

**Can subscribers have multiple active coupon redemptions on their account?**

Yes — you can allow multiple active coupon redemptions per account, which can result in multiple discounts appearing on a single invoice or line item. Settings for this feature can be adjusted on the coupon configuration page. See the [Multiple Coupons Per Account documentation](https://recurly.com/developers/api/v2021-02-25/index.html#tag/coupon) for details on how stacked discounts are applied.

**How do I create a coupon that discounts across several billing cycles?**

Set the duration to "Limited time" and configure the period to match your plan's billing cycle. Keep in mind that if the discount is a fixed amount and eligible charges are less than the discount on any given invoice, the remaining balance won't carry forward.

**Where can I find coupon redemption data?**

Every coupon has a Redemptions table showing all accounts that have redeemed it, along with the total discount applied. For bulk coupons, a "Not redeemed" table displays all unused unique codes. You can expire unredeemed codes early — expired codes appear at the end of the table.
