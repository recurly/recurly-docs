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

* Invoice number customization and prefix addition require support assistance.
* Certain invoice display customizations may not be supported in all configurations.
* Invoices displayed via the Admin Console, Hosted Invoice, and PDF truncate line items after the first 500.
* Once a manual invoice is paid or a payment attempt is made using billing information on file, it converts to automatic collection. Converting a charge invoice from automatic to manual collection is not currently supported.
* Once an invoice is failed (via Stop Collection), it cannot be reopened.

***

# Definition

Recurly's invoice management system generates, tracks, and customizes invoices to automate your billing process. Each invoice records transactions — including sales, renewals, and refunds — and clearly details the services or products provided and their associated costs. The system supports customizable invoice numbering and includes features to identify transaction origins, making financial reporting and compliance straightforward.

***

# Key benefits

* **Detailed transaction records:** Every invoice provides a full breakdown of transactions, including origins, amounts, and customer details — giving you the transparency you need to build trust with subscribers.
* **Customizable numbering and sequencing:** Tailor invoice numbering to start from a specific number or add prefixes for better organization — especially useful for businesses operating across multiple markets or product lines.
* **Comprehensive display options:** Customize invoices to include the business and customer information that matters most, keeping them informative, compliant, and on-brand.

***

# Key details

## Invoice numbering

<Image align="center" border={true} src="https://files.readme.io/2d854e9d97470a9a00e91944efdb6f1283cdcf0cbd4a37a39aa25773626b28e4-Screenshot_2026-04-28_at_2.25.43_PM.png" className="border" />

> **Note:** Invoice numbers are commonly used to reconcile invoices and transactions. Keep this in mind before adding an entity-specific prefix, as gateways handle invoice number length differently. See [gateway-specific information for invoice numbers](https://docs.recurly.com/recurly-subscriptions/update/docs/gateway-specific-information-for-invoice-numbers) for details.

### Add an entity prefix

An entity prefix is an alphanumeric value (four characters or fewer) prepended to the sequential invoice number. When you add one, the sequence restarts at 1000 and increments by one. Entity prefixes also support country-specific sequencing for EU countries within each sequence.

**To add an entity prefix:**

1. Go to **Business Entity → Invoice Settings → Invoice Number Settings: Entity Prefix**.
2. Contact [support@recurly.com](mailto:support@recurly.com) to have the entity invoice prefix added to your account.

For full configuration details, see [Business Entity Invoice Settings](https://docs.recurly.com/recurly-subscriptions/docs/business-entities#invoice-settings).

### Enable EU country-specific numbering

If you need a separate invoice sequence for each European Union country, you can activate Country Invoice Sequencing.

**To enable EU country sequencing:**

1. Go to **Business Entity → Invoice Settings**.
2. Find **Country Sequencing** and enable **Country Invoice Sequencing**.

For more information, see [EU Country Sequencing](https://docs.recurly.com/recurly-subscriptions/docs/eu-vat-2015#invoice-sequencing-by-country).

### Add a hidden order number prefix

If you use the same payment gateway across multiple billing systems, you can add a hidden prefix to segment your transactions. This prefix does not appear on invoices and is not configured per business entity.

**To add an order number prefix:**

1. Go to **Configuration → Site Settings**.
2. Enter your desired prefix under **Order Number Prefix**.

<Image align="center" border={true} width="75%" src="https://files.readme.io/b85d93e470e2b710adb1c1c440ffdf3a9a19d0aa11027b6a08f05e5d3aab3ed9-image.png" className="border" />

### Customize the starting number

If you'd like to start your invoice numbering at a number other than 1000, reach out to [Recurly Support](https://support.recurly.com/).

***

## Business entities

A business entity defines your company's identity on customer-facing invoices and emails. Setting it up correctly lets you control the company name, address, phone number, and VAT/Tax ID information that appear on every invoice.

<Image align="center" border={true} width="75%" src="https://files.readme.io/39d19465f4103b6cf482c18cd54f4d0382c305833ada260b4f3a4e30ce2dde98-image.png" className="border" />

For businesses with global locations, Recurly lets you set different addresses for invoice display and tax calculations — for example, a US address for tax purposes and a European address for invoice display.

### Set up your business entity

Setting up a business entity involves three required components and a few optional ones:

* **Company details:** The legal name of your business, location, contact information, and a unique entity code used in URLs and API references. The default entity code is `default` and cannot be modified.
* **Invoice display address:** The company address that appears on each customer invoice. By default, this address is also used for tax calculations.
* **Tax address:** The address Recurly uses to calculate tax obligations. If you want to use a different address for tax purposes, check **Set a different address for tax calculation** — this address will be sent to Avalara or Vertex, while the invoice display address remains unchanged.

<Image align="center" border={true} width="75%" src="https://files.readme.io/432de9b65c0a0c7302f7952394c1156dde527859eeec979331f02d333a417bca-image.png" className="border" />

<Image align="center" border={true} width="75%" src="https://files.readme.io/d74c7110316318650028b5d55e617bf68d0c9eea87bd1ae0623a5563b535358b-image.png" className="border" />

<Image align="center" border={true} width="75%" src="https://files.readme.io/acbfd75b522d3cc6b586948ade4b0bd2285952f48de71e898552c578fcb0b346-image.png" className="border" />

The following are optional:

* **Tax ID Numbers (TINs) / TIN/VAT information:** If your company collects VAT or has a Tax Identification Number (TIN), enter it here. Consult your tax advisor to determine whether this applies to your business.
* **Billing contact email:** The email address displayed on all Recurly invoices and receipts, and used as the "from" address for all transaction-related customer communications. Your Site Default Entity always uses the billing contact email set on your Site Settings page. If you're on Recurly's Elite plan, you can set [unique email addresses for each alternate business entity](https://docs.recurly.com/docs/multiple-business-entities#entity-specific-merchant-email-addresses).
* **Logo/images for header and footer:** Optional images added to the top and bottom of your invoices.
* **Customer notes:** A free-text section for any customer-specific details — for example, "Thanks for your business!" This is also where you can add information required for local invoice compliance, such as authorized dealer info, delivery note numbers, or Israel-specific invoice fields.
* **Terms and conditions:** A free-text section for payment terms, legal notes, or other contractual information.

> **Merchants on Recurly's Elite plans only:** [Learn more about entity-level invoice treatments.](https://docs.recurly.com/docs/multiple-business-entities#entity-level-invoice-treatments)

***

## Invoice display

Invoices rendered in the Admin Console, Hosted Invoice, or as a PDF include the following sections.

### Number and collection

Every invoice shows its invoice number and posting date. Charge invoices also display a payment term and due date. Credit invoices list the relevant charge invoice number(s) they were issued against.

Invoice numbers may include entity prefixes or EU country codes depending on your configuration.

<Image align="center" border={true} width="75%" src="https://files.readme.io/de8c42f72668ee9f22b1eed749ff5993d5922ceab201d0df15cd5eb926bb0c1a-image.png" className="border" />

### From address

Located at the top left of the invoice, the From address pulls from your Site Settings and includes:

* Company name
* Address (lines one and two)
* City, state/province, zip/postal code, and country
* Phone number
* Billing contact email
* VAT number
* Registration number

### Bill to

The Bill To section defaults to the account's billing information for automatic collection, or account information for manual collection. You can configure it to always use account information (with billing information as a fallback) by enabling **Use Account Information Address for all Invoices** under **Configuration → Taxes → Tax Settings**.

* Defaults to Billing Information for automatic collection methods or Account Information for manual methods.
* Can be configured to always use Account Information (with Billing Information as fallback) by enabling "Use Account Information Address for all Invoices" under Configuration→Taxes→Tax Settings. Fields displayed in the Bill To section:
* First and Last Name
* Company Name (from Account Information)
* Address (Address 1 and Address 2)
* City
* State/Province
* Zip/Postal Code
* Country
* VAT Number

* First and last name
* Company name (from Account Information)
* Address (lines one and two)
* City, state/province, zip/postal code, and country
* VAT number

### Ship to

* First and Last Name
* Address (Address 1 and Address 2)
* City
* State/Province
* Zip/Postal Code
* Country
* VAT Number Learn more about [Shipping Addresses](https://docs.recurly.com/docs/shipping-addresses)

### Line items

Invoices include a table of line items with the following columns:

* Date
* Description (HS Code is displayed after the description if provided)
* Quantity
* Price
* Discount (shown only if applicable)
* Subtotal
* Tax (shown only if applicable — displays the rate)
* Tax Net (shown only if applicable — displays tax calculated from subtotal and rate)
* Total (shown only if tax is applicable)

<Image align="center" border={true} width="75%" src="https://files.readme.io/a92bac25e71813afc14bc6a42def2339e755646c47c23ba4756f9bc8209d8652-image.png" className="border" />

At the bottom right of the invoice, the following invoice-level values are displayed:

* **Subtotal:** The total before taxes and additional charges.
* **Tax:** Shown only if tax is applicable to the invoice.
* **Total:** The invoice total, inclusive of all charges and taxes.
* **Balance:** The remaining amount due on the invoice. Between the Total and Balance, the following balance-changing entries are listed:
* **Paid:** Represents the total of all payment transactions.
* **Credit Applied/Redeemed:** The total value of all credit payments applied to the invoice.
* **Payment Refund:** The total of all refund transactions made against the invoice.
* **Credit Voided:** Any portion of the credit balance that has been removed or voided.
* **Write-Off:** The amount of the invoice that has been written off.

### Quantity-based pricing line items

Line item structure varies depending on your pricing model.

**Tiered pricing:** Each tier results in a separate line item. The add-on name includes the unit range (e.g., "Seats: 1–10").

<Image align="center" border={true} width="75%" src="https://files.readme.io/3dc4f14-Image_2020-03-20_at_8.53.19_AM.png" className="border" />

**Volume pricing:** Line items are similar to fixed-price products, using the per-unit price from the applicable subscription tier.

<Image align="center" border={true} width="75%" src="https://files.readme.io/576c291-volume.png" className="border" />

**Stairstep pricing:** A single line item is created showing the add-on name and purchased quantity. The charge quantity is set to one, with the price reflecting the fixed price for the applicable tier.

<Image align="center" border={true} width="75%" src="https://files.readme.io/a983819-Image_2020-03-20_at_8.59.44_AM.png" className="border" />

### Total and balance

At the bottom right of the invoice, you'll find:

* **Subtotal:** The total before taxes and additional charges
* **Tax:** Shown only if applicable
* **Total:** The invoice total, inclusive of all charges and taxes
* **Balance:** The remaining amount due

Between the Total and Balance, the following balance-changing entries are listed: Paid, Credit Applied/Redeemed, Payment Refund, Credit Voided, and Write-Off.

### Payment history

The Payments section lists all transactions and credit payments that have reduced the invoice's balance, including the date and amount of each.

### Notes

Invoices include up to three notes sections, which are visible only if they contain text. You can set site-level defaults on the [Invoice Settings](https://app.recurly.com/go/configuration/invoice_settings/edit) page, and override them per invoice via the Admin Console or API.

* **Customer notes:** Visible to the customer. Ideal for invoice-specific details, a thank-you message, or any information required for local invoice compliance (e.g., authorized dealer info, delivery note numbers, Israel-specific invoice fields).
* **Terms and conditions:** For payment terms, legal notes, or other important contractual information.
* **VAT reverse charge notes:** Used for EU reverse charge tax scenarios. Configured on the Tax Settings page. Learn more about [VAT Reverse Charge Notes](https://docs.recurly.com/docs/eu-vat-2015#section-eu-vat-registered-customers).

### Invoice currency notes

When currency conversion applies, Recurly displays the relevant currency information in the Notes section following any customer notes — including the displayed currency, converted currency rate, conversion date, and source used.

<Image align="center" border={true} width="75%" src="https://files.readme.io/6b0b5a50696c86ec60a37243c47758a48cdd01bb3c6aac8ae55fb3d62e812f5c-image.png" className="border" />

***

## PDF invoice attachments

You can attach PDF invoices to email notifications sent from Recurly.

**To enable PDF attachments:**

1. Go to **Configuration → Email Templates**.
2. Open the edit view of the email template you want to update.
3. Under **Attachments**, select **Attach PDF**.
4. Save your changes.

The following email templates support PDF invoice attachments:

* New Subscription
* New Invoice (Manual Invoice feature only)
* Invoice Past Due (Manual Invoice feature only)
* Payment Confirmation
* Payment Declined
* Payment Refunded
* Payment Voided

<Image align="center" border={true} width="75%" src="https://files.readme.io/7991f5e1662aac7700799c06d51013d81571f449a5957f284458d36a833b94cf-image.png" className="border" />

***

## Invoice emails

Recurly sends invoice-related emails based on the type of invoice and how it was created:

* **Initial subscription:** The first invoice is included in the **New Subscription** email.
* **Automatic collection invoices:** Subsequent invoices use the **Payment Confirmation** email. Invoices with a $0.00 total are not sent.
* **Manual collection invoices:** Always trigger the **New Invoice** email template.

To resend an invoice email, use the **Resend Last Email** button on the invoice detail page.

***

## Proration

Line items are prorated for immediate subscription changes. Proration is calculated down to the second, although line item dates are displayed by day. Learn more about [immediate subscription change proration](https://docs.recurly.com/docs/change-subscription#section-time-based-proration).

***

## Collection methods

The collection method on a charge invoice determines whether Recurly processes payment immediately or simply issues the invoice for manual payment.

### Automatic collection

Recurly attempts payment using the billing information on file (e.g., credit card, bank account, PayPal, Amazon). For new subscriptions and the Purchases API, a successful transaction is required before the invoice posts. For renewals and the Post Invoice API, the invoice posts and payment is processed per the invoice terms. If the transaction is declined, the invoice enters Past Due status and the dunning cycle begins.

### Manual collection

Recurly issues the invoice without attempting payment. External payments can be recorded manually later, or subscribers can pay via the **Make a Payment** button on the Hosted Invoice.

> **Note:** Once a manual invoice is paid — or a payment attempt is made using billing information on file — it converts to automatic collection. It's not currently possible to record a manual payment on an automatic collection invoice, or to convert a charge invoice from automatic to manual collection.

**To record an external payment manually:** open the invoice in the Admin Console and enter the payment details in the left sidebar. A manually paid invoice can be reopened.

Learn more about [manual collection](https://docs.recurly.com/docs/manual-payments) and the [Make a Payment option](https://docs.recurly.com/docs/hosted-account-management#section-online-payments).

### Change a subscription's collection method

Changing the collection method on a subscription affects the next charge invoice generated — it does not change any already-issued invoices.

**To change the collection method:**

1. Open the subscription in the Admin Console.
2. Select **Edit Subscription** from the **Subscription Actions** dropdown.
3. Scroll to the **Invoicing** section.
4. Select a new value from the **Collection Method** dropdown.
5. Save your changes.

> **Note:** The change applies immediately, regardless of whether "On next renewal" is selected under Plan Effective Date.

### Dunning

When an invoice enters Past Due status, Recurly initiates the dunning cycle:

* **Automatic collection:** Dunning begins after the first transaction decline, using the **Payment Declined** email template.
* **Manual collection:** Dunning begins 24 hours after the invoice's due date, using the **Invoice Past Due** email template.

At the end of the dunning cycle, you can choose to fail the invoice or leave it past due. With [Account Updater](https://docs.recurly.com/docs/account-updater) enabled, Recurly will continue running Account Updater on the account and attempt to collect payment indefinitely.

Learn more about [Dunning Management](https://docs.recurly.com/docs/dunning-management) and [Automated Transaction Retry Logic](https://docs.recurly.com/docs/retry-logic).

### Stop collection

To write off an unpaid invoice, use **Stop Collection** from the **Invoice Actions** dropdown on the invoice detail page. This changes the invoice state to Failed and removes the amount from the customer's account balance. With Credit Invoices enabled, failing an invoice creates a corresponding write-off credit invoice that balances the failed invoice to zero. Stopping collection also halts all dunning activity, including automated emails, payment retries, and Account Updater.

> **Note:** Failing an invoice does not cancel the related subscription. Cancel the subscription separately to stop future billing.

***

## Refunds

Refunds are processed at the invoice level. You can issue a refund by changing a subscription, refunding a specific invoice, or refunding the last invoice while terminating a subscription. These actions generate a refund credit invoice with credit line items against previously paid charge line items.

**To issue a refund:**

1. Open the invoice in the Admin Console.
2. Select **Issue Refund** from the **Invoice Actions** dropdown.

<Image align="center" border={true} width="75%" src="https://files.readme.io/b9244b94fbf72c85c2e397d4a58498e523050b7e1ad3b46ea3e495798ec04007-image.png" className="border" />

On the Issue Refund page, choose to refund by line item or for the entire invoice.

**Refund options by line item:**

<Image align="center" border={true} width="75%" src="https://files.readme.io/56d53f7e6e5a4c528ea0f3aed6dcc7909686fb6bc00d62e10621ffa26bd5d24d-image.png" className="border" />

**Refund options for the entire invoice:**

<Image align="center" border={true} width="75%" src="https://files.readme.io/f6a52be7f550e7850161b6873323e0c528f18232a9b9deca7059461e6c16696f-image.png" className="border" />

Available refund methods:

* **Quantity:** Refund specific quantities on any line item
* **Specific amount:** Refund a specific dollar or cent amount on a line item or from the invoice total
* **Percentage:** Refund a percentage of a line item or the invoice total

> **Note:** Merchants without the "Only Bill What Changed" and "Credit Memos" features enabled can only refund by quantity (line items) or specific amount (entire invoices). Percentage-based and specific-amount line item refunds are not available without these features.
>
> **Good to know:** If you refund a line item by specific dollar amount or percentage, the quantity shown for that line item on the invoice will appear as "1." Only quantity-based refunds display specific quantity amounts.

Invoice refunds are also supported in both versions of the Recurly API.

***

## Testing

Invoices created in a sandbox environment display a **TEST INVOICE** watermark. This watermark only appears on sandbox invoices and will not show up in production.

***

## Account hierarchy invoice display

Within an Account Hierarchy, invoices display **Primary Account** for the parent account and **Linked Account** for child accounts. This naming convention appears on the invoice PDF in customer emails, the Hosted Account Management invoice display, and the Recurly App Admin UI.

***

# FAQs

**Can I start my invoice numbering at a number other than 1000?**
Yes. Contact [Recurly Support](https://support.recurly.com/) to customize your starting invoice number.

**How do I add an entity prefix to my invoice numbers?**
Go to **Business Entity → Invoice Settings → Invoice Number Settings: Entity Prefix**, then contact [support@recurly.com](mailto:support@recurly.com) to have the prefix added to your account.

**What happens if a payment is declined on an automatic collection invoice?**
The invoice enters Past Due status and the dunning cycle begins. Recurly will retry payment and send the **Payment Declined** email template based on your dunning settings.

**Can I convert an invoice from automatic to manual collection?**
No. It's not currently possible to convert a charge invoice from automatic to manual collection.

**What happens when I stop collection on an invoice?**
The invoice state changes to Failed, the amount is removed from the customer's account balance, and all dunning activity stops. If Credit Invoices are enabled, a write-off credit invoice is created to balance the failed invoice to zero. Failed invoices cannot be reopened.

**Does failing an invoice cancel the subscription?**
No. You need to cancel the subscription separately to stop future billing.
