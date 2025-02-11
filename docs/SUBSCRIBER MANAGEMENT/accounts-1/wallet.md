---
title: Subscriber wallet
excerpt: >-
  The "Subscriber Wallet" is an innovative solution designed to enhance the
  subscription experience for customers by offering them unprecedented
  flexibility in managing their payments.
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

There are additional fees to use Wallet. Please reach out to your Account Manager, Account Executive or contact Recurly Support to learn more.

# Definition

The "Subscriber Wallet" is an innovative solution designed to enhance the subscription experience for customers by offering them unprecedented flexibility in managing their payments.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/488d078d6c1f98273b425a9afed644ea684bc4490ad209fc83ad5f245fd9947f-image.png",
        null,
        null
      ],
      "align": "center",
      "sizing": "75% ",
      "border": true
    }
  ]
}
[/block]


# Key benefits

- **Payment flexibility:** Customers can choose and switch between different payment methods for their subscriptions. This can be especially useful when one payment method fails or if they simply prefer a different option for certain transactions.
- **User-centric design:** The primary payment method acts as a default, ensuring seamless transactions even if a user forgets to specify a particular method.

# Key details

The Recurly "Subscriber Wallet" is a feature that allows for enhanced payment flexibility for both merchants and their subscribers. It provides subscribers the ability to manage multiple payment methods and assign specific billing info to different subscriptions or one-time purchases.

## Core functionalities

1. **Multiple Payment Options**: Customers can store multiple payment methods, catering to their dynamic financial situations.
2. **Adaptive Default Mechanism**: The primary payment method is the default choice unless indicated differently. This guarantees continuous service.
3. **Customizable Subscriptions**: Specific billing info can be assigned to each subscription, giving customers a tailored experience.
4. **Fallback Option**: In case a chosen billing method fails, there's a backup in place to ensure continuous service, and offers an additional recovery mechanism to avoid voluntary churn. [Learn more](https://docs.recurly.com/docs/backup-payment-method)

## Using the feature

To make the best of the wallet feature, merchants need to be aligned with certain prerequisites:

- For new merchants, features like "Credit Invoices" and "Only Bill What Changed" are enabled by default. However, legacy sites may need to manually activate these feature flags.
- Using the latest API versions ensures compatibility.
- The feature needs to be integrated into the Recurly contract. For setup or queries, merchants can contact the Recurly support team at [support@recurly.com](mailto:support@recurly.com).

## Management capabilities

### Definitions

- **Billing Info**: It pertains to the details associated with each payment method, like the card number, address, IP address, etc.
- **Payment method**: the funding source for making transactions. Such as credit or debit cards, bank account, PayPal.
  - **Primary Payment Method**: The primary or default payment method for transactions unless specified otherwise.  
    Endpoints have been designed for:

1. **Creation**: When a new billing info is introduced, it's automatically set as the primary info.
2. **Modification**: Existing billing info can be updated or a new primary can be designated.
3. **One-time Purchases & Subscriptions**: Specific billing info can be allocated or modified during these transactions.

### Accounts & subscriptions

- **Account Creation**: Every new billing info gets a unique ID, facilitating its use in various transactions.
- **Max Limit**: An account can store up to 20 billing infos.
- **Subscription Nuances**: By default, subscriptions tap into the primary billing info. But there's flexibility to assign specific billing methods or change them as needed.

### Payment Method and subscriptions

- Adding the first payment method to an account automatically makes it the primary payment method.
- Subscriptions default to the primary payment method when no specific billing_info_id is set. If a new primary payment method is added, these subscriptions will switch to it.
- Setting a specific billing_info_id on a subscription allows it to use a non-primary payment method.
- A subscription can be assigned to a current primary payment method by setting its billing_info_id. If the primary payment method changes, the subscription continues using the one initially set as primary.
- If a subscription's assigned payment method (specific billing_info_id) is deleted, the subscription defaults to the account's primary payment method.
- Deleting all payment methods on an account with active subscriptions may lead to subscription expiration unless a new payment method is added.

### Invoices

The billing information is crucial for invoicing:

- Invoices generated via API use the billing info provided in the request, a specified billing_info_id, or default to the account's primary billing info if none is provided.
- Past due invoices can have their associated billing info updated via API for collection attempts.
- Unpaid or past due invoices default to the primary payment method unless a specific payment method is set on the invoice.
- Updating billing info triggers an attempt to collect on all unpaid invoices associated with that billing info.

### Deleting billing infos

- Merchants can delete a customer's non-primary billing infos stored on the account.
- The sole primary billing info on an account can be deleted.
- To delete the primary billing info when multiple are present, a new primary must be set first, followed by deletion of the former primary.

> **Note:** Subscriptions or invoices linked to a deleted billing info will switch to the primary billing info for future charges or retries, unless a new billing info is specified.

### Manual collection method

- Subscriptions or invoices set to Automatic Collection Method default to the primary billing info unless otherwise specified.
- Subscriptions or invoices under Manual Collection Method do not require billing info.
- Switching a subscription from Automatic to Manual Collection Method removes any assigned billing info.

## Recurly app admin UI

The Recurly admin console supports the wallet feature, currently offering a read-only view. The supported payment methods are displayed neatly, including popular options like Visa, MasterCard, PayPal, and Amazon Pay.

## Exports

Wallet is supported in the Accounts Export and the billing_info Export:

**Accounts Export** (VERSION 4 - 12/10/20) additions and updates:

- The `tax_location_valid` column, based on the specific billing info in each row.
- New columns added at the end of the export, before any custom field columns:
  - `primary_payment_method` column, indicating TRUE or FALSE if the billing info is the primary payment method.
  - `billing_info_id`, displaying the ID of the billing info.  
    **billing_info Export** (VERSION 5 - 12/3/20) additions:
- A new `primary_payment_method` column, showing TRUE or FALSE based on if the billing info is the primary payment method.
- `billing_info_id`, displaying the ID of the billing info.

## Hosted pages

- Recurly’s hosted pages will only display the primary billing info for management purposes.
- Editing non-primary billing info is not currently available via Hosted Account Management pages.

## Payment gateway & account updater support

- Payment routing features compatible with Wallet include:
  - <a href="https://docs.recurly.com/docs/custom-gateway-routing-configuration" target="_blank">Custom Gateway Routing</a>.
  - <a href="https://docs.recurly.com/docs/gateway-failover" target="_blank">Gateway Failover</a>.
  - <a href="https://docs.recurly.com/docs/account-updater" target="_blank">Account Updater</a>.

## Wallet and account hierarchy feature support

Wallet is seamlessly integrated with the Account Hierarchy feature, including Invoice Roll-up.

### Supported use cases

**Child billing self**

- Can use the primary payment method for billing.
- Can use a specific payment method for billing.
- The backup payment method from the child account will be used if an invoice fails.

**Parent billing self**

- Can use the primary payment method for billing.
- Can use a specific payment method for billing.
- The backup payment method from the child account will be utilized if an invoice fails.

**Child billing parent**

- Can bill using the primary billing info from the parent account.
- Can bill using specific billing info from the parent account.
- Backup payment method from the parent account is used if an invoice fails.
- Aggregate invoices will combine from a single child account when set to use the same billing info as the parent account.
- Invoice Roll-up will combine invoices from multiple child accounts set to use the same billing info as the parent account.

### Important remarks

- When changing the `bill_to` account, all invoices must be paid (as per current functionality).
- Subscriptions will default to the primary payment method from the new `bill_to` account after a change, until a different payment method is specified.
- Changing the `bill_to` for an account clears any previously set `billing_info_id` on a subscription. If the `bill_to` changes again, subscriptions will default to the primary billing info of the `bill_to` account until a new `billing_info_id` is set.
- Uninvoiced charges will be included in the next invoice creation, using the associated payment method.

## Other Recurly feature support

- Wallet integrates with the Calendar Billing feature. Subscriptions set to Align or Aggregate onto the same invoice will do so if they use the same payment method.
- In cases where a subscription upgrade/downgrade request is made, and the site setting requires all invoices to be successfully paid, a collection attempt will be made on each invoice, regardless of the associated payment method.

# Additional notes

- Wallet is compatible with all payment methods supported by Recurly ([see the list of supported payment methods](https://go.recurly.com/rs/439-LSC-903/images/PaymentOptions_Data-Sheet.pdf)).
- Refunds are processed back to the original payment method used for the transaction.
- To change the billing info for the next recurring charge, update the billing info before the next charge is due.
- For an "immediate change" in subscription, update the billing info before making the change.
- Recurly's email templates will only include the primary billing info.
- Third-party integrations like NetSuite, Salesforce, and Zendesk will only display the primary payment method and details, specifically if the primary payment method is a credit card.
- The ability to list site’s accounts (GET /accounts) will return only the accounts and the primary billing info.
- Recurly's fraud prevention measures apply at the account level, not at the individual billing info level.
- Wallet supports 3DS flows in compliance with the PSD2 mandate. Transaction challenges are linked to the specific billing info initially attempted.
- Wallet is not compatible with certain features, including Auth and Capture, Adyen HPP, and the Verify Billing Info Endpoint.