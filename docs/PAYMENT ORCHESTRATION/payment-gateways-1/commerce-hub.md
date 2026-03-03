---
title: Commerce Hub by Fiserv
excerpt: >-
  Seamless and secure payment processing with Commerce Hub integration for
  Recurly.
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

### Required plan

This feature or setting is available to all customers on any Recurly subscription plan.

# Definition

Commerce Hub is a full-service payment management platform, developed by Fiserv / First Data. When configured with Recurly, it allows you to securely manage your transactions. You will need your Commerce Hub credentials to enable this integration.

> **Note**: Visit our guide on testing your gateway configurations in Recurly to ensure your payment processes are set up correctly.

## Requirements

* Ensure your Commerce Hub Merchant Account is set up to support "Multi-Use Public Key Encryption (MUPK)", and that it's set to recycle every 10 days at least. This is not enabled by default.
* Ensure you have your Business Entity Merchant Category Code filled in properly.

## Limitations

* Recurly does not support lifecycle webhooks or post-auth webhooks from the Gateway. If you are using gateway-level fraud review systems, gateway tokens, or are making transaction actions at the gateway, there is risk that Recurly and the gateway could be out of sync. It is advised to keep an eye on gateway-level fraud services, and ensure you are capturing, voiding, and processing refunds from Recurly instead of at the gateway.

# Key details

| Feature                         | Description                                                                                                                                                                                                                                                                                                 |
| ------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Services that work with Recurly | Payment Processing, Recurring Billing                                                                                                                                                                                                                                                                       |
| Supported Operations            | Verify, Purchase, Authorize and Capture, Void, Refund (Full and Partial)                                                                                                                                                                                                                                    |
| Supported Payment Types         | Credit/Debit Card, Apple Pay, Google Pay, Network Tokens                                                                                                                                                                                                                                                    |
| Supported Card Brands           | Visa, MasterCard, American Express, Discover, Diners Club, JCB, Union Pay                                                                                                                                                                                                                                   |
| Gateway Specific 3DS2 Supported | No                                                                                                                                                                                                                                                                                                          |
| Card On File Supported          | Yes                                                                                                                                                                                                                                                                                                         |
| Regions                         | Global                                                                                                                                                                                                                                                                                                      |
| Currencies                      | [All ISO Standard](https://docs.recurly.com/docs/currency-support-by-gateway#/)                                                                                                                                                                                                                             |
| Transaction Categories          | Ecommerce, Recurring, MOTO                                                                                                                                                                                                                                                                                  |
| Additional Feature Support      | [MOTO](https://docs.recurly.com/recurly-subscriptions/docs/moto-transactions#/)  Processing,  ProcessingBilling and Shipping Information, Level 2 Data, Visa Trial Descriptors,  AVS / CVV Checks, Fiserv Transarmor Gateway Tokens, Omnichannel Point of Sale Subscriptions, VAT and Line Item Passthrough |

## Migrating from First Data and Payeezy Gateways

> 🚧 Important
>
> First Data and Payeezy gateways will be deprecated at the end of Q3 2025. This date is mandated by Fiserv directly. Ensure you are onboarding Commerce Hub and testing your integration in a timely manner to avoid payment interruptions.

1. Onboard Commerce Hub in your Recurly Site.
2. If you have an integration to Recurly that uses the `gateway_code` value, ensure you modify it in your code to avoid sending transactions to the wrong gateway.
3. You may migrate away from Payeezy and First Data gradually if you desire. Simply change the `gateway_code` for new transactions and existing subscriptions over a period of time at your discretion.

### Parity with First Data and Payeezy

In building Commerce Hub, Recurly has taken great care in reaching parity with previous functionality, and certified our platform with Fiserv to ensure a smooth transition. Rest assured, transactions that functioned on First Data and Payeezy will seamlessly transition to Commerce Hub.

### Existing subscriptions

Since First Data and Payeezy merchants have already been migrated to Commerce Hub behind the scenes, all current subscription transactions have been processing on Commerce Hub behind the scenes due to an emulation rule at Fiserv. Existing subscriptions should continue to process as usual by changing the gateway code the subscription is pointed at within Recurly.

For new subscribers, ensure you change the `gateway_code`value you are sending API transactions to in order to avoid interruptions or errors once you disable your Fiserv or Payeezy gateway instances in your Recurly site.

## Address Verification System (AVS) settings

Unlike previous First Data and Payeezy gateway implementations, Merchants using Commerce Hub have the option to tailor their Address Verification System (AVS) and CVV (Card Verification Value) checks via the Payment Settings page. Learn more about our gateway agnostic AVS / CVV rules [here](https://docs.recurly.com/docs/payment-settings#/enabling-cvv-checks).

## Configuring Commerce Hub Gateway in Recurly

> **Note**: Zero-dollar verifications are available by default and do not require configuration.

### Step 1: Obtain Your Commerce Hub  Credentials

* Log into your Commerce Hub Developer Studio. If you do not have an account, you will need to sign up for one through Commerce Hub and acquire a Corporate Merchant Account.

You may already have a Fiserv Corporate Merchant account where Merchant ID access codes are created. If you need assistance with this dashboard, please reach out to Fiserv directly.

### Step 2: Generate your Commerce Hub credentials (if necessary)

#### Create or navigate to your Workspace

* **For new Merchants:** If you do not have a Workspace yet, work with your Fiserv merchant representative to create one, and ensure your sandbox or production MID is associated with it.
* **For migrating Merchants:** You will already have an existing Workspace with your production Merchant ID and existing API keys.

#### Check Merchant IDs

Click on Credentials, and ensure your existing Merchant IDs are present if you are migrating from First Data or Payeezy. If you do not see your Merchant IDs, add them using the ‘Add Merchant ID’ button.

<Image align="center" border={true} width="80% " src="https://files.readme.io/6beec713ce23e2045a422037bdd9856d1bc00fba79580dbcdd9263db26ee6f7e-Add_Merchant_ID_Step_1.png" className="border" />

You will need an **Access code** from Fiserv to add Production Merchant IDs.

* To add a Production MID, **ensure you select** the ‘Production’ Environment when adding a Merchant ID. You will not need a ‘Certification’ MID.
* To add a Sandbox Merchant ID, **simply click** ‘Add Merchant ID’ and **select** ‘Create new Sandbox Merchant Id’ and follow the prompts.

<Image align="center" border={true} width="80% " src="https://files.readme.io/d55d2e81ab2674a345d10ab92633880734f72cc124bbdd030f8fab0502d8a936-Add_Merchant_ID_Step_2_-_Access_Code.png" className="border" />

#### Create API Key(s)

API Keys for Commerce Hub are per Merchant ID. You may have API keys for a sandbox or production environment, and will want to ensure you are entering the correct credentials in your Recurly site.

1. **Click** ‘Add API Key’.
2. **Select** the Merchant ID from the available dropdown.
3. **Name** the API Key – example: Recurly-Sandbox, or Recurly-Production
4. API key names must include letters, numbers, "_", and "-" only.
5. **Check** All Features.
6. **Click** ‘Add Key’.

<Image align="center" border={true} width="80% " src="https://files.readme.io/5851e1561b0333b8968e438191d8d25249230646e28fdc1ef57557ce20073984-Add_API_Key.png" className="border" />

Once your API Key is successfully added, a pop up modal will appear on the page. Do NOT navigate away. You must collect certain details from this pop up modal including:

* API Key
* API secret

You will also need the following details to onboard to Recurly successfully:

* Fiserv Merchant ID
* Terminal ID
* Service Entitlement Number (former Payeezy Merchants only) for Descriptors

Optional credentials include the below fields. These are optional and aren’t necessary unless you have more than one site ID/store ID and wish to route.

* Store ID
* Site ID

Store these details somewhere safe, and proceed to Step 3.

### Step 3: Enter Commerce Hub Credentials in Recurly

As with any gateway, ensure the credentials you enter into this page are associated with the correct Commerce Hub and Recurly environments. Ensure you are adding sandbox credentials to your Sandbox Recurly site, and Production credentials to your Production Recurly site. Do not mix and match, or you may experience payment failures.

1. **Log into** your Recurly account and navigate to the Payment Gateways page.
2. **Click** on the "Add a New Gateway" button at the top right of the Payment Gateways page.
3. **Select** “Commerce Hub” from the list of available gateways.
4. **Enter** your **Merchant ID** into the “Fiserv Merchant ID” field.
5. **Enter** your **Terminal ID** into the “Terminal ID” field.
6. **Enter** your **API Key** into the “API Key” field.
7. **Enter** your **API secret** into the “API Secret” field.
8. If you are routing based on site or store ID in Commerce Hub:

* **Enter** your **Store ID** into the “Store ID” field.
* **Enter** your **Site ID** into the “Site ID” field.

9. If you are a former Payeezy Merchant:

* Enter your **Service Entitlement Number** into the “Service Entitlement Number” field. If you do not know, or do not have a Service Entitlement Number, please contact your Fiserv representative for assistance.

### Step 4:  Set your credit card types

Under the ‘ACCEPTED CARD TYPES’ header, you will see multiple card brand names. Only enable (select) those card types or payment methods that you have enabled on your Commerce Hub Merchant ID.

### Step 5: Enable currencies

USD will be enabled by default. If you want to add additional currencies, or remove USD, use the selection tool on the left to add the currencies your Commerce Hub gateway accepts.

### Step 6: Save and enable the gateway

After entering all the required information, click on the "Add Payment Gateway" button at the bottom of the page.

You will see that Commerce Hub has been added to your list of Production Gateways in Recurly with a status of "Enabled".

### Step 7: Test the configuration (recommended)

Make a test transaction to ensure that the integration is working correctly. This can be done in development mode for your sandbox site in Recurly before moving to a live environment.

### Step 8: Go live

After testing, if everything is working as expected, you are ready to accept live payments through the Commerce Hub gateway via Recurly.

> **Pro Tip:** Keep your Commerce Hub credentials secure and ensure only authorized personnel have access to this information.
>
> **Please note:** Always consult with your Commerce Hub account representative or support resources to ensure that your account is in good standing and that you are compliant with all relevant regulations and requirements.
