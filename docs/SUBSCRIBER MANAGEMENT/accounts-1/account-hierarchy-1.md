---
title: Account hierarchy
excerpt: >-
  Harness the power of structured relationships with Recurly's Account Hierarchy
  feature. Manage parent-child account relationships, streamline billing
  processes, and enhance customer experience with ease.
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

This feature is only available on advanced plans. If you’re currently on Pro or Starter, you may need to upgrade your plan to access it. Please contact [Recurly Sales](https://recurly.com/demo/contact-sales/) for more information.

# Definition

Account Hierarchy is a feature in Recurly that allows businesses to establish and manage parent-child relationships between accounts. It provides flexibility in billing processes by allowing either the parent or child account to be responsible for charges. This feature is particularly useful for businesses that have B2B customers with multiple divisions, departments, or subsidiaries.

# Key benefits

* **Streamlined billing:** Assign billing responsibilities to either the parent or child account, providing flexibility and simplifying the billing process.
* **Enhanced customer experience:** Enable a more personalized customer experience by tailoring communication and services to individual child accounts.
* **Efficient management:** Easily manage parent-child relationships through the API or Admin UI, allowing for seamless changes to account structures.
* **Improved tracking:** Track data around parent-child accounts and associated charges with enhanced export features.
* **Flexible subscription management:** Handle subscription changes, upgrades, downgrades, and terminations across parent-child accounts with ease.

# Getting started

Every customer account on your Recurly site can be designated as a parent or a child account. You can establish these relationships through the Admin UI or the API. This guide will focus on the Admin UI.

# Assigning a parent account

To assign a parent account via the UI, follow these steps during account creation or when editing an existing account:

1. Log into your Recurly account.
2. Navigate to the Customers, then Accounts section.
3. Create a new account or edit an existing account.
4. Navigate to the Account Hierarchy section.
5. Enter the parent account's code (or name).
6. Select the billing configuration (either Child or Parent's account).

<Image align="center" className="border" border={true} src="https://files.readme.io/e433c14-Screen_Shot_2018-10-09_at_3.29.46_PM.png" />

Please note, a child account (i.e., an account that already has a parent) cannot be assigned as a parent to another account. Child accounts will not appear in the dropdown menu and cannot be assigned as parents via the API.

<Image align="center" className="border" border={true} src="https://files.readme.io/6f00e24-Screen_Shot_2019-01-02_at_11.17.04_AM.png" />

In terms of hierarchy levels, a child account can only have one parent assigned to it. For example, a child cannot have both a parent and a grandparent.

# Editing account hierarchy

To modify the hierarchy of existing accounts:

1. Access the account you want to designate as a child.
2. In the Account Information box on the right side of the page, click the Edit hyperlink.
3. Scroll down to the Account Hierarchy section.
4. Search for or select the account you want to designate as the parent.
5. Select the billing configuration (either Child or Parent's account).
6. Click the Save Changes button.

<Image align="center" className="border" border={true} src="https://files.readme.io/8b17783-Screen_Shot_2020-08-24_at_11.10.48_AM.png" />

Upon completion, you'll be redirected back to the account page, confirming the successful addition of the account hierarchy link.

<Image align="center" className="border" border={true} src="https://files.readme.io/6c72d9f-Screen_Shot_2020-08-24_at_11.11.07_AM.png" />

# Configuring billing

After designating a parent account, you must decide where all charges should be billed. By default, all charges for a child account will be billed to itself. Alternatively, you can choose to bill all charges to the Parent Account. This is common in businesses where a parent organization manages finances for multiple subsidiaries.

For instance, if Pizza Planet headquarters (parent account) owns multiple pizza parlors (child accounts), and a child account is configured to *Bill All Charges to: Parent Account*, all charges will be billed to Pizza Planet Headquarters.

<Image align="center" className="border" border={true} src="https://files.readme.io/23498e6-Screen_Shot_2019-01-02_at_11.17.42_AM.png" />

# Viewing account hierarchy

After saving a new child account or updating an existing account with a parent, you can view the relevant Account Hierarchy information from both the child and parent accounts.

## Child account information

When viewing a child account, the Account Information includes a "Child" tag. This section also includes the Parent Account name and a link to the parent account, as well as a link to View Account Hierarchy, which provides an overview of all child accounts, subscriptions, and invoices.

<Image align="center" className="border" border={true} src="https://files.readme.io/d6ab978-Screen_Shot_2019-01-02_at_11.20.40_AM.png" />

## Parent account information

When viewing a parent account, the Account Information includes a "Parent" tag. This section also lists the number of child accounts associated with this parent account and provides a link to the Account Hierarchy overview page.

<Image align="center" className="border" width="25% " border={true} src="https://files.readme.io/980d06a-Screen_Shot_2019-01-02_at_11.21.34_AM.png" />

# Account hierarchy overview page

Accessible from either the child's or parent's account information, this page includes several index pages:

* **Accounts**: Lists all child accounts associated with the parent account.
* **Subscriptions**: Lists all subscriptions belonging to the parent's associated child accounts.
* **Invoices**: Lists all invoices belonging to the parent and its associated child accounts.

<Image align="center" className="border" width="75% " border={true} src="https://files.readme.io/85f50eb-Screen_Shot_2019-01-02_at_11.52.07_AM.png" />

You can filter accounts, subscriptions, and invoices based on whether they are billed to a child account or a parent account.

# Billing configuration

Recurly handles invoice and billing events differently depending on whether a child account is configured to bill charges to itself or to a parent.

# Child account that bills to itself

When a child account is configured to manage its own billing information and responsibilities, it behaves like a regular customer account in Recurly, with the primary difference being its association with a parent account. This association is reflected in the Overview Page in the Admin UI and in our Exports for your convenience.

# Child account that bills to parent

A child account can be configured such that all payment information, invoices, charges, and credits belong to the parent. In this setup, all invoices are owned by the parent account and reside on the parent account. By default, all charges originating from the child account will use the billing information on the parent account. With this configuration, a child account does not need to have billing information on its account for subscriptions or charges to be created.

> 📘 Adding billing information for a child
>
> A child account that bills to a parent can also have its own billing information. However, this information will not be used for any charges for the child account. In some cases, you may want to add billing information to a child account if a parent is going to be removed from the account. By doing so, any active subscriptions can be renewed using this billing information after the parent is removed.

## Adding a subscription

When adding a subscription for a child, the subscription will be created on the child account. If the subscription is created immediately, the invoice will be created on the parent account. For example, if you are viewing the child account details, you will see the subscription on the account but the invoice will not be listed on the Charges & Credits table. To access the invoice, you will need to go to the Subscription Details to access a link to the invoice.

<Image align="center" className="border" width="65% " border={true} src="https://files.readme.io/c683a70-Screen_Shot_2018-10-11_at_11.05.17_AM.png" />

### Subscription changes

During immediate subscription changes that result in an invoicing event, an invoice will be created on the parent account. Immediate subscription changes *can* result in a charge invoice and a credit invoice. If a subscription change results in a charge invoice and a credit invoice for the child exists on the parent account, it will be applied on the charge invoice. For example, if a child account has a subscription downgrade that results in a credit invoice on its parent, if a new subscription is added to the child account a credit invoice from the downgrade will be applied to the charge invoice for the new subscription.

## Adding a charge or credit

Posting custom charges or credits to the child account will immediately post an invoice to the parent account.

#### Invoice immediately

If you are adding a charge that "Invoices Now", the invoice will be created immediately. The charge will not be available on the child's Charges & Credits table on their account. You will be able to access the invoice from the parent account's Invoices table or Charges & Credits table.

Posting a custom credit from the child account will create a credit invoice immediately on the parent account. The credit invoice will reside on the parent account under the Charges & Credits table.

<Image align="center" src="https://files.readme.io/d62db59-Screen_Shot_2018-10-11_at_12.37.22_PM.png" />

> 🚧 Using the API for transactions
>
> Currently, we do not *fully* support the [transactions endpoint](https://dev.recurly.com/docs/create-transaction) in the API for custom charges that invoice immediately for Account Hierarchy. While it is possible to create a transaction for a child account that bills to itself, it is not supported for a child account that bills to a parent. We recommend that if you want to create one-time charges for a child account whose bill-to-account is a parent, you create them using the Admin UI or the [purchase endpoint](https://developers.recurly.com/api/latest.html#operation/create_purchase) in the API.

#### Invoice at next bill date

Recurly allows creating custom charges through the Admin UI that can be invoiced at the next bill date. We also allow you to do this through the API using the adjustments API endpoint.

If you are creating a custom charge that invoices at the next bill date, the uninvoiced charge will reside on the child account under the Charges & Credits table until it is invoiced. This means that if you are looking at the Adjustments - Export filtered by uninvoiced adjustments, the Account column will list the account code of the child associated with the uninvoiced adjustment.

<Image align="center" width="65% " src="https://files.readme.io/a3d4ac6-Screen_Shot_2018-10-11_at_12.51.49_PM.png" />

Uninvoiced charges are picked up in any billing event (adding a subscription, renewing a subscription, posting a charge), except for immediate subscription changes. Once the uninvoiced charge is invoiced, the charge will be moved from the child account Charges & Credits table to the parent account's Charges & Credits table. Additionally, the Adjustments - Export will reflect the parent under the Account column for the invoiced adjustment. If the parent payment method is declined at the time the uninvoiced charge is invoiced, the charge invoice will still be generated on the parent account and marked as failed.

## Credit invoices

Credit invoices created manually or as a result of a subscription change, will be created on the parent account if the child bills to the parent. Credit invoices will be applied towards any charge invoice originating from any child.

#### Example

A child company called Pizza Planet-Oakland bills to a parent company Pizza Planet - Headquarters. A custom credit invoice is created for Pizza Planet-Oakland that is issued to the parent account. Pizza Planet - San Francisco is a sibling to child company Pizza Planet-Oakland and also bills to the parent company. If a subscription is added to Pizza Planet-San Francisco, the credit invoice originating from *Pizza Planet-Oakland* will be applied to the charge invoice billed to Pizza Planet-Headquarters.

Credit invoices created as a result of creating a custom credit on a *parent account* or originating from a subscription change or refund *for a parent* that may *also* have a subscription, will apply towards any charge invoices created from the parent's children that bill to it. This means that a single credit invoice can be applied across multiple children until the credit is used up entirely.

## Coupons

Coupons can be redeemed in a number of ways. You can redeem individual coupons via the Admin UI to a child account or when adding a subscription to a child account. You can also redeem coupons via the API. In order for discounts to apply towards an invoice to a parent, the coupon must live on the child account. For example, a subscription is created on a child account and the child account has an eligible account-level coupon on its account. This coupon will be applied towards the eligible charge(s) on the invoice billed to its parent.

Coupons that are redeemed on a parent account will not be applied towards invoices created as a result of a child billing to its parent. If a parent has a coupon(s) on its account, they will only apply to subscriptions or charges created on the parent account *for* the parent (e.g if a parent has its own subscription).

Coupon application rules are the same as existing coupon logic outlined [here](https://docs.recurly.com/v1.0/docs/coupons#section-coupon-accounting).

## Refunds

Invoice refunds for an invoice on a parent account will create a refund credit invoice on the parent account, which includes credit line items against previously paid for charge line items. Refunding will never reopen the original charge invoice. When refunding an invoice directly, you can choose to distribute the resulting credit balance as a payment refund (cash back on the parent's payment method), or leave it as a credit balance to be used as payment on future invoices.

For more information on how refunds work, visit this [page](https://docs.recurly.com/v1.0/docs/invoices#section-refunds).

## Taxes

If you are using Recurly taxes, line items on an invoice billed to a parent, will be taxed based on the parent's taxable address.

#### Collection method

When **automatic collection** method is used, the invoice line items will be taxed based on the parent's billing information address unless your site settings specify to use account address. If the latter is true, tax will be calculated based on the parent's account information address. If **manual collection** method is used, the invoice line items will be taxed using the parent's account information address.

#### Tax exempt

If you are utilizing our [tax exemption](https://docs.recurly.com/v1.0/docs/tax#section-exempt-customers) feature, the following rules will apply to account hierarchy accounts:

* if a parent is tax exempt, all parent’s invoices (e.g child that bill to parent invoices and the parent's own invoices if they have their own subscription) will not be taxed
* If a child is tax exempt but the parent is not, the invoices generated for this child will not be taxed.

> 📘 Displaying Child Information on Invoice
>
> If you would like to include information (such as name and address) on the invoice to the parent account, you will want to ensure that you pass in a shipping address when creating a subscription. The resulting invoice should display a Bill To address based on the parent's billing information and a Ship To address of the child's shipping address. Additionally, passing in a shipping address will ensure that the invoice is taxed based on the location of the child account. 
>
> Refer to the Shipping section below for more information.

#### Shipping address

In some cases, you may want to use tax line items on an invoice based on the location of the child account. We recommend that for this use case, to specify a shipping address for the child account's subscription. The resulting invoice should display a Bill To address based on the parent's billing information and a Ship To address of the child's shipping address.

<Image align="center" className="border" width="75% " border={true} src="https://files.readme.io/e6cffc2-Screen_Shot_2019-01-03_at_12.26.03_PM.png" />

There are a couple of ways to apply a shipping address to a subscription, which is outlined in our existing [shipping address documentation](https://docs.recurly.com/v1.0/docs/shipping-addresses).

If you are using the [purchase endpoint in our API](https://docs.recurly.com/v1.0/docs/shipping-address-per-line-item) to create subscriptions and custom charges and also want to use a child's shipping address for taxation, we recommend that you specify an account-level shipping address for the purchase. This means that all line items will be based on the account-level shipping address. Any new subscription(s) created will be associated with this shipping address.

#### VAT reverse charge notes

If you are using Recurly's [EU VAT feature](https://docs.recurly.com/v1.0/docs/eu-vat-2015), and the taxable address for parent invoice is based in the EU and is a different country than that of your business and VAT number, then VAT Reverse charges will be included on the invoice.

#### Tax location validation

Recurly's [Tax Location Validation](https://docs.recurly.com/v1.0/docs/tax-location-validation) service is used at the time any account's taxable address is added to, or updated on, the account. For example, if a parent account's billing information address or account address was updated, at the time of invoicing, Recurly will check the status of the parent account and allow the invoice to be posted if the parent account is valid and blocks the invoice if the parent account is invalid.

Note: If you are using the shipping address from the child account as the taxable address, Recurly will not validate the shipping address. This means that Recurly will only evaluate a parent account's location evidence.

## View invoice

The display on customer invoices that are in an Account Hierarchy reads as: "Primary Account" for the parent, and "Linked Account" for the child. The invoice locations where this naming convention will display includes the invoice PDF in customer emails, Hosted Account Management invoice display, and the Recurly App Admin UI.

<Image align="center" className="border" width="65% " border={true} src="https://files.readme.io/eed8019-Screen_Shot_2018-10-11_at_2.52.16_PM.png" />

## Updating or removing billing information

If you are changing billing information or removing billing information for the *parent* account, this will directly impact any children that bill to this parent. If you remove a parent account's billing information, any non-trial subscriptions for those children that bill to the parent will expire at the next bill date. Trial subscriptions will expire when trial ends, if no payment method is added to the parent account. If billing information is updated, the updated payment method will be used for any charges originating from a child that bills to the parent account.

Adding or removing billing information for a *child account* that bills to a parent, has no impact on subscriptions being purchased or renewed. However, if you are planning to remove a parent from a child account, we recommend adding a payment method to the child account so that subscriptions are able to renew after the parent account (and therefore means of payment) is removed.

## Dunning

If you are utilizing [Recurly's Dunning Management](https://docs.recurly.com/v1.0/docs/dunning-management), dunning notifications will be sent to the parent account when invoices move to past due, since the parent account is the invoice owner for children that bill to a parent.

# Emails

When using Recurly automatic emails in conjunction with Account Hierarchy, the recipient of the emails (parent or child) depends on the configuration of the billing responsibilities for the child account.

#### Child that bills to itself

If a child account is set to bill to itself and not pass charges to its parent, any enabled email template will dispatch an email to the child account's email address.

#### Child that bills to parent

For child accounts configured to bill to their parent, it's crucial that only the parent receives email notifications containing invoice information. 

The following emails, if enabled, will be dispatched to the parent account's email address, representing events originating from the child that bills to the parent:

* Invoice (New Invoice, New Credit Invoice, Payment Confirmation, Payment Refunded)
* Subscription (New Subscription, Subscription Change, Subscription Canceled, Subscription Expired, Expired for Non-Payment, Trial Ending, Renewal Reminder, SEPA, CC Expired)
* Dunning emails

If a parent or child is permitted to log into their account via Hosted Account Management, Recurly will dispatch all Account emails to the email address of the account initiating the change. 

For instance, if a child account accesses your hosted account management login page and requests account activation, Recurly will send an email to the child account. Likewise, if a parent account requests account activation, Recurly will send an email to the parent account. Furthermore, if a child or a parent requests a Password Reset, the requesting account will receive the email to reset the password. If the password is reset, the account will also receive the 'Password Has Been Reset' success email.

# Modifying parent-child relationships

You can remove or change a parent for a child either through the API or the Admin UI. 

## Removing a parent

When detaching a parent from a child account, bear in mind that subscriptions on the child account may expire at the next bill date, unless a valid payment method is added to the account. You can remove the parent account in the same manner as changing the parent, by editing the child account and selecting the 'Remove Parent' option before saving the change.

<Image align="center" className="border" width="75% " border={true} src="https://files.readme.io/e7c545da22a38b300f7c8d4c53ea3b81f48e56e7ef73105d2f6d4082ab574aae-Screenshot_2025-01-16_at_11.52.49_AM.png" />

Upon removal of a parent account, the child account effectively becomes independent. This implies that all charges and subscriptions will be billed using the billing information on the account. If the account had existing billing information (child billing information that existed while it was a child), any active subscriptions will attempt to renew at the next bill date using this billing information. If the billing process fails, active subscriptions will undergo the standard dunning process.

Moving forward, the account will no longer appear in the Account Hierarchy Overview page nor be included in the count of children for that parent. The Accounts - Export will also indicate that the account has been modified and no longer has a parent account associated with it. 

## Changing a parent

When a parent account is replaced for a child, the child account will lose its association with the previous parent. Changes to the parent of an account cannot be made if there are outstanding invoices. This ensures that the account is in good standing (invoices paid, refunds issued to old parent if necessary) before altering the billing owner of the child. The child will be included in the count of children for the new parent and in the Account Hierarchy Overview page for the new parent and its children. The Accounts - Export will also indicate that the account has been modified and has a new parent account associated with it. 

If the child account is set to bill to the parent, any charge or credit invoices will be created on the parent account. Charge invoices will be billed using the new parent account's billing information.

> 🚧 Subscriptions with usage based billing
>
> If a child account has an active subscription that is billed using [usage based billing](https://docs.recurly.com/v1.0/docs/usage-based-billing) and you change the bill-to-account (e.g., previously billed to Parent A and now bills to Parent B) in the middle of the current billing cycle, there are a few things to note if you decide to do so:
>
> * Any unbilled usage will be billed to the *new* parent at the next bill date. 
> * Terminating the subscription in the middle of the current billing cycle will result in an invoice to the *previous* parent for any unbilled usage. 
>
> If you do not want the previous parent to be invoiced for unbilled usage when terminating the subscription mid-cycle, we recommend that you [zero-out](https://docs.recurly.com/v1.0/docs/usage-based-billing#section-cancel-or-terminate-a-usage-based-subscription) the usage prior to termination.

### Subscription changes if bill-to-account is different

When adding, changing, or removing a parent from an account, it's crucial to understand how this will impact any existing subscriptions and/or past invoices on the affected account. Specifically, how an existing subscription(s) is invoiced if a subscription change is made during the middle of the billing cycle. 

If any subscription changes are applied [effective immediately](https://docs.recurly.com/v1.0/docs/change-subscription#section-timing-of-change), and are made to a subscription where the account that paid the most recent invoice for the subscription doesn't match the current billing account, any change will trigger a full prorated credit against the old account, and a new prorated charge against the new bill-to-account. In other words, if you upgrade or downgrade the subscription prior to the next bill date after changing the ***bill to*** account, the *new* bill-to-account is responsible for paying for the *full prorated amount* of the updated subscription for the remainder of the billing cycle, not just the *difference* between the old subscription price and the new subscription price.

Having a different original billing owner can occur in 3 ways:

* Adding a parent to an existing account with an active subscription 
* Changing a parent of a child with an active subscription
* Removing a parent of a child with an active subscription 

#### Upgrading subscription if billing account has changed since last recent invoice

Suppose a child is subscribed to a monthly Silver subscription which is billed to Parent A. During the middle of the monthly billing period, the child's parent bill-to-account is changed to Parent B. Later, the subscription is upgraded to Gold with the timing of change effective immediately. Parent A will receive a credit for the remaining time to Gold. Parent B will receive a full rebill of the subscription to Gold.

#### Downgrading subscription if billing account has changed since last recent invoice

Suppose a child is subscribed to a monthly Gold subscription which is billed to Parent A. During the middle of the monthly billing period, the child's parent bill-to-account is changed to Parent B. The subscription is later immediately downgraded to Silver. Parent A will receive a credit for the remaining time to Gold. Parent B will receive a full rebill of the subscription to Silver. 

#### Removing a parent of child with an active subscription

If a parent is removed from an account that bills to a parent and there are any active subscriptions on the account, an immediate downgrade will issue a credit invoice to the original parent account. Any immediate upgrades will result in a charge invoice to the account if there is valid billing information available. 

> 📘 Refunding invoice if billing account has changed
>
> If an account has invoices and subscriptions that were previously paid for by a different account (e.g., a parent or different parent from the one it has now), those invoices will be refunded to the original account that paid for them. For example, Child A has an active subscription paid for by Parent A, but Parent A is removed. If you wish to refund any invoices *that were issued* prior to Parent A being removed, you can go to Parent A's account to refund any invoices associated with Child A. Those will be refunded to Parent A's payment method used for those transactions.

# Closing a child or parent account

If you need to **close a child account**, you must conclude any outstanding business with that child account (e.g., close any past due invoices) before you can close the account. Upon closing the child account, any billing information on the account will be removed. Active subscriptions for that child will be canceled and expire at the next bill date. The child account will maintain its relationship with the parent account, unless the parent is removed from the child. 

In the event that a *parent account* needs to be closed (e.g., the parent no longer requires a subscription to your service for its children or the business is shutting down), you must close all child accounts for this parent first or remove the parent from the child. As best practice, you should ensure that each child account has all invoices paid and/or any refunds issued prior to closing the child account. Once all child accounts have been closed, you can close the parent account. Once the parent account is closed, billing information will be removed and if the parent has any active subscriptions, they will be canceled and expire at the next bill date. The parent account will maintain its relationship with the child accounts. Reopening the parent account will *not* automatically reopen the child accounts.

> 🚧 Reopening a child account
>
> If you want to reopen a child account whose parent account is *closed*, reopening the child account will effectively sever the parent relationship. We recommend that if you want to reopen the child account and maintain the parent, that you reopen the parent account first. 
>
> However, if a child's parent is still *active*, reopening the child account will maintain the parent-child relationship.

# Hosted account management

If you are using Recurly's [Hosted Account Management](https://docs.recurly.com/v1.0/docs/hosted-account-management) and you plan to allow parents and children with Account Login access, there are some differences between HAM and  the Admin UI. Hosted Account Management pages do not include any labels denoting whether the account is a parent or a child. 

#### Parent account

When a parent logs into their account, they will be able to view any subscriptions (if the parent is subscribed to a plan) belonging to itself and any invoices created as a result of a child billing to the parent. In most cases, a parent will not have a subscription of their own, therefore a parent would only see invoices originating from a child that billed to it. If a parent updates their payment method, any child that currently bills to the parent, will use the updated billing information. 

#### Child account that bills to parent

When a child that bills to its parent logs into their account page, they will not be able to access any price or invoice information, unless the invoices were created prior to the child account billing to its parent. 

For example, on a regular account in Hosted Account Management,  we display both an invoice link and pricing information for each subscription within the Subscription card. We also include a table of invoices created for that account. For Account Hierarchy, a child that bills to a parent will not have access to invoice or pricing information. This is due to the fact that the parent is the owner of the invoice and payment information. A child cannot view any parent information from the child account page. 

If a child account that bills to its parent, eventually has its parent removed, any invoices belonging to the parent account that were associated with the child will remain on the parent account. 

#### Child account that bills to self

When a child that bills to itself (e.g., uses its own payment method and does not use the parent account) logs into their account, they will be able to view all of their subscriptions and any invoices created for that child account. A child cannot view any parent information from the child account page. 

If a child account is updated to "bill to parent", any invoices created using the parent's billing information will be created on the parent account and not accessible from the child hosted account page. Similarly, invoice and pricing information will not be displayed for any new subscriptions or invoices created for the child account.

#### Child account's parent removed

If the parent is removed and the account is no longer a child, the account will reset to be its own billing owner and the invoices table should be present again.  Any invoices that were created for the account when it previously billed to its parent will not be displayed on the account however, and continue to live on the parent account.

# Exports

To facilitate the tracking of data around your parent-child accounts and the associated parent-child accounts to a charge, we've introduced several enhancements to Exports. 

## Accounts export

We've added a new column to the Accounts export to identify a parent account associated with an account. An account can be identified as a child if there is a parent account code populated in the new parent\_account\_code column. This feature is available in version v3 of the Accounts Export.

| Column Name           | Example                                                | Description                                                                                                                              |
| :-------------------- | :----------------------------------------------------- | :--------------------------------------------------------------------------------------------------------------------------------------- |
| parent\_account\_code | 123456789, [parent@gmail.com](mailto:parent@gmail.com) | When an account has a parent (i.e., is a child), the account code of the parent for this child account will be populated in this column. |
