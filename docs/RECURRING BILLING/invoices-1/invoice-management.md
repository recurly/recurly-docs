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

Invoice numbers are often used to reconcile invoices and transactions, so consider this before adding an entity-specific prefix. Gateways also handle this information differently, including invoice number length. For more detailed information, visit [gateway specific information for invoice numbers](https://docs.recurly.com/recurly-subscriptions/update/docs/gateway-specific-information-for-invoice-numbers).

Invoice numbering customization options are detailed below:

### Invoice Number Settings: Entity Prefix

Customize invoice numbering to reflect the appropriate entity for your business requirements.

Recurly enables you to add an invoice number prefix. The prefix is an alphanumeric value prepended to the sequential number. When you add an entity prefix, the sequence starts at 1000 and increments by 1.

An entity prefix will continue to support country-specific sequencing for countries in the EU for each sequence/prefix.

You can add an invoice number prefix per business entity. Go to Business Entity→Invoice Settings: Invoice Number Settings: Entity Prefix.

For more information on configuring prefixes, visit [Business Entity Invoice Settings](https://docs.recurly.com/recurly-subscriptions/docs/business-entities#invoice-settings).

Contact [support](mailto:support@recurly.com) to have entity invoice prefix added to your account.

## Business entities

### Definition

A business entity is a critical part of defining your business's identity to your customers. By carefully setting up your business entity, you can control how your business is represented on invoices, which can have a significant impact on how your customers perceive your brand.

### Key benefits

* **Customized customer experience:** By defining your business entity, you can tailor the information displayed on your customer invoices and emails, enhancing brand recognition and professionalism.
* **Global flexibility:** With the ability to set different addresses for invoice display and tax calculation, you can effectively manage your operations if your business has multiple locations around the globe.
* **Enhanced tax compliance:** Set up unique VAT/Tax ID information for each entity to comply with regional tax regulations and ensure correct tax calculations for each transaction.
* **Scalability:** The option to configure multiple business entities provides scalability for growing businesses with complex organizational structures or multiple distinct brands.

### Key details

## What is a business entity?

Your business entity allows you to define your business's identity to your customers. By setting up your business entity, you can control the company name, address, contact phone number, and VAT/Tax ID information that is displayed on customer invoices. You are also able to set a unique entity tax address for your business within the business entity setup, that can either be the same address as the invoice display or entirely different.

<Image align="center" border={true} width="80% " src="https://files.readme.io/39d19465f4103b6cf482c18cd54f4d0382c305833ada260b4f3a4e30ce2dde98-image.png" className="border" />

For businesses with global locations, Recurly offers the flexibility to set different addresses for invoice display and tax calculations. This means you could have a US address used for tax calculation on a purchase and a European address for invoice display.

### Setting up your business entity

Setting up your business entity in Recurly involves defining three essential components: company details, invoice display address, and tax address. Additionally, you have the option to enter Tax ID Numbers (TINs) or TIN/VAT information based on your organization's needs, as well as header and footer logo images for invoice display.

* **Company details**: This is the foundational information about your company. It includes the legal name of the business, location, contact information, and other relevant details.
* **Invoice display address**: This is the address that will appear on invoices that are generated by Recurly. It should be the official business address where your company is registered.
* **Tax address**: This is the address used by Recurly to calculate tax obligations. It’s essential to enter this information accurately, as it affects the calculation of sales and other taxes for your transactions.
* **Tax ID numbers (TINs) / TIN/VAT information (optional)**: If your company is required to collect VAT or has a Tax Identification Number (TIN), you can enter this information here. This section is optional, and you should consult with your tax advisor or authority to determine if it is necessary for your business.
* **Billing Contact Email**: This is the email address used for display on all Recurly invoices/receipts and acts as the 'from' address for all transaction-related customer communications. Your Site Default Entity will always use the billing contact email address set on your Site Settings page. If you are on Recurly's Elite plan, you can set [unique email addresses for each alternate business entity](https://docs.recurly.com/docs/multiple-business-entities#entity-specific-merchant-email-addresses). If you do not set an entity-specific billing contact email address on an alternate entity, the email address on your Site Settings page will be used as a fallback.
* **Logo/images for header and footer**: Images to add to the invoice header and footer. These are optional configurations.

Please ensure that the company details, invoice display address, and tax address are filled out accurately based on your organization’s requirements, as they are critical to your operation within Recurly.

**For merchants on Recurly's Elite plans only:** [Learn more.](https://docs.recurly.com/docs/multiple-business-entities#entity-level-invoice-treatments)

* **Customer notes**: Customer Notes is another notes section available to you for any details you would like to add. This section is ideal for notes on invoice details or including a special message for the customer, like "thanks for your business".
* **Terms and conditions**: Terms and Conditions is a notes section available to you for any details you would like to add. The section is ideal for notes about payment or contract terms.

### Company details

This section captures the name of the company, entity code (which acts as a unique identifier used in URLs and API references - the default entity code is "default" and cannot be modified), and the phone number that will appear on invoices (often a customer support number).

<Image align="center" border={true} width="80% " src="https://files.readme.io/432de9b65c0a0c7302f7952394c1156dde527859eeec979331f02d333a417bca-image.png" className="border" />

### Invoice display address

The address you enter is the company information that appears on each customer invoice. By default, this address is also used as the origin merchant address for tax calculations. If you want to specify a different address for tax calculation purposes, you need to check the box labeled "Set a different address for tax calculation." When this box is checked, you will have the option to enter a separate address that will be used solely for tax calculations, while the original address remains as the display address on customer invoices.

If you choose to use different addresses for invoice display and tax calculation, you can enter a unique address for each. Note that only the tax calculation address will be sent to Avalara or Vertex; the invoice display address will not be used for tax calculations.

<Image align="center" border={true} width="80% " src="https://files.readme.io/d74c7110316318650028b5d55e617bf68d0c9eea87bd1ae0623a5563b535358b-image.png" className="border" />

Even if you don't have taxes enabled on your Recurly site, setting up your business entity is beneficial. The invoice display address will appear on all customer invoices, which can contribute to your brand image and identity.

<Image align="center" border={true} width="80% " src="https://files.readme.io/acbfd75b522d3cc6b586948ade4b0bd2285952f48de71e898552c578fcb0b346-image.png" className="border" />

### Invoice settings

Merchants can set invoice treatments specific to their Site Default Business Entity by configuring custom settings for entity prefix, EU country sequencing, header images and footer images. By doing this, any invoice generated will receive the invoice treatments applied to the corresponding entity, unless custom settings are set to override business entity logic from the Invoice Templates page.

#### Invoice Number Settings: Entity Prefix

Merchants will be able to choose whether or not to enable entity-specific invoice sequencing directly on each of their business entities.

* An entity prefix is an alphanumeric of 4 characters or less that is prepended to the sequential number.
* When adding an entity prefix, the sequence will start at 1000 and increment by 1.

Note: Changes to invoice numbering can potentially disrupt reconciliation and gateway processing. For more detailed information, visit [gateway specific information for invoice numbers](https://docs.recurly.com/recurly-subscriptions/update/docs/gateway-specific-information-for-invoice-numbers).

Contact [support](mailto:support@recurly.com) to have entity invoice prefix added to your account.

### Invoice Number Settings: EU Country-specific numbering

For a separate invoice sequence for each European Union country, you can activate the Country Invoice Sequencing feature in Recurly. Go to Business Entity→Invoice Settings: Invoice Settings, find "Country Sequencing", and enable "Country Invoice Sequencing".

For more detailed information, visit [EU Country Sequencing](https://docs.recurly.com/recurly-subscriptions/docs/eu-vat-2015#invoice-sequencing-by-country). For configuration details, visit [Business Entity Invoice Settings](https://docs.recurly.com/recurly-subscriptions/docs/business-entities#invoice-settings).

### Order Number Prefix

Recurly enables the addition of a hidden prefix to your invoice numbering. This is particularly helpful if you use the same payment gateway for multiple billing systems and need to segment your transactions. The order number prefix will not appear on invoices. The order number prefix is not configured per business entity.

To add a hidden prefix, go to Configuration→Site Settings and enter your desired prefix under "Order Number Prefix".

<Image align="center" border={true} width="80% " src="https://files.readme.io/b85d93e470e2b710adb1c1c440ffdf3a9a19d0aa11027b6a08f05e5d3aab3ed9-image.png" className="border" />

### Customize initial number

If you prefer to start your invoice numbering at a different number other than 1000, you can reach out to Recurly Support. Contact them through this link: [Recurly Support](https://support.recurly.com/)

## Display

The display of invoices in the Recurly Admin Console, Hosted Invoice, or as a PDF includes the following elements:

### Number and collection

* **Invoice number & posting date:** Every invoice displays its number and the date it was posted.
* **Charge Invoices:** These will additionally show a term option and due date.
* **Credit Invoices:** If issued against a charge invoice, the relevant charge invoice number(s) will be listed.
* **Visualization:** Invoice numbers may include prefixes or country codes as configured in Business Entities. The following visualization is an example of what invoice number sequencing looks like with multiple business entities.

<Image align="center" border={true} width="80% " src="https://files.readme.io/de8c42f72668ee9f22b1eed749ff5993d5922ceab201d0df15cd5eb926bb0c1a-image.png" className="border" />

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
* Can be configured to always use Account Information (with Billing Information as fallback) by enabling "Use Account Information Address for all Invoices" under Configuration→Taxes→Tax Settings.

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
* VAT Number

Learn more about [Shipping Addresses](https://docs.recurly.com/docs/shipping-addresses)

### Line items

Invoices contain a table of line items with these columns:

* Date
* Description (if provided, HS Code will be displayed following the description)
* Quantity
* Price
* Discount (shown only if applicable)
* Subtotal
* Tax (shown only if applicable, displaying the rate)
* Tax Net (shown only if applicable, displaying the tax calculated by subtotal and tax rate)
* Total (shown only if tax is applicable)

<Image align="center" border={true} width="80% " src="https://files.readme.io/a92bac25e71813afc14bc6a42def2339e755646c47c23ba4756f9bc8209d8652-image.png" className="border" />

> **Note:** Invoices displayed via the Admin Console, Hosted Invoice, and PDF will truncate line items after the first 500. The subtotal, tax, and total will reflect the sum of all line items. To access line items beyond the first 500, use the [Adjustments Export](https://docs.recurly.com/docs/adjustments-exports)

### Total and balance

At the bottom right of the invoice, the following invoice-level values are displayed:

* **Subtotal:** The total before taxes and additional charges.
* **Tax:** Shown only if tax is applicable to the invoice.
* **Total:** The invoice total, inclusive of all charges and taxes.
* **Balance:** The remaining amount due on the invoice.

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

<Image align="center" border={true} width="80% " src="https://files.readme.io/3dc4f14-Image_2020-03-20_at_8.53.19_AM.png" className="border" />

#### Volume pricing

* **Description:** Line items for Volume pricing are similar to those for fixed-price products, using the per-unit price from the relevant subscription tier.
* **Visualization:**

<Image align="center" border={true} width="80% " src="https://files.readme.io/576c291-volume.png" className="border" />

#### Stairstep pricing

* **Description:** A single line item is created, displaying the Add-On name and purchased quantity. The charge quantity is set to 1, with the price reflecting the fixed price for the applicable tier.
* **Visualization:**

<Image align="center" border={true} width="80% " src="https://files.readme.io/a983819-Image_2020-03-20_at_8.59.44_AM.png" className="border" />

### Payment history

The "Payments" section of the invoice display includes all transactions and credit payments that have reduced the invoice's balance. It details the date and amount of each payment.

### Notes

Invoices feature three types of notes sections, which are visible only if they contain text. These notes can have site-level default settings and can also be customized per invoice via the Admin Console or API. Set up site-level defaults on the [Invoice Settings](https://app.recurly.com/go/configuration/invoice_settings/edit) page.

#### Customer notes

* **Notes:** A section for any customer-specific notes, such as special invoice details or a thank-you message.
* **Title Visibility:** The title of this section is always visible and cannot be altered.

#### Terms and conditions

* **Description:** A section for payment terms, legal notes, or other important information.
* **Title Visibility:** The title of this section is always visible and cannot be altered.

#### VAT reverse charge notes

* **Description:** Used for European Union reverse charge tax scenarios.
* **Configuration:** Set up on the Tax Settings page.

Learn more about [VAT Reverse Charge Notes](https://docs.recurly.com/docs/eu-vat-2015#section-eu-vat-registered-customers).

<Callout icon="👍" theme="okay">
  The Customer Notes section is ideal for invoice details or a message such as "thanks for your business." Invoice notes also let you add information that may be required for local invoice compliance, such as Authorized Dealer, delivery note number, type of supply, intra-community supply, goods status, Israel invoice model, and Israel special note.
</Callout>

### Invoice currency notes

In the Notes section of the invoice following any customer-specific notes, Recurly will display any relevant invoice currency information. Information such as the displayed currency, the converted currency rate, date and source used for currency conversion are provided.

<Image align="center" border={true} src="https://files.readme.io/6b0b5a50696c86ec60a37243c47758a48cdd01bb3c6aac8ae55fb3d62e812f5c-image.png" className="border" />

## PDFs

Enable PDF invoice attachments in email notifications by navigating to the Email Templates page in the Configuration section of the Recurly App.

From there, open the edit view of any of the 7 email templates associated with invoices, select "Attach PDF" under "Attachments," and save your changes.

Email Templates that support invoice PDF attachments:

* New Subscription
* New Invoice (Manual Invoice feature only)
* Invoice Past Due (Manual Invoice feature only)
* Payment Confirmation
* Payment Declined
* Payment Refunded
* Payment Voided

<Image align="center" border={true} width="80% " src="https://files.readme.io/7991f5e1662aac7700799c06d51013d81571f449a5957f284458d36a833b94cf-image.png" className="border" />

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

### Dunning

When an invoice enters a Past Due state, it initiates the dunning cycle. For automatic collection invoices, this occurs after the first transaction decline. For manual collection invoices, it starts 24 hours after the invoice's due date. Automatic and manual collection invoices each have distinct dunning cycles and associated email templates: "Payment Declined" for automatic and "Invoice Past Due" for manual collection. Within your dunning settings, you can choose to either fail the invoice at the end of the cycle or leave it past due. Note: With [Account Updater](https://docs.recurly.com/docs/account-updater) enabled, Recurly will continually run Account Updater on the associated account and attempt to collect payment indefinitely.

Learn more about [Dunning Management](https://docs.recurly.com/docs/dunning-management) and [Automated Transaction Retry Logic](https://docs.recurly.com/docs/retry-logic).

### Stop collection

To write off an unpaid invoice, use the **Stop Collection** option in the Invoice Actions dropdown on the invoice details page. This action changes the invoice state to Failed and removes the amount from the customer's account balance. With Credit Invoices enabled, failing an invoice creates a corresponding write-off credit invoice, balancing the failed invoice to zero. Stopping collection also halts the dunning cycle, including all automated emails and payment retries, as well as activities performed by Recurly's [Account Updater](https://docs.recurly.com/docs/account-updater).

Once failed, an invoice cannot be reopened. This applies to manual collection invoices due to the existence of the write-off credit invoice.

> **Note:** Failing an invoice does not automatically cancel the related subscription. To stop future billings, cancel the subscription separately.

## Refunds

Refunds are processed at the invoice level. Options include changing a subscription, refunding a specific invoice, or refunding the last invoice while terminating a subscription. These actions generate a refund credit invoice with credit line items against previously paid charge line items. Directly refunding an invoice allows you to distribute the credit as a payment refund or retain it as a credit balance for future invoices.

To refund an invoice, select "Issue Refund" in the **Invoice Actions** dropdown in the Admin Console. 

<Image align="center" border={true} width="80% " src="https://files.readme.io/b9244b94fbf72c85c2e397d4a58498e523050b7e1ad3b46ea3e495798ec04007-image.png" className="border" />

Invoice refunds are also supported in both versions of Recurly's API.

On the Issue Refund page, you can refund by line item or for the entire invoice.

> 🚧 Important
>
> Merchants _**without**_ the "Only Bill What Changed" and "Credit Memos" feature flags enabled on their site only have the option to refund by "Quantity" for line items and by "Specific Amounts" for entire invoices. Refunding by percentages and specific amounts on line items, and by percentages on entire invoices, is _not available_ for merchants without the "Credit Memos" and "OBWC" features enabled.

**Select to refund by line item**:

<Image align="center" border={true} width="80% " src="https://files.readme.io/56d53f7e6e5a4c528ea0f3aed6dcc7909686fb6bc00d62e10621ffa26bd5d24d-image.png" className="border" />

**Select to refund by entire invoice:**

<Image align="center" border={true} width="80% " src="https://files.readme.io/f6a52be7f550e7850161b6873323e0c528f18232a9b9deca7059461e6c16696f-image.png" className="border" />

Refund options for individual line items include refunding by quantity, specific amount, or percentage. Refund options for whole invoices include refunding by a specific amount or percentage.

* Quantity refunds allow you to refund quantities on any line item on an invoice.
* Specific amount refunds allow you to refund specific dollar or cent amounts on any line item on an invoice or from the total amount of an invoice.
* Percentage refunds allow you to refund percentage amounts on any line item on an invoice or from the total amount of an invoice.

> 👍 Good to know
>
> If you choose to issue a line item by a specific dollar amount or percentage, the “quantity” item for the line item(s) will show up as “1” on the invoice. Only quantity-based refunds will show specific quantity amounts for items on the invoice.

## Testing

Invoices created in a sandbox environment display a "TEST INVOICE" watermark. This watermark is exclusive to sandbox invoices and will not appear on production invoices.

## Account hierarchy invoice display

Invoices within an Account Hierarchy show "Primary Account" for the parent account and "Linked Account" for child accounts. This naming convention appears on the invoice PDF in customer emails, the Hosted Account Management invoice display, and the Recurly App Admin UI.