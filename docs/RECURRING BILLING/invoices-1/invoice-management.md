---
title: Invoice management
excerpt: >-
  Effortlessly manage and customize invoices with Recurly's comprehensive
  invoice management features, ensuring clear, compliant invoices  tailored to
  your business needs.
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

### Limitations

* Invoice number customization and prefix addition may require support assistance.
* Certain invoice display customizations might not be supported in all configurations.

# Definition

Recurly's invoice management system provides tools for generating, tracking, and customizing invoices to automate the billing process. It records transactions, including sales, renewals, and refunds, clearly detailing services or products provided and the costs involved. The system supports customizable invoice numbering and includes features to identify the transaction origins, aiding in financial reporting and compliance. Designed for clarity and accuracy, it simplifies managing financial transactions between a business and its customers.

## Key benefits

* **Detailed transaction records:** Invoices in Recurly provide a full breakdown of transactions, including origins, amounts, and associated customer details, enhancing transparency and trust.
* **Customizable numbering and sequencing:** Tailor invoice numbering to start from a specific number or add prefixes for better organization and identification, especially useful for businesses operating in multiple markets or with varied product lines.
* **Comprehensive display options:** Customize the invoice display to include essential business and customer information, ensuring invoices are informative, compliant, and aligned with your brand.

## Numbering

All invoices on your Recurly site, both charge and credit, follow the same invoice number sequence. This sequence starts at 1000 and increments by 1.

### Considerations

Invoice numbers are often used in reconciliation of invoices and transactions.  This should be considered when adding an entity specific prefix.  Gateways handle the information sent differently, including length of these invoice numbers.

Invoice numbering customization options are detailed below:

### Invoice Number Settings: Entity Prefix

Customize invoice numbering to reflect the appropriate entity for your business requirements.

Recurly enables the addition of an invoice number prefix to be added to invoice numbers. The prefix is an alphanumeric that is prepended to the sequential number.  When adding an entity prefix, the sequence will start at 1000 and increment by 1.

An entity prefix will continue to support country-specific sequencing for countries in the EU for each sequence/prefix.

An invoice number prefix can be added per Business Entity, go to Business Entity > Invoice Settings: Invoice Number Settings: Entity Prefix.

For more information on configuring prefixes, visit [Business Entity Invoice Settings](https://docs.recurly.com/recurly-subscriptions/docs/business-entities#invoice-settings).

### Invoice Number Settings: EU Country-specific numbering

For a separate invoice sequence for each European Union country, you can activate the Country Invoice Sequencing feature in Recurly. Go to Business Entity > Invoice Settings: Invoice Settings, find "Country Sequencing", and enable "Country Invoice Sequencing".

For more detailed information, visit [EU Country Sequencing](https://docs.recurly.com/recurly-subscriptions/docs/eu-vat-2015#invoice-sequencing-by-country) For more information on configuration, visit [Business Entity Invoice Settings](https://docs.recurly.com/recurly-subscriptions/docs/business-entities#invoice-settings).

### Order Number Prefix

Recurly enables the addition of a hidden prefix to your invoice numbering. This is particularly helpful if you use the same payment gateway for multiple billing systems and need to segment your transactions. The order number prefix will not appear on invoices.  The order number prefix is not configured per business entity.

To add a hidden prefix, go to Configuration > Site Settings and enter your desired prefix under "Order Number Prefix".

!\[Order Number Prefix] ([https://drive.google.com/file/d/1MypjSoH13qtFnX4YExAchLZ\_yQ3oDV2f/view?usp=drive\_link](https://drive.google.com/file/d/1MypjSoH13qtFnX4YExAchLZ_yQ3oDV2f/view?usp=drive_link) "Order Number Prefix")

### Customize initial number

If you prefer to start your invoice numbering at a different number other than 1000, you can reach out to Recurly Support. Contact them through this link: [Recurly Support](https://support.recurly.com/)

## Display

The display of invoices in the Recurly Admin Console, Hosted Invoice, or as a PDF includes the following elements:

### Number and collection

* **Invoice number & posting date:** Every invoice displays its number and the date it was posted.
* **Charge Invoices:** These will additionally show a term option and due date.
* **Credit Invoices:** If issued against a charge invoice, the relevant charge invoice number(s) will be listed.
* **Visualization:** Invoice numbers may include prefixes or country codes as configured in Business Entities. The following visualization is an example of what invoice number sequencing looks like with multiple business entities.

![](https://files.readme.io/de8c42f72668ee9f22b1eed749ff5993d5922ceab201d0df15cd5eb926bb0c1a-image.png)

<br />

### From address

Located at the top left of the invoice, this section lists your company's information as provided in Site Settings under Configuration in the Admin Console. It includes:

* Company Name
* Address (Address 1 and Address 2)
* City
* State/Province
* Zip/Postal Code
* Country
* Phone Number
* Billing Contact Email
* VAT Number
* Registration Number

### Bill to

Every invoice includes a Bill To address for the customer:

* Defaults to Billing Information for automatic collection methods or Account Information for manual methods.
* Can be configured to always use Account Information (with Billing Information as fallback) by enabling "Use Account Information Address for all Invoices" under Configuration > Taxes > Tax Settings.\
  Fields displayed in the Bill To section:
* First and Last Name
* Company Name (from Account Information)
* Address (Address 1 and Address 2)
* City
* State/Province
* Zip/Postal Code
* Country
* VAT Number

### Ship to

An invoice includes a Ship To address if a shipping address is associated with the subscription or specified for a line item:

* First and Last Name
* Address (Address 1 and Address 2)
* City
* State/Province
* Zip/Postal Code
* Country
* VAT Number\
  Learn more about [Shipping Addresses](https://docs.recurly.com/docs/shipping-addresses)

### Line items

Invoices contain a table of line items with these columns:

* Date
* Description
* Quantity
* Price
* Discount (shown only if applicable)
* Subtotal
* Tax (shown only if applicable, displaying the rate)
* Total (shown only if tax is applicable)

<br />

> **Note:** Invoices displayed via the Admin Console, Hosted Invoice, and PDF will truncate line items after the first 500. The subtotal, tax, and total will reflect the sum of all line items. To access line items beyond the first 500, use the [Adjustments Export](https://docs.recurly.com/docs/adjustments-exports)

### Total and balance

At the bottom right of the invoice, the following invoice-level values are displayed:

* **Subtotal:** The total before taxes and additional charges.
* **Tax:** Shown only if tax is applicable to the invoice.
* **Total:** The invoice total, inclusive of all charges and taxes.
* **Balance:** The remaining amount due on the invoice.\
  Between the Total and Balance, the following balance-changing entries are listed:
* **Paid:** Represents the total of all payment transactions.
* **Credit Applied/Redeemed:** The total value of all credit payments applied to the invoice.
* **Payment Refund:** The total of all refund transactions made against the invoice.
* **Credit Voided:** Any portion of the credit balance that has been removed or voided.
* **Write-Off:** The amount of the invoice that has been written off.

### Quantity-based pricing line items

Recurly's invoice line items are structured differently based on the pricing model used, such as Tiered Volume and Stairstep. The first charge typically reflects the plan's base fee, followed by charges for Add-Ons determined by the chosen pricing model and quantity. For more information, refer to [Billing Models](https://docs.recurly.com/docs/billing-models#section-quantity-based).

#### Tiered pricing

* **Description:** For the Tiered model, each tier results in a separate line item.
* **Naming:** The Add-On name includes the range of units. Example: "Seats: 1-10".
* **Visualization:**

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/3dc4f14-Image_2020-03-20_at_8.53.19_AM.png" />

#### Volume pricing

* **Description:** Line items for Volume pricing are similar to those for fixed-price products, using the per-unit price from the relevant subscription tier.
* **Visualization:**

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/576c291-volume.png" />

#### Stairstep pricing

* **Description:** A single line item is created, displaying the Add-On name and purchased quantity. The charge quantity is set to 1, with the price reflecting the fixed price for the applicable tier.
* **Visualization:**

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/a983819-Image_2020-03-20_at_8.59.44_AM.png" />

### Payment history

The "Payments" section of the invoice display includes all transactions and credit payments that have reduced the invoice's balance. It details the date and amount of each payment.

### Notes

Invoices feature three types of notes sections, which are visible only if they contain text. These notes can have site-level default settings and can also be customized per invoice via the Admin Console or API. Set up site-level defaults on the [Invoice Settings](https://app.recurly.com/go/configuration/invoice_settings/edit) page.

#### Customer notes

* **Description:** A section for any customer-specific notes, such as special invoice details or a thank-you message.
* **Title Visibility:** The title of this section does not appear on the invoice.

#### Terms and conditions

* **Description:** A section for payment terms, legal notes, or other important information.
* **Title Visibility:** The title of this section is always visible and cannot be altered.

#### VAT reverse charge notes

* **Description:** Used for European Union reverse charge tax scenarios.
* **Configuration:** Set up on the Tax Settings page.\
  Learn more about [VAT Reverse Charge Notes](https://docs.recurly.com/docs/eu-vat-2015#section-eu-vat-registered-customers)

## PDFs

Enable PDF invoice attachments in email notifications by navigating to the Email Templates page in the Configuration section of Recurly App. From here, you can go into the "edit" view of any of the 7 email templates with invoices associated, select "Attach PDF" under "Attachments" and save your changes. PDFs of invoices can also be downloaded from the Admin Console or Hosted Pages.

Email Templates that support invoice PDF attachments:

* New Subscription
* New Invoice (Manual Invoice feature only)
* Invoice Past Due (Manual Invoice feature only)
* Payment Confirmation
* Payment Declined
* Payment Refunded
* Payment Voided

<Image align="center" width="75% " src="https://files.readme.io/142bd85-Screenshot_2024-08-05_at_9.21.28_AM.png" />

## Emails

* **Initial Subscription:** The first invoice is included in the "New Subscription" email.
* **Automatic Collection Invoices:** Subsequent invoices are sent using the "Payment Confirmation" email. Invoices with a $0.00 total are not sent.
* **Manual Collection Invoices:** These always trigger the "New Invoice" email template.
* **Resending Emails:** Invoice emails can be resent using the **Resend Last Email** button on an invoice. Enable PDF attachments for all invoice-related emails in the [Invoice Settings](https://app.recurly.com/go/configuration/invoice_settings/edit).

## Proration

The line items Recurly creates on an invoice are prorated in the event of an immediate subscription change and include the option for proration in an invoice refund. All proration calculations are down to the second, although the line item dates are listed by day. Learn more about [immediate subscription change proration](https://docs.recurly.com/docs/change-subscription#section-time-based-proration).

## Collection method

Recurly uses the collection method for charge invoices to determine whether to process payment immediately with the billing information on file or to merely issue the invoice. The collection method can be set at either the invoice level or the subscription level.

### Automatic collection

Posting an invoice with automatic collection instructs Recurly to attempt payment with the billing information on the account (e.g., credit card, bank account, PayPal, Amazon). For new subscriptions and the Purchases API endpoint, a successful transaction is required for the invoice to post. For renewals and the Post Invoice API endpoint, the invoice posts and processes the automatic payment respective of the invoice terms. If a decline is returned, the invoice enters the Past Due status and begins the dunning cycle.

### Manual collection

Posting an invoice with manual collection prompts Recurly to issue the invoice without attempting any payment. External payments can be manually entered later as a manual transaction, or customers can pay the invoice using an automatic method via our Make a Payment button on the hosted invoice.

> **Note:** Once a manual invoice is paid, or an attempt is made to pay it, with the billing information on the account, it converts to automatic collection. It is currently not possible to record a manual payment on an automatic collection invoice or convert a charge invoice from automatic to manual collection.

To manually record an external payment, view the invoice in the Admin Console and enter the payment details in the left sidebar. A manually paid invoice can be reopened.

* Learn more about [manual collection](https://docs.recurly.com/docs/manual-payments).
* Learn more about our [Make a Payment option](https://docs.recurly.com/docs/hosted-account-management#section-online-payments).

### Modify subscription's collection method

Changing the subscription's collection method affects the collection method of the next charge invoice for that subscription. It does not alter the collection method of any already issued invoices for the subscription.

To change the collection method of a subscription, view the specific subscription in the Admin Console and select "Edit Subscription" from the Subscription Actions dropdown at the top right. Scroll down to the "Invoicing" section on the Edit Subscription page and select the new value in the Collection Method dropdown. Save your changes. Note that changing the collection method applies immediately, regardless of whether "On next renewal" is selected under Plan Effective Date.

The "Dunning," "Stop Collection," "Refunds," "Testing," and "Account Hierarchy Invoice Display" sections are clear and well-structured. Here’s a review focusing on grammar and tone:

### Dunning

When an invoice enters a Past Due state, it initiates the dunning cycle. For automatic collection invoices, this occurs after the first transaction decline. For manual collection invoices, it starts 24 hours after the invoice's due date. Automatic and manual collection invoices each have distinct dunning cycles and associated email templates: "Payment Declined" for automatic and "Invoice Past Due" for manual collection. Within your dunning settings, you can choose to either fail the invoice at the end of the cycle or leave it past due. Note: With [Account Updater](https://docs.recurly.com/docs/account-updater) enabled, Recurly will continually run Account Updater on the associated account and attempt to collect payment indefinitely.

Learn more about [Dunning Management](https://docs.recurly.com/docs/dunning-management) and [Automated Transaction Retry Logic](https://docs.recurly.com/docs/retry-logic).

### Stop collection

To write off an unpaid invoice, use the **Stop Collection** option in the Invoice Actions dropdown on the invoice details page. This action changes the invoice state to Failed and removes the amount from the customer's account balance. With Credit Invoices enabled, failing an invoice creates a corresponding write-off credit invoice, balancing the failed invoice to zero. Stopping collection also halts the dunning cycle, including all automated emails and payment retries, as well as activities performed by Recurly's [Account Updater](https://docs.recurly.com/docs/account-updater).

Once failed, an invoice cannot be reopened. This applies to manual collection invoices due to the existence of the write-off credit invoice.

> **Note:** Failing an invoice does not automatically cancel the related subscription. To stop future billings, cancel the subscription separately.

## Refunds

Refunds are processed at the invoice level. Options include changing a subscription, refunding a specific invoice, or refunding the last invoice while terminating a subscription. These actions generate a refund credit invoice with credit line items against previously paid charge line items. Directly refunding an invoice allows you to distribute the credit as a payment refund or retain it as a credit balance for future invoices.

To refund an invoice, select "Refund Invoice" in the Invoice Actions dropdown in the Admin Console. Invoice refunds are also supported in both versions of Recurly's API.

Once you are on the Issue Refund page, you have a few options to choose how to handle your refund. You can issue your refund either by the line item level, or for the entire invoice.

> 🚧 Important Callout:
>
> Merchants ***without*** the "Only Bill What Changed" and "Credit Memos" feature flags enabled on their site only have the option the to refund by "Quantity" for line items, and by "Specific Amounts" for entire invoices. Refunding by percentages and specific amounts on line items, and percentages on entire invoices, is *not available* for merchants without the "Credit Memos" and "OBWC" features enabled.

**Select to refund by line item**:

<Image align="center" className="border" border={true} width="75% " src="https://files.readme.io/1d7bd0ff3a3c0d40d7baa51e77984d63c2a1b382e0913f5ea12724339d7e7566-Screenshot_2024-08-20_at_1.18.46_PM.png" />

**Select to refund by entire invoice:**

<Image align="center" className="border" border={true} width="75% " src="https://files.readme.io/155cce782e09c877c4053f44bd9913362ac7a89b8a9794883765198888a69af3-Screenshot_2024-08-20_at_1.27.12_PM.png" />

Refund options for issuing refunds by individual line items include refunding a line item by quantity, specific amount, or percentage. Refund options for issuing refunds for whole invoices include refunding by a specific amount, or percentage amount.

* Quantity refunds allow you to refund quantity amounts on each/any line item on an invoice.
* Specific amount refunds allow you to refund specific dollar/cent amounts on each/any line item on an invoice, or refund off of the total amount of an invoice.
* Percentage refunds allow you to refund percentage amounts on each/any line item on an invoice, or refund off of the total amount of an invoice.

> 👍 Good to know:
>
> If you choose to issue a line item by a specific dollar amount or percentage, the “quantity” item for the line item(s) will show up as “1” on the invoice. Only quantity-based refunds will show specific quantity amounts for items on the invoice.

## Testing

Invoices created in a sandbox environment display a "TEST INVOICE" watermark. This watermark is exclusive to sandbox invoices and will not appear on production invoices.

## Account hierarchy invoice display

Invoices within an Account Hierarchy show "Primary Account" for the parent account and "Linked Account" for child accounts. This naming convention appears on the invoice PDF in customer emails, the Hosted Account Management invoice display, and the Recurly App Admin UI.