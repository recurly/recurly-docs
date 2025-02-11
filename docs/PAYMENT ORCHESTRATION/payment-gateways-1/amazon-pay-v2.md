---
title: Amazon Pay V2
excerpt: >-
  Amazon Pay V2 on Recurly offers a streamlined, secure way for customers to pay
  using their Amazon account information. It enhances the subscription
  experience by leveraging familiar Amazon payment methods.
deprecated: false
hidden: true
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

### Prerequisites & Supported Gateways

- Recurly account setup.
- Amazon Pay Seller account.
  - Ensure <https://api.recurly.com/> is allow-listed in Amazon.
  - Ensure you have a webhook endpoint set up in your Integration configuration in Amazon. See **Enabling IPN Notifications / Webhooks** below.
- Integration requires Recurly.js or HPP
- Supported in the US, with Europe, and the United Kingdom coming soon.

### Limitations

- Amazon Pay V2 now supports full name, email, and billing address retrieval from Amazon via scopes. Using invoice previews for tax calculation can be used.
- Amazon Pay V2 does not yet support shipping address provision from Amazon. Shipping Address details must be provided to Recurly.

### Use cases

- Subscriptions and one-time transactions for customers preferring Amazon Pay.
- Businesses targeting Amazon's vast user base for increased convenience.

# Description

Amazon Pay V2 integration with Recurly simplifies the transaction process. It allows customers to use their existing Amazon-stored payment methods for subscribing to services or making purchases, providing a familiar and trusted payment environment.

Recurly offers more ways for your customers to transact, providing the trust and convenience of Amazon Pay. Amazon Pay simplifies the process for hundreds of millions of Amazon customers, allowing them to subscribe to your plans using the payment methods already stored in their Amazon accounts. Recurly streamlines the setup process, making it quick and easy to integrate with your Recurly site.

# Key details

| Feature                         | Description                                                                                     |
| ------------------------------- | ----------------------------------------------------------------------------------------------- |
| Services that work with Recurly | One Time Purchases, and Subscriptions                                                           |
| Supported operations            | Purchase, Refund, Verify, Void                                                                  |
| Supported payment types         | [Amazon Support](https://www.amazon.com/gp/help/customer/display.html?nodeId=GFBWMNXEPYVJAY9A)  |
| Supported card brands           | [Amazon Support](https://www.amazon.com/gp/help/customer/display.html?nodeId=GFBWMNXEPYVJAY9A)  |
| Gateway Specific 3DS2 Supported | Yes (UK / EUR regions only)                                                                     |
| Card on File Supported          | Yes                                                                                             |
| Regions                         | Everywhere AmazonPay is supported                                                               |
| Currencies                      | USD, GBP, EUR, DKK, ZAR, SEK, JPY, CHF, NZD, HKD, AUD                                           |

## Amazon support

Recurly supports Amazon Pay in the US, as well as the UK and Europe. Within the UK and Europe, 3DS and Multi-currency are supported through Recurly.js.

## Sign up for an Amazon seller account

To use Amazon Pay, you'll need to sign up for an Amazon Pay Seller account. This is a free online process. If you already have an Amazon Pay account, simply log in.

After signing up, you should follow Amazon's Getting Started Guide, which guides you through completing your account configuration.

1. **Subdomain**: Add your Recurly subdomain to your Amazon allowed JavaScript origins. [Learn more](#) about adding a website to an Amazon security profile.
2. **Testing**: Conduct validation of your Amazon Pay integration.
3. **Go Live**: After successful testing, switch your Amazon Pay account to Production mode.

**Note**: Ensure you are choosing the correct AmazonPay tile. If you've got a UK or EU seller account, do not authenticate through the US AmazonPay tile.

## Amazon Pay support in Europe and the United Kingdom

Recurly enables transactions in the following regions and currencies:

- Europe region with Euros (EUR), Australian Dollar (AUD), British Pounds (GBP), Danish Krone (DKK), Hong Kong Dollar (HKD), Japanese Yen (JPY), New Zealand Dollar (NZD), South African Rand (ZAR), Swedish Krone (SEK), Swiss Franc (CHF), and United States Dollar (USD).
- United Kingdom with British Pounds (GBP), Euros (EUR), Australian Dollar (AUD), Danish Krone (DKK), Hong Kong Dollar (HKD), Japanese Yen (JPY), New Zealand Dollar (NZD), South African Rand (ZAR), Swedish Krone (SEK), Swiss Franc (CHF), and United States Dollar (USD).

To integrate Amazon Pay in Europe and the UK, be aware of some regional-specific differences. You need to have a Seller Central account from the respective UK or EU Amazon website and set the billing region accordingly when using Recurly.js.

## Sign up for Amazon in Europe and the United Kingdom

Firstly, sign up for an Amazon Pay account tailored for the EU or UK. If you already have an Amazon Seller Central account in the UK/EU, just log use your existing account.

## Enabling IPN Notifications / Webhooks

Within your Amazon Seller Central account:

1. Click on the Gear icon in the upper right corner navigation.
2. Choose **Integration Settings**. 
3. Under **Instant Notification Settings**, choose **Edit** and add your site's callback URL. Use the URL format below and replace `<merchantsubdomain>` with your own site.
   1. Callback URL format:  `https://callbacks.recurly.com/amazon_v2/<merchantsubdomain>`
4. Click **Update** to finalize your settings.

## Adding the gateway

The Amazon Pay gateway employs a redirect method for secure account authorization and to obtain processing credentials. To start, select the Amazon Pay V2 option from your Gateway choices in Recurly. This action redirects you to the Amazon website corresponding to your business entity's location.

- **For US-based entities**: You'll be directed to the US Amazon Seller Central website for login.
- **For UK or EU-based entities**: The UK/EU Amazon Seller Central website is your destination for login. Ensure your Business Entity is located in the correct country in order to be redirected properly.

After authenticating your Amazon Seller credentials, simply provide approval for Recurly to handle processing on your behalf. You'll then be redirected back to your Recurly dashboard, where you can conduct sandbox transactions or set up for live operations.

> 📘 Redirection Note:
> 
> Amazon will display a notice that you will be redirected to a specific URL. Do **NOT** copy/paste the URL -- this will cause a 404 response. Please click the button that says 'Transfer API Keys'.

**Note**: Transactions will not be processed in Recurly's sandbox environment. However, Amazon Pay credentials are valid in both Recurly development and production accounts. To test your Amazon Pay transactions, you can put your Recurly sandbox into development mode. To commence live transactions, your Amazon Pay account and Recurly account must be in production mode.

## Integration

Once your Amazon Pay accounts are set up and your Recurly site is configured, the next step is to integrate Recurly.js into  your subscription checkout process.

> **Note:** It's crucial to understand that the Version 1 (V1) library of Amazon Pay is not supported with Amazon Pay Version 2 (V2). Instead, you should use standard "Recurly.js" functionality for integration. This distinction is essential to avoid any confusion and ensure a smooth integration process. Make sure to refer to the latest documentation and integration guidelines provided by Amazon Pay and Recurly for accurate and up-to-date instructions.

Recurly seamlessly integrates Amazon Pay V2 into Recurly.js, simplifying its addition to your transaction flow. Interactions primarily occur through the standard Recurly.js process, with the initial Amazon login as the only external site experience.

Once customers select their Amazon payment details for the subscription, the Amazon Charge Permission ID (`id`) is returned to Recurly and is tokenized using Recurly.js. The Recurly.js token is then utilized with Recurly's create subscription API as the account's billing information.

Incorporating Recurly.js is essential for integrating Amazon Pay V2 with your Recurly account. It also includes a pricing module to enhance the checkout experience by allowing a preview of the purchase. There is no longer a need to utilize the Pay with Amazon library utilized with V1.

## Merchant and Buyer Data Support

Recurly sends additional data to Amazon on subscriptions and transactions, based on data available for a given merchant site, subscription plan, or invoice description.

Recurly will send the following information: 

- Merchant DBA as Seller Store Name
- Transaction Description as Buyer Notes
  - For Subscriptions, this will be the Plan name
  - For One-time charges, this will be the Invoice Description, or Item Description depending on your workflow.

## Standard subscription

This section outlines the basic setup for Amazon Pay using Recurly.js, demonstrating standard configurations for a seamless integration.

## Setting the Amazon Pay region in Recurly.js

For transactions through Amazon Pay EU/UK, merchants must specify a region code in Recurly.js requests (options.region). Failing to set the region results in Recurly will cause transactions to default to US settings, including currency selection of USD. This oversight can lead to declines in one-time transactions, initial subscription transactions, and subscription renewals. For detailed guidance, refer to the [Recurly developer hub](#).

## Handling 3DS and PSD2 requirements for UK/EU integrators

UK or EU merchants must incorporate the 3DS into their flows to comply with SCA and PSD2. Amazon Pay V2 requires standard usage of Recurly.js 3DS behaviors. If you are already handling this in your Recurly.js setup, you can continue without any changes. If you are not yet handling [3DS behaviors in Recurly.js](https://recurly.com/developers/reference/recurly-js/#3d-secure), please see our developer hub for more information.

## Handling amazon shipping addresses

Currently, Amazon's integration does not support providing shipping addresses from Amazon accounts. To ensure transaction accuracy, especially for transactions involving physical product shipments, it's recommended to prompt customers for shipping address details separately.

## Subscription management

When integrating Amazon Pay with your subscription checkout, customers first authenticate with their Amazon credentials. They can then confirm their payment details, granting charge permission ID for the subscription.

Upon subscription confirmation, the customer's Amazon information, including the charge permission ID, is stored with Recurly. For subsequent renewals, this ID is used for automatic billing.

Customers can modify their charge permission ID through Amazon or Recurly:

- **Amazon**: Customers can update or cancel the charge permission ID for their subscription plan via their Amazon account.
- **Recurly**: Update billing information with a new Amazon Charge Permission ID or a different payment method using Recurly’s [update billing info](https://docs.recurly.com/api/billing-info). Customers must reauthenticate through Amazon to change their billing information through Recurly.js.

## Amazon references in Recurly Admin and Reporting

In the Recurly Admin interface, under the Billing Info section of an Account Details page, you can view details of Amazon Pay usage. This includes the Amazon Charge Permission ID and corresponding Refund and Charge IDs, facilitating customer service and reporting alignment between Recurly and Amazon.

Recurly stores several details relating to Amazon transactions in Gateway Parameters in UIs and APIs including: 

- Charge Permission ID
- Capture Amount
- Transaction Status (at Amazon)
- Creation, Updated, and Expiration Timestamps
- Charge ID (formerly Auth and Capture ID in V1)
- Currency Code 
- Capture Now indicator

## Testing your implementation

To test transactions, create a secondary Amazon account, as transactions cannot be processed through your own Seller Central account. This ensures an accurate testing environment.

Please note, that Amazon V2 sandbox does not support fully testing 3DS flows.

## Migrating from Amazon Pay V1 to Amazon Pay V2

Amazon Pay V1 relied on widgets and a distinct library external to Recurly.js, utilizing Billing Agreement IDs. With Amazon Pay V2, these elements are obsolete, as it integrates directly with Recurly.js. For detailed information on the transition, consult the [Amazon V2 specific Recurly.js documentation](https://recurly.com/developers/reference/recurly-js/#amazon-pay-v2).

Existing Amazon Pay V1 subscriptions can automatically transition to Amazon Pay V2 upon gateway activation, unless a specific gateway code was assigned. In such cases, a script update is necessary post-activation. HPP one time and initial subscription transactions will automatically use V2 if enabled.

Amazon Pay V1 will remain operational until 2024, and updates to this guide will reflect any new information from Amazon.

# FAQs

**Q: Are Amazon Pay Charge Permission IDs usable everywhere on Amazon?**  
**A:** Amazon Pay charge permission IDs are specific to the region where they were created. To switch regions for a user, a new charge permission ID must be generated in the respective region.

**Q: Can I pull shipping addresses from Amazon Pay V2?**  
**A:** Shipping addresses from Amazon Pay V2 need to be passed via API parameters. Updates will be provided if this feature is added in the future.

**Q: Will Amazon Widgets be available in V2?**  
**A:** Amazon Widgets are not supported in Amazon Pay V2.

**Q: Do I need to use the Amazon library for Amazon V2?**  
**A:** No, Amazon Pay V2 is integrated into Recurly.js, so the separate Amazon library is not needed. Amazon Pay V2 is not supported by the Amazon library.

**Q: I don't see a consent widget in Amazon Pay V2. Is this unavailable?**  
**A:** In Amazon Pay V2, consent is obtained on the Amazon Pay hosted page, eliminating the need for a separate consent widget.

**Q: Do I need to use any other gateway to access Amazon Pay V2?**  
**A:** No, Amazon Pay V2 is a standalone service and does not require any additional gateways or merchant accounts outside of Amazon.

**Q: What happens if I cannot authorize or authenticate via hosted onboarding?**  
**A:** Check the accuracy of your Amazon Seller Central credentials. For US accounts, ensure the business entity is located in the United States; for UK or EU accounts, the entity should be in the UK or an EU country.

**Q: Which currencies are available for Amazon Pay in the US?**  
**A:** In the United States, USD is the available currency for Amazon Sellers.

**Q: Which currencies are available on Amazon Pay in the UK or EU?**  
**A:** For sellers in the UK, GBP is available, and for those in the EU, EUR is available.

# Version history

- As of December 2023, Amazon Pay V2 is available.