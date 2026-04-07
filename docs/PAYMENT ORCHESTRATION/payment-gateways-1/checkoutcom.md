---
title: Checkout.com
excerpt: >-
  Connect Checkout.com to Recurly for card and wallet payments, 3D Secure, and
  webhook-based verification.
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

<Callout icon="👍" theme="okay">
  **Early Access**
  Checkout.com is currently available in Early Access. Interested merchants can contact [support@recurly.com](mailto:support@recurly.com) to gain access.
</Callout>

### Required plan

This feature or setting is available to all customers on any Recurly subscription plan.

### Requirements

* Ensure you have your Business Entity Merchant Category Code filled in properly.

### Limitations

<Callout icon="📘" theme="info">
  ## **Important note:**

  Checkout.com gateway requires Browser Information in all transactions, so using Recurly.js for new signups and new billing information entry, such as billing info updates, regardless of 3DS usage, is important. You may use Recurly.js for either by following our standard guides for 3DS with Recurly.js. If you need 3DS on known billing information, you may also find our guide for known billing information found in our Integration Guides: [Recurly.js with Stored Billing Information](https://docs.recurly.com/recurly-subscriptions/docs/using-3d-secure-with-stored-billing-information)
</Callout>

* Using the API to send in raw card details, or billing info IDs without using Recurly.js will not be supported due to the gateway's strict browser information requirement. Browser details are collected automatically when using Recurly.js.
* When enabling 3D Secure, the service is not immediately active after adding the gateway account. There is a behind-the-scenes enrollment process that must be completed. Please allow 3 business days for this process to be completed.
* Swapping site modes at will is not supported. Ensure you've got two separate sites for production and development testing to avoid issues.
* Gateway Tokens and Chargeback Notifications are not supported at this time.

# Definition

The integration of Checkout.com with Recurly facilitates a smooth pathway for managing your financial transactions. Whether you are a new merchant working with Checkout.com or you're an existing merchant migrating to the gateway, the process is designed to be straightforward and efficient.

For pricing and signup information for a new production Checkout.com account, please check with your gateway provider point of contact.

| Features & Specifications       | Description / Availability                                                                                                                   |
| :------------------------------ | :------------------------------------------------------------------------------------------------------------------------------------------- |
| Services that work with Recurly | Recurring Subscriptions, Payments (eCommerce and [MOTO](https://docs.recurly.com/recurly-subscriptions/docs/moto-transactions#/)), 3D Secure |
| Supported Operations            | Authorize and Capture, Purchase, Refund, Verify, Void, Recurring, Unscheduled MIT                                                            |
| Supported Payment Types         | Credit Card, Apple Pay, Google Pay                                                                                                           |
| Supported Card Brands           | Visa, MasterCard, Amex, Discover, JCB, Diners Club, Union Pay                                                                                |
| Unified 3DS2 Supported          | Yes                                                                                                                                          |
| Card on File Supported          | Yes                                                                                                                                          |
| Regions                         | Worldwide                                                                                                                                    |
| Currencies                      | All supported currencies.                                                                                                                    |
| Additional Feature Support      | Billing and Shipping Information, Level 2 Data, Dynamic Descriptors,  AVS / CVV Checks, and Line Item Passthrough                            |

# Setup Checkout.com with Recurly

To enable seamless communication between Recurly and your Checkout.com account, it is essential to configure your API credentials within Recurly.

## Step 1: Obtain your Checkout.com credentials

* You'll need to obtain your credentials from your Checkout.com account directly, and ensure you have them available for entry in Step 2.
  * **Sign in** to your Checkout.com dashboard and click **Developers** from the top navigation and click **Keys**.
  * **Select** **Create a new key**. When creating keys, it is not advised to _Customize_ your key permissions unless you are certain no functionality is blocked by the scopes chosen.
    * **Note**: If you must limit scopes, ensure you have at least payments, gateway, disputes, search, and risk enabled. While we do not support all of these options presently, we want to ensure no limitations or issues arise from required key changes for future iterations of this gateway.
* You can find distinct documentation on Checkout.com website: [Access and/or Create API Credentials](https://support.checkout.com/hc/en-us/articles/14327309405842-Create-new-API-keys) and in [Dashboard documentation](https://www.checkout.com/docs/business-operations/use-the-dashboard/developers#Manage_API_authentication) for Checkout.
* **Note:** If you intend to use 3DS, you will also need the following information:
  * Your Acquirer BIN (6 digits)
  * Your Acquirer Merchant ID
  * Your Acquirer Country
* To create your Source Verification Key, you must set up Webhooks within Checkout. Proceed to Step 2.

## Step 2: Configure webhooks in Checkout.com

* **Navigate** to **Developers > Webhooks** and select 'Create configuration'.
* **Enter** a descriptive name, and the webhook destination URL as follows: [https://callbacks.recurly.com/checkout/merchant-subdomain](https://callbacks.recurly.com/checkout/merchant-subdomain),  replacing  "merchant-subdomain" with your Recurly site's actual subdomain. Example: If your Recurly subdomain is '**mywebsite**', you would enter `[https://callbacks.recurly.com/checkout/mywebsite](https://callbacks.recurly.com/checkout/mywebsite) in this configuration.
* You will select specific event types. To avoid having to make changes in the future, simply select all events. At minimum ensure you have payment events and dispute events.
* **Keep** your Signature key (Source Verification Key) for setup inside Recurly.

## Step 3: Enter your Checkout.com credentials in your Recurly site

* **Navigate** to **Configuration > Payment Gateways**and **Select** Checkout.com from the options available.
* **Enter** the details you've obtained from your Checkout.com configuration into the following fields:
  * Your API Public Key
  * Your Channel ID
  * Your API Secret Key
  * Your Source Verification Key

## Step 4: Enable 3D Secure

If you are choosing to enable 3DS, you must select **Enable 3D Secure** as well as enter the following details.

**Note:** You will also want to ensure the consumer-facing website domain (url) **and** your business' main MCC value are both present in your Default Business Entity before enabling 3DS.

* Your Acquirer BIN, Acquirer Merchant ID, and Acquirer Country.
* You can obtain these by speaking to Checkout.com directly.

## Step 5: Enable Currencies

You can add as well as **change** which currencies your Checkout.com gateway can accept. Please choose from available currencies depending on which you are approved to accept.

<Image align="center" border={true} width="80% " src="https://files.readme.io/c4a227a-image.png" className="border" />

## Step 6: Add or Update your gateway

Once your configuration is set up the way you would prefer, **click** ‘Add Payment Gateway’. If you are editing your implementation, the button will state ‘Update Payment Gateway’.

# Additional Configuration

## Address and Card Code Verification Enablement

If you haven't already, you can block mismatched Address and CVV code results on approved transactions, by configuring rules in **Configuration → Payment Settings**. If ‘Enabled’, if Recurly receives information in the transaction response that the Address or CVV provided does not match what the Issuer has on file, the transaction will be rejected. **Please note**, these settings apply to all supported gateways and will not be Checkout.com specific.

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

<Image align="center" border={true} width="80% " src="https://files.readme.io/9306094-image.png" className="border" />

## Test your integration

1. In your Recurly account, **navigate** to `Configuration → Payment Gateways`.
2. Choose your new Checkout.com integration and click **Click** on `Options > Test Configuration` to ensure that Recurly can successfully communicate with your Checkout.com account.

   If you have provided your credentials correctly, you will see a confirmation message.

## Go Live!

1. Once you’ve successfully tested the integration, you are ready to accept real transactions.
2. Monitor your transactions in Recurly and  Checkout.com to ensure everything is working smoothly.

> **Note:** Ensure that you comply with PCI regulations when handling sensitive credit card information.

This guide is designed to walk you through the process of integrating  Checkout.com with Recurly, configuring key features, and ensuring that everything is set up to start processing payments securely and efficiently. Always consult with your Checkout.com representative or Recurly support for any specific questions or issues related to your integration.

# Production and Sandbox behavior

Production and Sandbox environments are entirely different endpoints and systems. If you create a Checkout.com gateway account while your site is in Production or Sandbox mode, you can control whether or not these transactions are using the sandbox / production endpoints easily.

If you have support move your site from Production/Sandbox **to** Development mode, or visa versa, you will need to create new gateway tiles, and disable the old ones as they will not be functional post site-mode migration. To that end, it is best practice to have your site remain in the same 'mode', and if you have a specific development site that you use for integration testing and other testing scenarios, ensure your site is set to and stays in Development mode for the duration and prior to adding accounts to avoid issues.
