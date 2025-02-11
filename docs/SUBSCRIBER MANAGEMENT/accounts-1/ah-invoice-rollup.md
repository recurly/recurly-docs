---
title: Account hierarchy - invoice rollup
excerpt: >-
  Simplify your billing process with Recurly's Account Hierarchy - Invoice
  Rollup feature. Consolidate charges from multiple accounts into a single
  invoice, enhancing clarity and reducing administrative effort.
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

This feature is only available to customers on the Elite subscription plan. To request to upgrade to this plan, please reach out to your Recurly account manager or [support@recurly.com](mailto:support@recurly.com) for more details.

# Definition

Account Hierarchy - Invoice Rollup is a feature in Recurly that allows businesses to consolidate line items from multiple accounts within an account hierarchy and bill them to the parent account in a single invoice. This feature is powered by Recurly's Calendar Billing feature and is particularly useful for businesses managing multiple accounts with shared billing responsibilities.

# Key benefits

- **Simplified billing:** Consolidate charges from multiple accounts into a single invoice, reducing administrative effort and enhancing clarity.
- **Enhanced tracking:** Easily track charges and invoices across multiple accounts with detailed invoice displays and API support.
- **Flexible management:** Handle one-time charges, recurring charges, and subscription changes across multiple accounts with ease.
- **Improved customer experience:** Provide a more streamlined and clear billing experience for your customers by consolidating invoices.
- **Efficient taxation:** Tax line items based on the parent account's taxable address or, if needed, on the child account's address.

# Key details

This functionality is powered by Recurly's Calendar Billing feature, detailed as follows:

- Through [Calendar Billing - Aggregate Invoices](https://docs.recurly.com/docs/calendar-billing#section-aggregate-invoices), charges from both child and parent accounts are merged into a single invoice. This is provided the child accounts are set to bill to the parent account and all [required conditions](https://docs.recurly.com/docs/calendar-billing#eligible-subscriptions) are met.

  - [Calendar Billing - Alignment](https://docs.recurly.com/docs/calendar-billing#alignment) allows for the automatic alignment of billing dates across a hierarchy of accounts to match the billing date of the common parent account.

  #### One-time charges

  - Any one-time charges on an account (whether parent or child) will be included in the consolidated invoice if they are present before the invoicing event. This includes recurring charges, as long as there is no shipping address associated. One-time charges requiring immediate billing will be invoiced separately.

  ## Interface updates

  #### PDF and Emails

  - Invoice-related emails will now include charges from multiple accounts within a hierarchy in the HTML/Text invoice display. Charges will be listed collectively, not by the originating account. However, email templates can be customized to include account information for each line item.

  - Invoice PDFs will similarly reflect the amalgamation of charges from multiple accounts. Here, the charges will be categorized by their originating accounts and will include relevant account details (such as Account Code).

  > 📘 Important!
  > 
  > The Admin Console, Hosted Invoice display, and PDFs will show only the first 500 line items, but the subtotal, tax, and total will accurately represent all items. To access details of line items beyond the initial 500, use the Adjustments Export.

  #### Recurly admin and hosted invoices

  - The Recurly Admin UI and hosted invoice page will display consolidated invoices, mirroring the format of the PDFs.

  #### API Support

  - Charges are retrievable via the Recurly API v3 through the <a href="https://developers.recurly.com/api/v2021-02-25/index.html#tag/invoice" target="_blank">invoices</a> or <a href="https://developers.recurly.com/api/v2021-02-25/index.html#tag/line_item" target="_blank">line items</a> endpoints. The data includes which account the charges were billed from and to (e.g., parent or child). Recurly API v2 continues to be supported.

# Instructions for use

## Implementing calendar billing with aggregate invoices

A feature known as Account Hierarchy - Invoice Rollup has been introduced. To utilize Account Hierarchy alongside Calendar Billing - Aggregate Invoices, this feature must be activated on your Recurly site. Please reach out to our <a href="https://support.recurly.com" target="_blank">support team</a> for activation.

Consider two child accounts, A and B, that are set to bill to a common parent account:

#### Combining recurring charges

1. On child account A, establish one or more subscriptions through the Recurly <a href="https://developers.recurly.com/api/v2021-02-25/index.html#tag/purchase" target="_blank">Purchase</a> or <a href="https://developers.recurly.com/api/v2021-02-25/index.html#operation/create_subscription" target="_blank">New Subscription</a> endpoints. You may also set up a subscription directly via the Recurly UI.

2. On child account B, initiate one or more subscriptions with the same exact billing date as those on child account A.

3. At the time of the invoicing event (when the common billing date arrives), the recurring charges from subscriptions on both child accounts will be billed together. You will notice:

- A PDF of the collective invoice, itemizing charges by originating account along with details such as account code, name, and company, should these details be provided on the Account. This PDF can be found attached to invoicing emails, as well as on the hosted pages and Invoice details page in the Recurly Admin UI.

- Use Recurly API v3 or v2 to review the comprehensive invoice and its individual line items.

**Note:** _Subscriptions on the parent account can be synchronized with those on child accounts, allowing the parent's charges to be incorporated into the collective invoice._

#### Combining recurring and one-time charges

1. On Child Account A, add a one-time charge scheduled for the next billing cycle (avoid immediate billing).

2. Follow the initial two steps outlined under "Consolidation of recurring charges."

3. At the invoicing event, the one-time charge from Child Account A will be combined with the recurring charges as described previously.

#### Creative configurations

Explore the flexibility of this system by creating different 'billing groups' within your Account Hierarchy. For example, you might arrange for Child Accounts A and B to be billed on one date, while the Parent and Child Accounts C and D are billed on another, resulting in two distinct batches of collective invoices.

## Guidelines for calendar billing - alignment

Utilize Account Hierarchy with [Calendar Billing - Alignment](https://docs.recurly.com/docs/calendar-billing#alignment) to automate alignment of subscription billing dates. To enable the **Account Hierarchy - Alignment** feature, please contact [support](https://support.recurly.com).

#### Account billing date

With Calendar Billing - Alignment and Account Hierarchy combined, a parent account's billing date synchronizes the billing dates of subscriptions on its child accounts, assuming the child accounts bill to the parent. If a child bills independently, it will align with its own billing date. The determination of the parent account's billing date follows this principle and may be set based on the activity of its child accounts or the [standard alignment logic](https://docs.recurly.com/docs/calendar-billing#aligning-logic).

## Taxation

The default setting taxes all items on a consolidated invoice according to the parent account's [taxable address](https://docs.recurly.com/docs/tax#taxable-address). To tax a child account's line items based on its specific address, enable the new setting provided. Absent an address for the child account, the system defaults to the parent's taxable address.

> 📘 Note on Shipping Addresses
> 
> Currently, shipping addresses are not compatible with Account Hierarchy Invoice Consolidation. Charges linked to a shipping address will be billed separately or at the next qualifying event.

## Coupons

Apply coupons to child accounts or their subscriptions following the usual coupon guidelines. Discounts from coupons will apply only to the charges from the associated child account.

## Credits

The [standard credit rules](https://docs.recurly.com/docs/account-hierarchy-1#credit-invoices) associated with [Account Hierarchy](https://docs.recurly.com/docs/account-hierarchy-1) are in effect. Credits are applied to the entire invoice rather than to individual items. Only credits on the parent account are eligible for use.

## Refunds

All forms of refunds are compatible with this system.

## Gift card redemptions

Gift card redemptions adhere to the [standard procedures](https://docs.recurly.com/docs/gift-cards).

## Invoice presentation

Invoices within an Account Hierarchy will label the parent account as "Primary Account" and child accounts as "Linked Account." This naming is consistent across the invoice PDF in customer emails, the Hosted Account Management invoice view, and the Recurly App Admin UI.