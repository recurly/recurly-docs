---
title: Nuvei
excerpt: >-
  Set up Nuvei in Recurly to process cards and wallets, enable 3D Secure, and
  meet browser data requirements.
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

<Callout icon="👍" theme="okay">
  **Early Access**
  Nuvei is currently available in Early Access. Interested merchants can contact [support@recurly.com](mailto:support@recurly.com) to gain access.
</Callout>

### Required plan

This feature or setting is available to all customers on any Recurly subscription plan.

### Limitations

<Callout icon="📘" theme="info">
  ## **Important note**:

  Nuvei gateway requires Browser Information in all transactions, so using Recurly.js for new signups and new billing information entry, such as billing info updates, regardless of 3DS usage, is important. You may use Recurly.js for either by following our standard guides for 3DS with Recurly.js. If you need 3DS on known billing information, you may also find our guide for known billing information found in our Integration Guides: [Recurly.js with Stored Billing Information](https://docs.recurly.com/recurly-subscriptions/docs/using-3d-secure-with-stored-billing-information)
</Callout>

* Using the API to send in raw card details, or billing info IDs without using Recurly.js will not be supported due to the gateway's strict browser information requirement. Browser details are collected automatically when using Recurly.js.
* Swapping site modes at will is not supported. Ensure you've got two separate sites for production and development testing to avoid issues.
* Gateway Tokens and Chargeback Notifications are not supported at this time.
* Processing via the Admin UI may not be supported due to Nuvei's CVV and Customer IP address requirements. As these may be configurable with your gateway, please speak to your Nuvei representative if you need to run Admin transactions.

# Definition

The integration of Nuvei with Recurly facilitates a smooth pathway for managing your financial transactions. Whether you are a new merchant working with Nuvei or you're an existing merchant migrating to the gateway, the process is designed to be straightforward and efficient.

For pricing and signup information for a new production Nuvei account, please check with your gateway provider point of contact.

| Features & Specifications       | Description / Availability                                                                                                                   |
| ------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- |
| Services that work with Recurly | Recurring Subscriptions, Payments (eCommerce and [MOTO](https://docs.recurly.com/recurly-subscriptions/docs/moto-transactions#/)), 3D Secure |
| Supported Operations            | Authorize and Capture, Purchase, Refund, Verify, Void, Recurring, Unscheduled MIT                                                            |
| Supported Payment Types         | Credit Card, Apple Pay, Google Pay                                                                                                           |
| Supported Card Brands           | Visa, MasterCard, Amex, Discover, JCB, Diners Club, Union Pay                                                                                |
| Unified 3DS2 Supported          | Yes                                                                                                                                          |
| Card on File Supported          | Yes                                                                                                                                          |
| Regions                         | Worldwide                                                                                                                                    |
| Currencies                      | All supported currencies.                                                                                                                    |
| Additional Feature Support      | Billing and Shipping Information, Level 2 Data, Dynamic Descriptors,  AVS / CVV Checks, and Line Item Passthrough                            |

# Setup Nuvei with Recurly

To enable seamless communication between Recurly and your Nuvei account, it is essential to configure your API credentials within Recurly.

### Step 1: Obtain your Nuvei credentials

* You'll need to obtain your credentials from your Nuvei account directly, and ensure you have them available for entry in Step 2.
  * From the REST API **Configuration** tab, click **Generate New API Key**.
  * You will also need your Site ID, Merchant ID, Secret, and Source verification key.
* You can find distinct documentation on Nuvei's website: [Access and/or Create API Credentials](https://docs-apm.nuvei.com/generate-api-key/)
* **Note:** If you intend to use 3DS, you will also need the following information:
  * Your Acquirer BIN (6 digits)
  * Your Acquirer Merchant ID
  * Your Acquirer Country

### Step 2: Setup Nuvei webhooks

* Log into the Nuvei dashboard and navigate to **Settings > My Account**. Select the **Events Configuration** tab. Choose 'Client' from the dropdown.
* Locate the specific events and enter the webhook endpoint as follows: [https://callbacks.recurly.com/nuvei/\{\{your-subdomain}}](https://callbacks.recurly.com/nuvei/\{\{your-subdomain}}). You may need to repeat this step multiple times.
* Ensure the status is toggled to ON.
* Specific events: Chargeback, Chargeback/Dispute

### Step 3: Enter your Nuvei credentials in your Recurly site

* Navigate to **Configuration > Payment Gateways**and **Select** Nuvei from the options available.
* Enter the details you've obtained from your Nuvei configuration into the following fields:
  * Your Merchant ID
  * Your Site ID
  * Your Secret Key
  * Your Source Verification Key

### Step 4: Enable 3D Secure

If you are choosing to enable 3DS, you must select **Enable 3D Secure** as well as enter the following details.

**Note:** You will also want to ensure the consumer-facing website domain (url) **and** your business' main MCC value are both present in your Default Business Entity before enabling 3DS.

* Your Acquirer BIN, Acquirer Merchant ID (CAID), and Acquirer Country.
* You can obtain these by speaking to Nuvei directly.

### Step 5: Enable currencies

You can add as well as **change** which currencies your Nuvei gateway can accept. Please choose from available currencies depending on which you are approved to accept.

<Image align="center" border={true} width="80% " src="https://files.readme.io/c4a227a-image.png" className="border" />

### Step 6: Add or Update your gateway

Once your configuration is set up the way you would prefer, **click** ‘Add Payment Gateway’. If you are editing your implementation, the button will state ‘Update Payment Gateway’.

## Additional Configuration

### Address and Card Code Verification Enablement

If you haven't already, you can block mismatched Address and CVV code results on approved transactions, by configuring rules in **Configuration → Payment Settings**. If ‘Enabled’, if Recurly receives information in the transaction response that the Address or CVV provided does not match what the Issuer has on file, the transaction will be rejected. **Please note**, these settings apply to all supported gateways and will not be Nuvei specific.

**Enable Address Verification Checks**

1. In your Recurly account, **navigate** to `Configuration → Payment Settings`.
2. **Scroll** to the `Address Verification Check` section.
3. **Select** your desired AVS rules (e.g., Enabled (default) or Disabled).
4. **Click** `Save Changes`.

**Enable Card Code Verification (CVV) Checks**

1. In your Recurly account, **go to** `Configuration → Payment Settings`.
2. **Scroll** to the `Credit Card Verification Code Check` section.
3. **Set** the Radio Button option to ‘Enabled’. When Enabled, invalid or mismatched CVV code submissions will be rejected based on feedback from the card Issuer.
4. **Click** `Save Changes`.

<Image align="center" border={true} width="75% " src="https://files.readme.io/9306094-image.png" className="border" />

### Test your integration

1. In your Recurly account, **navigate** to `Configuration → Payment Gateways`.
2. Choose your new Nuvei integration and click **Click** on `Options > Test Configuration` to ensure that Recurly can successfully communicate with your Nuvei account.

   If you have provided your credentials correctly, you will see a confirmation message.

### Go Live!

1. Once you’ve successfully tested the integration, you are ready to accept real transactions.
2. Monitor your transactions in Recurly and  Nuvei to ensure everything is working smoothly.

> **Note:** Ensure that you comply with PCI regulations when handling sensitive credit card information.

This guide is designed to walk you through the process of integrating  Nuvei with Recurly, configuring key features, and ensuring that everything is set up to start processing payments securely and efficiently. Always consult with your Nuvei representative or Recurly support for any specific questions or issues related to your integration.

## Production and Sandbox behavior

Production and Sandbox environments are entirely different endpoints and systems. If you create a Nuvei gateway account while your site is in Production or Sandbox mode, you can control whether or not these transactions are using the sandbox / production endpoints easily.

If you have support move your site from Production/Sandbox **to** Development mode, or visa versa, you will need to create new gateway tiles, and disable the old ones as they will not be functional post site-mode migration. To that end, it is best practice to have your site remain in the same 'mode', and if you have a specific development site that you use for integration testing and other testing scenarios, ensure your site is set to and stays in Development mode for the duration and prior to adding accounts to avoid issues.
