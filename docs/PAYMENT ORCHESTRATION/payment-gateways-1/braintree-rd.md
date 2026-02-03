---
title: Braintree
excerpt: >-
  Integrate Braintree seamlessly into your Recurly account for efficient and
  secure payments processing.
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

* Braintree restricts usage of its gateway to certain business types. If your business is on the list of restricted business models described on Braintree’s <a href="https://www.braintreepayments.com/legal/acceptable-use-policy" target="_blank">Acceptance Use Policy</a>, you will not be able to use the Braintree gateway.
* Recurly does not support lifecycle webhooks or post-auth webhooks from the Gateway. If you are using gateway-level fraud review systems, gateway tokens, or are making transaction actions at the gateway, there is risk that Recurly and Braintree could be out of sync. It is advised to keep an eye on gateway-level fraud services, and ensure you are capturing, voiding, and processing refunds from Recurly instead of at the gateway.
* While we support dynamic descriptors for Braintree, they are only supported for card payments at this time.

# Definition

Braintree, a full-stack payment platform known for its robust support for mobile and online transactions, can be easily integrated with Recurly, allowing merchants to process payments effortlessly. Braintree supports multiple currencies, requiring a separate gateway configuration for each currency with Recurly.

> **Note**: Visit our [guide on testing your gateway configurations ](https://docs.recurly.com/docs/how-to-test-your-gateway)in Recurly to ensure your payment processes are set up correctly.

# Key details

| Features                        | Description/Availability                                                                                                                                                                                              |
| :------------------------------ | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Services that work with Recurly | Subscription Billing, One-time Payments, [Card Dynamic Descriptors](https://docs.recurly.com/docs/payment-descriptors#/), [MOTO](https://docs.recurly.com/recurly-subscriptions/docs/moto-transactions#/)  Processing |
| Supported Operations            | Authorize & Capture, Purchase, Refund, Void                                                                                                                                                                           |
| Supported Payment Types         | Credit/Debit Cards, PayPal, Venmo, Apple Pay, Google Pay                                                                                                                                                              |
| Supported Card Brands           | Visa, Mastercard, Amex, Discover, JCB, Diners, Union Pay                                                                                                                                                              |
| Gateway Specific 3DS2 Supported | Yes                                                                                                                                                                                                                   |
| Card on File Supported          | Yes                                                                                                                                                                                                                   |
| Regions                         | Global                                                                                                                                                                                                                |
| Currencies                      | Multiple (per merchant account ID). See <a href="https://docs.recurly.com/docs/currency-support-by-gateway" target="_blank">all available.</a>. PayPal currencies will be limited to PayPal supported currencies.     |
| Additional Feature Support      | Billing and Shipping Information, Level 2 Data, Visa Trial Descriptors, Braintree Gateway Tokens, Vaulting in Braintree, [MOTO](https://docs.recurly.com/recurly-subscriptions/docs/moto-transactions#/)              |

## Braintree and multi-currency

For merchants wishing to accept multiple currencies through Braintree, it is necessary to configure individual Braintree gateway instances for each currency. To do this, you will need your _Merchant ID_, _Merchant Account ID_, _Public Key_, and _Private Key_. Notably, the _Merchant Account ID_ specifies the currency that is enabled.

## Processing PayPal transactions through Braintree

Recurly now empowers you to process PayPal transactions through your Braintree merchant account. It is crucial to ensure that your Braintree merchant account is correctly configured to accept PayPal transactions.

To enhance your checkout experience, we recommend utilizing Recurly.js v4 to initiate the PayPal one-touch checkout flow. For a detailed guide, please refer to the [Recurly.js PayPal section](https://developers.recurly.com/reference/recurly-js/index.html#paypal).

It's important to note that the transaction details displayed in Recurly Admin for PayPal payments via Braintree may vary slightly from other payment methods. This is primarily because Recurly receives and securely stores Braintree’s vault token rather than the actual PayPal Billing Agreement. Recurly will employ this Braintree vault token for all ensuing PayPal transactions.

## Processing Venmo through Braintree

See the <a href="https://docs.recurly.com/docs/pay-with-venmo" target="_blank">Venmo payment method</a> for more information.

## Processing Verifications with 3DS through Braintree

Braintree's Verification path generally does not include 3DS capabilities on the traditional verify route unless you have integrated the [Proactive 3D-Secure route through Recurly.js](https://recurly.com/developers/reference/recurly-js/#additional-configuration-2). If you are a PSD2-mandated merchant (EU) or require 3DS for risk purposes and want to process verifications versus purchases, you will need to integrate to this style of 3D-secure.

Additionally, there are two mutually-exclusive settings that need enabling, one of which requires Braintree assistance. Contact your Braintree account manager for assistance with 'Enable without Verification'.

1. If you are not Vaulting with Braintree, and want to use Proactive 3DS, you must have a special setting enabled.  **Enable Verifications without Vaulting**: This setting requires the holder of information to be PCI compliant. PayPal has advised us to instruct merchants to request this feature be enabled and to indicate that Recurly is storing the card data.
   1. When that is complete, please ask Support to enable the following feature flag on the Recurly side that will give you access to this route: **Enable Braintree ZDA**
   2. Enabling this feature flag does not disable 3DS through purchase routes, it only enables it through verification flows. However, this flag **should_not_ be enabled prior to the setting at Braintree** to avoid payment failures.
2. **Card Verification**: this setting can be enabled in your Braintree control panel to ensure all vaulted cards are being verified prior to entering into the Braintree Vault. See an image of this setting below.

<Image align="center" border={false} src="https://files.readme.io/681d369645a07ae29f6a77ea7353288b5417a3641d99540622a318784d53c8af-Screenshot_2024-11-12_at_3.52.41_PM.png" />

Enabling this feature flag does not disable 3DS through purchase routes, it only enables it through verification flows. However, this flag **should_not_ be enabled prior to the setting at Braintree** to avoid payment failures.

# Integrating Braintree with Recurly

## Step 1: Gather your Braintree credentials

Before integrating Braintree with Recurly, you will need the following Braintree credentials:

* Merchant ID
* Merchant Account ID (for each currency you intend to accept)
* Public Key
* Private Key

You can find these details in your Braintree Control Panel.

## Step 2: Configure Braintree in Recurly

1. Log in to your Recurly account.
2. Navigate to **Configuration→Payment Gateways**.
3. Click on **Add a Gateway**, and then select **Braintree** from the list of available gateways.
4. Enter your Braintree credentials: _Merchant ID_, _Public Key_, and _Private Key_.
5. For multi-currency support, add separate Braintree gateways for each _Merchant Account ID_ (each associated with a different currency).
6. To enable Zero Dollar Authorizations, select the card types you wish to utilize. Visa, Mastercard, Discover, and American Express are supported. When checking American Express, please be aware this will send a penny authorization, per Braintree guidance.
7. If you wish to Vault with Braintree, check the 'Store in Braintree Vault' checkbox.
8. To comply with Visa’s free trial mandate, if your Braintree merchant account is associated with Australia or Canada specifically, choose one of those countries from the dropdown options. For all other countries, choose ‘Other’.

If you are not running free trials, choose ‘None’. See [https://docs.recurly.com/docs/visa-free-trial-mandate#updates-for-braintree](https://docs.recurly.com/docs/visa-free-trial-mandate#updates-for-braintree) for more information.

## Step 3: Enable PayPal (optional)

If you want to process PayPal transactions through Braintree:

1. Ensure that your Braintree merchant account is configured to accept PayPal transactions. This might require contacting Braintree support or checking within your Braintree Control Panel.

## Step 4: Test the configuration

Before going live, it’s wise to run test transactions to ensure the integration is functioning as expected. To test, your Recurly Account must be in development mode or production mode. It cannot be tested in sandbox mode.

1. In your Recurly account, navigate to the **Payment Gateways** configuration page for Braintree and click **Test Configuration**.
2. Check the test results. Successful tests will confirm that Recurly can communicate with Braintree and process transactions.

## Step 5: Go Live

1. Once you have tested successfully and are ready to go live, make sure your Braintree account is in “Production” mode (not “Sandbox”).
2. In your Recurly account, navigate to the Braintree configuration page and change the environment to **Production**.
3. Save your settings.

## Step 6: Monitor and manage transactions

After going live, continually monitor your transactions through the Recurly Admin Interface or Braintree’s Control Panel. Regularly review reports and analytics to optimize your payment operations.
