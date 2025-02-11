---
title: Tax location validation
excerpt: >-
  Automate tax compliance with Recurly's Tax Location Validation, ensuring
  accurate tax collection based on customer location.
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

- Integration with Recurly's API or select client libraries.
- Subscription to Recurly's out-of-box tax solution or direct integration with Avatax and Vertex.

### Limitations

- Manual collection invoices are not supported for Tax Location Validation.
- Certain payment methods may not support BIN country lookup.

# Definition

Recurly's "Tax Location Validation" feature ensures compliance with tax regulations in specific regions by automatically verifying the customer's country through two pieces of evidence before tax collection on digital services.

# Key benefits

- **Automated compliance**: Streamline tax collection processes by automating location validation.
- **Enhanced accuracy**: Ensure accurate tax application based on verified customer location.
- **Support for multiple regions**: Stay compliant across various regions including Australia, the European Union, New Zealand, and the United Kingdom.

# Supported regions

In the rapidly evolving landscape of digital services taxation, a growing number of countries are implementing regulations that require two distinct pieces of location evidence for accurate tax application. Recurly's Location Validation feature is tailored to support these regulatory requirements for the following regions:

- **Australia**
- **European Union** (inclusive of the United Kingdom until 12/31/2021)
- **New Zealand**
- **United Kingdom** (effective from 1/1/2021)

# How tax location validation works

Recurly's Tax Location Validation is designed to be both proactive and dynamic. While the actual location evidence is essential for invoice generation, the validation process is initiated the moment an account's taxable address is either added or updated. By the time an invoice is prepared, Recurly assesses the account's status. If the account meets the validation criteria, the invoice is posted. Conversely, if the account is deemed invalid, the invoice generation is halted.

The determination of an account's taxable address hinges on the "Use Account Info Address on all Invoices" setting, which can be located under Configuration > Taxes > Tax Settings on the Tax Settings page.

- If this setting is **disabled**, the Billing Address is treated as the taxable address.
- If **enabled**, the Account Address is considered the taxable address.

> **Note:** For manual collection invoices, only the Account Address is used. However, these are not compatible with Tax Location Validation. More details on this are provided in the "Manual Invoices Not Supported" section below.

The validation is activated for any taxable address update where the country falls within the enabled validation regions (Australia, the European Union, or New Zealand). Furthermore, the address should not have a VAT number (for Australia, the VAT number can be present, but it shouldn't qualify for an exemption). The validation process cross-references one additional piece of country evidence against the country of the taxable address. If there's no match, the validation is deemed unsuccessful, and the account is marked as invalid. However, it's important to note that a failed validation won't impede the address update.

For accounts where the taxable address is the **Billing Address**, the validation checks the following fields for a country match:

1. Account Address Country
2. IP Address Country
3. Credit Card BIN Country

Conversely, if the taxable address is the **Account Address**, the following fields are cross-referenced:

1. Billing Address Country
2. IP Address Country
3. Credit Card BIN Country

## Billing address

The Billing Address can serve dual purposes: it can either be the primary taxable address or act as supplementary evidence. This is particularly useful when payment methods such as credit cards, PayPal, or Amazon are involved.

- For PayPal transactions initiated via Recurly's Hosted Payment Pages, the customer's country is automatically provided.
- However, if the PayPal transaction is processed through Recurly.js, it's imperative to separately collect the country information from the customer. Subsequently, a second "Update Billing Info" API call should be made to store the country details before finalizing the subscription.

## Account address

The Account Address can be utilized as the primary taxable address or as an auxiliary piece of evidence. Typically, this address is used to record the customer's shipping or mailing details.

- For those using Pay with Amazon, there's an option to replicate the returned address into the Account Address.

## IP address

The IP Address associated with the Billing Information can act as a supplementary piece of evidence, especially when payment methods like credit cards, PayPal, or Amazon are in play. Recurly captures and retains the customer's IP address whenever they interact with a Hosted Page (be it Hosted Payment Pages or Hosted Account Management) for adding or updating Billing Information, or when actions are executed via Recurly.js. Merchants also have the flexibility to input their own collected IP address through the Billing Info API.

- Given the occasional inaccuracies associated with IP Address-based location validation, it's advisable to gather both the Billing Address and Account Address from customers, especially when the Credit Card BIN isn't accessible (as is the case with PayPal or Amazon).

## Credit card BIN

For those collecting credit card details from customers, the Credit Card BIN (Bank Identification Number) of the Billing Information can serve as an additional piece of evidence. The BIN is essentially an identifier for the credit card's issuing bank. Recurly employs a BIN lookup to ascertain the bank's country. Typically, the country of the bank aligns with the customer's billing address country. In instances where they don't match, it's often indicative of fraudulent activity. The Credit Card BIN country is cross-referenced every time Location Validation is executed. The BIN, along with the returned country, is displayed on the account's Billing Info under the "BIN" field.

- It's worth noting that payment methods like PayPal and Amazon don't support BIN country lookup since Recurly doesn't have access to the actual credit card number.

# Enable tax location validation

Activating Tax Location Validation is a straightforward process. Simply navigate to the Tax Settings page in your Admin Console, which can be found under Configuration > Taxes > Tax Settings.

- For **Australian** customers, activate the "GST Location Validation" under the "Australia Settings" section.
- For customers in the **European Union**, toggle on the "VAT Location Validation" under the "European Union VAT Settings".

![VAT Location Validation](https://files.readme.io/b331d07-vat-location-validation.png "vat-location-validation.png")

- For **New Zealand** customers, enable the "GST Location Validation" under the "New Zealand Settings".

Upon enabling the Tax Location Validation feature, Recurly will initiate a validation process for all accounts that:

- Possess a taxable address within the activated region (Australia, European Union, or New Zealand).
- Lack a VAT Number or GST Number associated with that taxable address (For Australia, the absence of an exemption qualified ABN is also a criterion).
- Currently maintain an active or future subscription.

If there's a modification in the "Tax Calculation Address" on the Tax Settings page, either by enabling or disabling the "Use Account Info Address on all Invoices" option, Recurly will re-run the validation for all your accounts that fit the aforementioned criteria. However, this time, the alternate address will be treated as the taxable address for the account.

When tax location validation is executed on your existing accounts, Recurly will send notifications to your Billing Contact email address for each account that is deemed invalid.

# Identify valid and invalid accounts

Determining an account's validation status can be achieved through various means:

## Email to billing contact

In situations where an address update results in an account being marked as invalid, Recurly will dispatch an email to your designated Billing Contact email address, providing the account code of the affected account. It then becomes imperative to liaise with the customer to incorporate a second piece of location evidence to the account. If this isn't done before the subscription renewal, the subscription will lapse upon renewal.

[block:image]{"images":[{"image":["https://files.readme.io/f7f7a73-eu-email.png","eu-email.png","VAT Location Validation Email"],"align":"center","sizing":"50% ","border":true}]}[/block]

[block:image]{"images":[{"image":["https://files.readme.io/239df9d-nz-email.png","nz-email.png","GST Location Validation Email"],"align":"center","sizing":"50% ","border":true}]}[/block]

## Accounts export

If Tax Location Validation for Australia, the European Union

, or New Zealand is activated on your site, the Accounts export will be augmented with two additional columns. These columns will provide insights into whether the account has undergone validation and its current status.

[View the comprehensive documentation on the Accounts export here.](https://docs.recurly.com/docs/export-overview#section-accounts)

| Column Name                  | Example     | Description                                                                                                                                                                                                                                                              |
| :--------------------------- | :---------- | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| tax_location_valid           | TRUE, FALSE | This column becomes visible only if your site has activated European Union VAT or New Zealand GST Location Validation. It indicates if the account has successfully passed the tax location validation process.                                                          |
| location_validation_tax_type | eu, nz      | This column, visible only if European Union VAT or New Zealand GST Location Validation is enabled on your site, denotes the region where the tax location validation was executed on the account. `eu` pertains to the European Union, while `nz` refers to New Zealand. |

## Admin console

Accounts that are marked as invalid will be flagged with a conspicuous red banner at the top of the account page within the Admin Console. This visual cue, however, won't be displayed on the Hosted Account Management page.

![VAT Location Validation Admin](https://files.readme.io/f160c95-eu-admin.png "eu-admin.png")  
![GST Location Validation Admin](https://files.readme.io/87002bb-nz-admin.png "nz-admin.png")

Furthermore, every instance of tax location validation, regardless of its outcome, is meticulously logged in the account's Activities section. A successful validation will detail the two pieces of evidence that corroborated, while a failed attempt will enumerate all four evidence options. This provides clarity on what was either missing or needs rectification.

[block:image]{"images":[{"image":["https://files.readme.io/70e453a-nz-failed-activity.png","nz-failed-activity.png","Failed Validation Activity"],"align":"center","border":true}]}[/block]

[block:image]{"images":[{"image":["https://files.readme.io/9b436bd-nz-passed-activity.png","nz-passed-activity.png","Successful Validation Activity"],"align":"center","border":true}]}[/block]

## How to rectify an invalid account

In the event that an account is flagged as invalid, it's incumbent upon you to collaborate with the affected customer to update their evidence options prior to the subscription renewal. Failing to do so will result in the subscription expiring upon renewal. The activity log within the Activities section of the customer's account can provide insights into which pieces of evidence were inconsistent. It's crucial to remember that the taxable address is the primary address. Therefore, you need to ascertain whether this was the Billing Address or the Account Address and then match against that. Simply finding a correlation between two pieces of evidence that don't include the invoice address won't suffice to validate the account. If the Billing Address is the taxable address, a straightforward solution is to confirm with the customer that their physical location aligns with their Billing Address. Subsequently, the Account Address can be updated to reflect that country.

# Subscription sign-ups

If a subscription sign-up activates the location validation and the validation doesn't pass muster, the purchase will be halted. The customer will be presented with the following error messages:

```xml EU
<errors>
    <error field="invoice.base" symbol="tax_invalid_location">You are located in the European Union but your country cannot be verified for VAT. Please try again or contact the merchant.</error>
</errors>
```
```xml NZ
<errors>
    <error field="invoice.base" symbol="tax_invalid_location">You are located in New Zealand but your country cannot be verified for GST. Please try again or contact the merchant.</error>
</errors>
```

It's worth noting that Recurly won't dispatch an email to your Billing Contact email address if a sign-up is thwarted due to Tax Location Validation. However, if you're leveraging our API and wish to monitor these failures, you can listen for the specific error message and log the form details on your end.

# Subscription renewal

At the juncture of renewal, if the account is validated, the invoice generation proceeds seamlessly, and the subscription is renewed. If the account is flagged as invalid, the subscription renewal is automatically aborted, culminating in the subscription's expiration. If the account hasn't been explicitly marked as valid or invalid, the Location Validation is reinitiated, the account is subsequently marked, and based on the outcome, either the invoice is generated or the subscription is terminated.

In scenarios where a subscription lapses due to Tax Location Validation, the reason for expiration will be cataloged as `Tax Location Invalid`. This specific reason can be gleaned from the Subscriptions - Churned export and the Churn Analysis report.

# Subscription modifications

If any modification to a subscription (be it an upgrade or downgrade) activates the location validation and the validation is unsuccessful, the modification will be halted. Both the customer and the Admin Console will be presented with the same error as detailed in the sign-up section above.

# Invoice evidence

When an invoice is successfully generated for an account that has met the tax location validation criteria, the two corroborating pieces of evidence are archived and can be retrieved from the "Invoices - Summary" export under the columns `invoice_country` and `evidence_matched`.

[For a comprehensive understanding of the Invoices - Summary export, click here.](https://docs.recurly.com/docs/export-overview#section-invoices-summary)

[block:image]{"images":[{"image":["https://files.readme.io/801c7f7-location-validation-invoice-export.png","location-validation-invoice-export.png","Invoices - Summary export"],"align":"center","border":true}]}[/block]

| Column Name      | Example                                                                                 | Description                                                                                                                                                                                                                                                              |
| :--------------- | :-------------------------------------------------------------------------------------- | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| invoice_country  | FR                                                                                      | This column, visible only if European Union VAT or New Zealand GST Location Validation is enabled on your site, displays the EU or NZ country code of the customer's address on the invoice. The country corresponds to the evidence_matched column.                     |
| evidence_matched | Account Info Country, Billing Info Country, IP Address Country, Credit Card BIN Country | This column, visible only if European Union VAT or New Zealand GST Location Validation is enabled on your site, enumerates the two pieces of evidence that matched when the invoice was generated. The corresponding country is reflected in the invoice_country column. |

# Manual invoices not supported

It's pivotal to understand that Tax Location Validation is only compatible with automatically collected invoices. Manual Invoicing remains outside the purview of Tax Location Validation. This is primarily because manual collection invoices invariably use the Account Address as the taxable address and often imply that the customer won't furnish billing information. In the absence of billing information, the three other evidence options (Billing Address, IP Address, and Credit Card BIN) are rendered moot. Consequently, the onus falls on the merchant to gather a second piece of location evidence for manual invoices and archive those details. One viable approach is to document the evidence details in one of the invoice notes sections prior to posting the invoice.

If your Tax Settings are configured to utilize the Account Info Address for all invoices, you might still encounter a validation notice on an account that can't be validated. However, if the subscription is set to Manual Collection, it won't lead to the subscription's cancellation. For Manual Collection subscriptions, such notices can be safely disregarded.

# Testing

Recurly's comprehensive Tax Location Validation can be thoroughly tested in sandbox mode to ensure seamless integration and functionality.

## Setting up tax location validation

- **Step 1**: Access your Recurly dashboard.
- **Step 2**: Navigate to Configuration > Taxes > Tax Settings.
- **Step 3**: Choose the desired region and enable the respective Location Validation option.

## Addressing invalid accounts

- **Step 1**: Identify invalid accounts using the red banner or account activities.
- **Step 2**: Communicate with the customer to update their evidence options.
- **Step 3**: Revalidate the account.

## Handling subscription renewals with tax location validation

- **Step 1**: Check the account's validation status.
- **Step 2**: If valid, proceed with the renewal and invoice creation.
- **Step 3**: If invalid, the subscription will automatically expire.

## Managing subscription sign-ups

- **Step 1**: If a sign-up triggers validation and fails, the purchase is blocked.
- **Step 2**: Display the error message to the customer.
- **Step 3**: Guide the customer to provide accurate location evidence.