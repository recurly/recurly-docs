---
title: Manual invoicing
excerpt: >-
  Take control of your billing process with Recurly's Manual Invoicing, offering
  flexibility and precision in your customer billing interactions.
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

 This feature is only available to customers on the Professional and Elite subscription plans. To request to upgrade to this plan, please reach out to your Recurly account manager or [support@recurly.com](mailto:support@recurly.com) for more details.

# Definition

Manual Invoicing in Recurly allows businesses to create and manage invoices manually. This feature gives companies the flexibility to set specific payment terms, apply unique identifiers like PO numbers, and manage payments according to their unique business processes.

# Key benefits

- **Enhanced Flexibility:** Customize payment terms, collection methods, and billing details to suit specific customer agreements and business needs.
- **Professional and Compliant:** Generate clean, professional invoices that align with tax regulations, enhancing customer trust and satisfaction.
- **Streamlined Payment Management:** Easily record, track, and manage payments, with options to reopen invoices and record partial payments as needed.

# Key details

### Email templates

Enhance the clarity and professionalism of your communications by personalizing the default text for your Invoice New, Subscription New, and Invoice Past Due emails. Incorporate additional fields like `po_number`, `net_terms`, and potentially `net_terms_type` to ensure your communication resonates with your company's branding and messaging approach. 

> **Note**: The inclusion of `net_terms_type` may be contingent upon specific feature availability.

#### Payment confirmation options

Choose whether to send a payment confirmation every time a payment is entered, or only when an invoice is fully paid, allowing you to control and minimize the communication your customers receive.

### List views

Organize and manage your invoices effectively by using filters in the list view. Filter invoices by manual or automatic to quickly and efficiently manage and review invoices based on their type, making it easier to track and act on outstanding payments.

### Exports

Boost your data management and reporting efficiency by incorporating extra fields in the invoice, subscription, and transaction exports. Utilize fields like `po_number`, `collection_method`, `net_terms`, and potentially `net_terms_type` to generate comprehensive and structured data exports ideal for accounting, auditing, and analytical purposes.

**Note**: The availability of `net_terms_type` might be conditional based on specific feature settings.

### US sales tax/VAT

For manual invoices, US sales tax and VAT are calculated using the account level address. This ensures tax compliance and accurate billing. The account's VAT number, if available, is factored into the tax calculation, along with the address, allowing for precise and compliant tax calculations.

### Billing information

With manual invoices, the account address serves as the billing address, which appears on invoices and impacts US sales tax and VAT charges. This feature ensures that the correct address is used for tax calculations and that invoices are sent to the correct location.

#### Address requirements

If the account has a billing address but an empty account address, you will need to enter the account address in order for taxes to be calculated correctly, ensuring compliance and accuracy.

### Integration methods

Seamlessly create subscriptions and one-time invoices via the API, specifying the collection method, net terms, and PO number as needed. This integration allows for streamlined and automated creation of manual invoices, reducing manual effort and the risk of errors.

### Dunning management

Manual Payments includes a new set of dunning rules tailored specifically for manually invoiced customers. Customize your dunning settings at [Dunning Configuration](https://app.recurly.com/go/configuration/dunning) to align with your company’s credit control processes and customer communication strategy.

#### Dunning for manual payments

The dunning period for manual payments will kick off after an invoice has exceeded its net terms + 1 day. Recurly will not perform any payment retries on ACH payments. Retries can be initiated by attempting to collect the invoice in the Admin Console or using the APIs.

## Additional notes

- Reopening a manual invoice will not be logged in the account's Activity Log. Additionally, our exports and API will not indicate that a manual invoice was reopened.
- When a manual invoice with a partial payment recorded fails dunning, a write-off invoice for the full amount of the invoice will be created. Additionally, a partial credit from the write-off invoice will be applied to the remaining open balance on the purchase invoice. Recurly will also void the remainder of the open credit on the write-off invoice.

## Integration notes

### API integration for manual invoicing

- Recurly provides a robust API that allows you to integrate Manual Invoicing directly into your existing systems. This includes creating subscriptions and one-time invoices via the API, specifying the collection method, net terms, and PO number as needed.

### Webhooks for real-time updates

- Consider setting up webhooks to receive automated messages from Recurly when specific events related to manual invoicing occur, such as when a new manual invoice is generated. This allows for real-time syncing of invoice data between Recurly and your internal systems.

### Error handling in integration

- When integrating with Recurly’s API, ensure that your system is set up to handle errors gracefully. For example, if an API call to create a new manual invoice fails, your system should be able to retry the request or log the error for manual review.

### Security considerations

- Ensure that your integration with Recurly adheres to best practices for security. This includes using secure connections (HTTPS) for all API calls and safeguarding any API keys or credentials.

### Compliance and tax considerations

- Manual Invoicing in Recurly is designed to be compliant with various tax regulations, including US sales tax and VAT. However, tax regulations can vary significantly between regions, so it is essential to consult with a tax professional to ensure that your invoicing practices are fully compliant with all relevant laws and regulations.

### Testing in a sandbox environment

- Before deploying your integration in a production environment, thoroughly test it in a sandbox or staging environment. Recurly provides a [sandbox environment](https://docs.recurly.com/docs/sandbox-features-to-discover) for this purpose, allowing you to ensure that the integration works as expected without affecting your live data.

By paying attention to these integration notes, you can ensure a smooth and effective implementation of Recurly's Manual Invoicing feature within your existing infrastructure and workflows.

## Collection terms

### 1\. Automatically charge

This method will directly bill a credit card that the customer has on file.

### 2\. Invoice

This method allows for a manual invoice to be generated for the customer.

### 3\. Terms options for invoices

- **General Note**: All invoices are due "On-Receipt" by default. 
- **Manual Invoices**: If you're on our Professional or Elite plans and issue manual invoices, you'll have access to a Terms dropdown. Here are the available options:
  - On-Receipt
  - Net-10
  - Net-30
  - Net-60
  - Custom days 

### 4\. End of month (EOM) terms

These terms are particularly useful when you have business customers who pay invoices weeks or even months after the initial invoice was issued.

- **Access**: Available for Professional or Elite plans
- **Calculation**: The "Due Dates" on invoices indicate when they're considered "past due". An additional 24-hour window is added beyond the payment deadline. When an EOM term is applied, the "Due Date" considers the "Issue Date" of the invoice. From the last day of the issued month, the selected EOM duration is added, plus an extra 24 hours to get the final "Due Date".
- **Examples**:
  - Invoice created on June 6 with EOM +0 term: Due Date is July 1.
  - Invoice created on February 18 with EOM +15 term: Due Date is March 16.
  - Invoice created on September 27 with EOM +60 term: Due Date is November 30.
- **Supported EOM Terms**:
  - EOM +0
  - EOM +15
  - EOM +30
  - EOM +45
  - EOM +60
  - EOM +90
- **Restrictions**: Custom EOM terms are not supported. Once an EOM term is set on an invoice, its Due Date can't be edited. To change the Due Date, a refund must be issued for the current invoice, and a new one should be created.
- **API Availability**: This feature is currently accessible via our User Interface and both V2 and V3 API

### 5\. Understanding past due invoices

An invoice is considered past due the day after its official due date. For example, a "Net 30" invoice becomes past due exactly on the 31st day.

### 6\. Modifying a subscription payment method

To modify:

1. Go to the Recurly Admin Console and access the customer's account.
2. Click "Edit" next to the subscription plan that requires changes.
3. In the subscription details, click "Edit".
4. Here, you can toggle between payment options - Auto-Collect or Manually Collect. Note: To switch to Auto-Collect, the account must have stored credit card details.

**Note**: Price, quantity, or plan alterations will result in account credits or invoices. However, changes in manual invoice terms won't generate new customer invoices.

# Generating a manual invoice for a subscription

1. **Create a customer account (optional)**

- If the customer’s account is not already created, navigate to `https://app.recurly.com/go/accounts/new` to create a new account.

2. **Add account level address information**
   - Input the address information that will be carried over to all invoices for this account.

3. **Add as subscription**
   - Click `Add Subscription` on the customer’s account page.
   - Configure the customer’s subscription plan according to their needs.

4. **Edit billing details**
   - Under “Billing Details,” click `Edit`.
   - Set the `Collection Terms` (see options below).

5. **Customer communication**
   - Based on the outcome of the collection terms and payment attempt, the customer will receive appropriate communication. If you select `Invoice`, the customer will receive both a new subscription and a new invoice email.

### Generating one-off invoices

1. **Add charges to an existing account**
   - On an existing account, add any charges you'd like to bill the customer for using the "Add Charge" button on the account screen.

2. **Generate the invoice**
   - Once you're ready to invoice the customer, click the "Generate Invoice..." button at the top of the customer's account page.

3. **Select collection method**
   - On the left-hand side, you'll see a dropdown for the collection method. Select `Manual`.

4. **Enter additional details**
   - Enter a PO number if the customer had requested one, select your net terms, then click `Create Invoice`.

### Recording payments on manual invoices

1. **Access the customer’s account**
   - Navigate to the customer’s account inside the Recurly Admin Console.

2. **Open the invoice**
   - Click on the open invoice you want to record a payment for.

3. **Record a payment**
   - Choose `Record a Payment`.
   - Enter payment details, amount received, and payment receipt date, then click `Save`.

4. **Handle partial payments**
   - If only a partial payment is entered, be aware that the invoice may still enter a past due state and the customer may receive past due notifications.

### Reopening manual invoices

1. **Access the invoice**
   - Navigate to the paid or failed manual invoice you want to reopen.

2. **Reopen the invoice**
   - Click the "Reopen" button in the Invoice Actions dropdown.

3. **Record new payments**
   - After reopening, you can record new payments on the invoice and change its status to Paid.