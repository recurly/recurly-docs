---
title: Multiple coupons per account
excerpt: >-
  Explore the dynamic ways to drive customer engagement and boost revenue by
  allowing your customers to redeem multiple coupons and receive multiple
  discounts at a time.
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

Recurly's "Multiple Coupons per Account" feature allows customers to participate in multiple campaigns or redeem more than one coupon on your checkout page. This feature can apply all eligible coupon discounts to each purchase invoice when multiple coupons are redeemed on an account.

# Key benefits

* **Loyalty through flexibility**: Allows multiple coupons per account, enhancing customer satisfaction and loyalty.
* **Strategic campaign management**: Facilitates the running of various promotional campaigns concurrently, optimizing marketing efforts.
* **Granular discount control**: Provides precise control over discount sequencing, with options for percentage or fixed amount precedence.

# Key details

## Why allow multiple coupons on an account?

Enabling multiple coupons on an account not only magnifies savings for your customers but also broadens the spectrum of your promotional campaigns. Say, you have a loyal customer enjoying a 10% off perpetual early-adopter discount. With the multiple coupons feature, they can now also indulge in your latest $20 off coupon campaign. Should both coupons meet the eligibility criteria for a purchase, voila! Both discounts get applied to the invoice line item, amplifying the joy of savings.

## Which coupons are applied to the invoice?

Upon activating the Multiple Coupons Per Account feature, any eligible coupons redeemed on an account will automatically grace each purchase invoice with their respective discounts. This automatic application is the inherent behavior of this feature and doesn't entertain a one-coupon-per-invoice configuration. However, if your goal is to stick to a single coupon discount per purchase while keeping multiple coupons active on customer accounts, opt for our [Subscription Level](https://docs.recurly.com/coupons-beta#subscription_level_coupons) coupon scheme. This allows you to associate a specific coupon discount with a particular subscription.

## Multiple percentage discounts

As you switch on the Multiple Coupons Per Account, decisions await on the handling of multiple percentage discounts, especially when more than one is eligible for a single invoice line item.

### Apply to full line item amount

Choosing "Apply to full line item amount" ensures that each percentage discount addresses the entire line item amount, sequentially from the oldest to the newest redeemed on the account. 

* In cases where fixed-amount coupons precede in settings and are applied to the invoice, the percentage discounts then embrace the net amount post fixed-coupon deductions, veering away from the full line item amount.
* Upon reaching a full discount on the line item, the curtain falls on further coupon discounts, potentially sidelining an eligible coupon if other coupons have already orchestrated a 100% discount.
* This method tips the scale in favor of the customer, offering a more generous discount.

### Compound the discounts

Opting for "Compound the discounts" directs each percentage discount to the net residue post the preceding discount, aligning from the oldest to the newest redeemed on the account.

* Similar to the previous method, a fully discounted line item halts any further coupon applications, leaving an eligible coupon in the wings if preceding coupons already rendered a 100% discount.
* This tactic leans towards the merchant’s advantage, rendering a modest discount.

### Example

Let's illustrate with Coupon A offering a 10% discount and Coupon B extending a 50% discount on a $100.00 line item purchase.

* Employing the "Apply to full line item amount" method yields a $10.00 discount from Coupon A and a $50.00 discount from Coupon B, aggregating to a total discount of $60.00 on the line item. Thus, the purchase subtotal rolls down to $40.00.
* On the other hand, the "Compound the discounts" technique triggers a $10.00 discount from Coupon A and a subsequent $45.00 discount from Coupon B (calculated on the remaining $90.00), amalgamating to a total discount of $55.00 on the line item. Hence, the purchase subtotal modestly descends to $45.00.

## Proration

When a subscription alteration occurs mid-billing cycle, prorated credits and charges come into play. Each discount associated with these prorated amounts is meticulously calculated at the individual coupon redemption level for every line item. For instance, suppose a line item has been graced with three different coupon redemptions. Each of these three discount fragments is prorated individually, their collective discount values then aggregated to form the line item's total discount amount for the prorated charge or credit.

## Refunds

* **Line Item Refunds** impeccably preserve the discount amount and identity right down to the individual coupon redemptions on the line item. The invoice displays the line item level discounts, and exports shine a light on the individual coupon redemption discounts.
* **Open Amount Refunds**, on the flip side, ensure the correct amount is refunded but do not retain the discount amount or identity. The discount remains absent from both the refund invoice and exports.

## Invoices

The Discounts Applied section on the invoice unfurls a detailed view of all coupons that have lent their discounts to the invoice. In scenarios where a coupon has been redeemed multiple times on the same invoice, a singular mention of the coupon surfaces, accompanied by a count (enclosed in parentheses) indicating the number of redemptions.

## Exports

Merchants have the provision to delve into multiple discounts via the Invoices - Summary, Invoices - Line Items, and the fresh Invoices - Line Item Coupons exports.

### Invoices - summary

This export resolves queries regarding which coupons have been applied to the invoice.

* The `coupon_code` column unveils a comma-separated list of coupon codes, provided the invoice has more than one coupon code applied.
* A unique roster of coupons applied to the invoice is presented. In cases of multiple redemptions of a coupon on the same invoice, the coupon makes a singular appearance on this list.
* Coupons contributing to calculated returned credits are also exhibited on this list.

Explore the minutiae of this export in our [Invoices - Summary export documentation](/export-overview#invoices-summary).

### Invoices - line Items

This export elucidates which coupons have kissed the line item with their discounts and the total discount birthed on the line item.

* The `adjustment_discount` column showcases the total discount for the line item.
* Should the line item be adorned with more than one coupon code, the `adjustment_coupon_code` column reveals a comma-separated list of these coupon codes.
* Unique coupons applied to the line item make their way to this list. Even if a coupon is redeemed multiple times on a single line item, its mention is singular.
* Coupons instrumental in calculating returned credits are also paraded on this list.

Dive deeper into this export via our [Invoices - Line Items export documentation](/export-overview#invoices-line-items).

### Invoices - line Items - coupons

Dedicated to detailing the individual discounts each coupon bestows upon a line item, this export rolls out only when the Multiple Coupons Per Account feature is activated in your coupon settings.

* Each line item discount births a row in this export. A line item basking in multiple discounts will have multiple rows dedicated to it in the export.
* The `adjustment_discount` column flaunts the fragment of the line item discount crafted by the specific coupon reflected in the `adjustment_coupon_code` column for that row.
* Each `adjustment_coupon_code` column unveils a single coupon code. Witnessing two rows for the same line item brandishing the same coupon code translates to multiple redemptions of the coupon, each carving out a discount on the line item.
* Line items pertaining to credits also exhibit any coupons and discounts applied, ensuring accurate credit calculations.

Scrutinize the details of this export in our [Invoices - Line Items Coupons export documentation](/export-overview#invoices-line-items-coupons).

# Guide to enable multiple coupons per account

**Step 1: Navigate to the coupons configuration Page**

* Log into your admin dashboard.
* Navigate to the ‘Configuration’ section, usually found in the settings or admin panel.
* Select the ‘Coupons’ page.

**Step 2: Access the Coupon Settings**

* On the ‘Coupons’ page, locate the 'Settings' button at the top right of the page.
* Click on the ‘Settings’ button.

**Step 3: Enable Multiple Coupons Per Account**

* Find the section titled ‘Multiple Coupons Per Account’ within the Settings page.
* Select the ‘Enable’ option, usually represented as a checkbox or toggle button.

**Step 4: Configure the Order of Application**

### Order of coupon application

When enabling Multiple Coupons Per Account, a decision must be made on the order in which percentage discounts and fixed amount discounts are applied when both are eligible for a single invoice line item. The two options are:

**Apply Percentage Discounts First**

This approach prioritizes customer savings. All percentage discounts are applied to the line item first, followed by fixed amount discounts. This may result in a larger total discount for the customer.

**Apply Fixed Amount Discounts First**

This option is more favorable to the merchant, as fixed amount discounts are applied to the line item first, followed by percentage discounts, which could result in a smaller total discount for the customer.

### Order of application (subscription vs account level)

When you enable Multiple Coupons Per Account, you need to decide in what order you would like us to apply percentage discounts and fixed amount discounts in the event both discount types are eligible for a single line item on an invoice. In this particular case of multiple coupons being applied to multiple subscriptions or a hybrid purchase, we will preserve the order of the coupon application that is configured in your coupon settings. Coupons that are configured for one-time purchases, will apply based on that type of discount (percentage or fixed amount). 

#### Subscription level coupon application

* Multiple subscription level coupons that are redeemed in a purchase where >1 subscription is eligible, the coupons will apply to the first eligible and more expensive subscription (if applicable).

* If a subscription level coupon is redeemed in a purchase but its eligible subscription is already entirely discounted (presumably by other coupons or credits), the coupon will still be redeemed to the subscription without applying a discount and should remain active and unused until the subscriptions next invoice. 

* Subscription-level coupons that are fixed amount, will not carry over any leftover discount to other eligible subscriptions.

#### Account level coupon application

**Fixed amount account level**

* A fixed amount, account level coupon, that is eligible to all plans and one time charges will apply first to a setup fee if there is one,  and then other setup fees - if there is additional discount remaining, first subscription plan, and work it's way down the plan fees and then the adjustments if the discount can.

* If an account level coupon is redeemed in a purchase but it's eligible charge(s) are already entirely discounted, the coupon will be redeemed to the account and should remain active and unused until the next invoice.

**Continue with the following:**

* In the same ‘Settings’ page, find the section titled ‘Order of Application’.
* Choose between “Apply Percentage First” or “Apply Fixed Amount First” based on your preference.
  * “Apply Percentage First” applies percentage discounts before fixed amount discounts.
  * “Apply Fixed Amount First” applies fixed amount discounts before percentage discounts.

**Step 5: Configure multiple percentage discounts**

* In the same ‘Settings’ page, locate the ‘Multiple Percentage Discounts’ section.
* Choose between "Apply to Full Line Item Amount" or "Compound the Discounts” based on your preference.
  * “Apply to Full Line Item Amount” applies each percentage discount to the full line item amount.
  * “Compound the Discounts” applies each percentage discount to the net result of the previous discount.

**Step 6: Save your settings**

* After confirming that “Order of Application” and “Multiple Percentage Discounts” are set to the options you want, find the ‘Save’ button, usually located at the bottom of the page.
* Click on the ‘Save’ button to confirm and implement the changes.

**Step 7: Review and test**

* It’s advisable to create a test account or use a sandbox environment to verify the functionality and confirm that the coupons are being applied in the desired manner.

![865](https://files.readme.io/nppgofaXQ2yeqLSibs9g_multiple-coupons-per-account.png "multiple-coupons-per-account.png")
