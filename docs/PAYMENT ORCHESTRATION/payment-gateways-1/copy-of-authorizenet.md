---
title: Copy of Authorize.net
excerpt: >-
  Harness the power of Authorize.net’s global payment solutions, seamlessly
  integrated with Recurly, to elevate your business's payment experience.
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

### Required plan

This feature or setting is available to all customers on any Recurly subscription plan.

### Limitations

* Authorize.net's API response detail is limited as far as in-depth responses on declines. Recurly uses decline reasons and merchant-advice-code logic to inform retries, and other processor, issuer, and network responses to help us decide when and how to retry. Due to the generic nature of this gateway's response information, we have employed best practices as instructed by the gateway.
  * In general, Recurly does not retry renewal declines in cases where Auth.net recommends treating a decline as a 'hard' decline. These include instances of:
    * Expired Cards
    * Lost or Stolen cards
  * You can read more about Auth.net's gateway responses in their [knowledgebase article](https://support.authorize.net/knowledgebase/Knowledgearticle/?code=000001111).
* We do not support Auth.net's fraud review flow -- if you are using Authorize.net's fraud monitoring, please be aware the gateway can void or invalidate transactions that were initially approved. It is advised to keep an eye on these external systems to avoid transactions that were initially approved and then cancelled by the gateway outside of Recurly's visibility.
* Authorize.net does not return raw NTIDs. If you need to migrate away from Authorize.net to another platform, you must engage with Tech Support to start an NTID migration conversation with one of our team members and Auth.net directly.

# Definition

Authorize.net is a well-established payment gateway that facilitates the seamless and secure transfer of credit card transactions between a payment portal (such as a website or mobile phone) and the credit card processors. It employs various features and tools to help businesses prevent fraudulent transactions while accepting payments with ease.

For pricing and signup information for a new production Authorize.net account, please visit [Authorize.net](https://www.authorize.net/).

| Features & Specifications       | Description / Availability                                                                                                        |
| ------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| Services that work with Recurly | Recurring Subscriptions, Payments (eCommerce and [MOTO](https://docs.recurly.com/recurly-subscriptions/docs/moto-transactions#/)) |
| Supported Operations            | Anti-Fraud, Authorize and Capture, Purchase, Refund, Verify, Void                                                                 |
| Supported Payment Types         | Credit Card                                                                                                                       |
| Supported Card Brands           | Visa, MasterCard, Amex, Discover, JCB, Diners Club, Union Pay                                                                     |
| Gateway Specific 3DS2 Supported | No. Authorize.net does not support 3DS.                                                                                           |
| Card on File Supported          | Yes                                                                                                                               |
| Regions                         | Worldwide                                                                                                                         |
| Currencies                      | AUD, CAD, EUR, GBP, NZD, PLN, and USD.                                                                                            |

# Gateway Setup Guide

## API Login ID and Transaction Key

To enable seamless communication between Recurly and your Authorize.net account, it is essential to configure your API Login ID and Transaction Key within Recurly.

To find these credentials within your Authorize.net account, navigate to:

`Account → Settings → API Login ID and Transaction Key`.

Once you have obtained your API Login ID and Transaction Key, input these credentials into Recurly’s Payment Gateway configuration settings, thereby establishing a secure link between Recurly and Authorize.net. This step is vital for processing transactions and managing subscriptions effectively. Step by step instructions with images are below.

## Authorize.net setup

This step-by-step guide will help you integrate your Authorize.net account with Recurly, enabling you to securely and efficiently process payments.

**Step 1: Sign up for an Authorize.net account**

1. **Visit** the [Authorize.net Signup Page](https://www.authorize.net/sign-up/)
2. **Complete** the application form with your business details.
3. After approval, **log in** to your Authorize.net account.

**Step 2: Obtain your API Login ID and Transaction Key**

1. In your Authorize.net account, **navigate** to `Account → Settings → 	API Credentials & Keys`.
2. **Note down** your API Login ID; you will need this to configure Recurly.
3. If you do not know your Transaction Key or have never created one before, **choose** ‘New Transaction Key’. You can choose to Disable previously created Transaction Keys Immediately using the checkbox that appears in your Auth.net dashboard.

Please note, checking the box to “Disable Old Transaction Key Immediately” will _instantly break your integrations_ once you click “Submit”. Only do this if you’ve been instructed to do so for fraud-prevention or security purposes, or if you do not have an active Auth.net integration that needs previous Transaction Keys to function.

4. **Click** ‘Submit’.

<Image align="center" border={true} width="60% " src="https://files.readme.io/2c5f346-image.png" className="border" />

In certain cases, you may be asked to provide a PIN to create a Transaction Key. Check your email for a PIN provided by Authorize.net in order to continue with this process.

<Image align="center" border={true} width="50% " src="https://files.readme.io/cdbb55e-image.png" className="border" />

If you have any issues, call the number at the bottom of the modal to speak to an Auth.net representative.
The email will contain a PIN, like the example below, which you will need to copy/paste into the field provided on Auth.net.

<Image align="center" border={true} width="75% " src="https://files.readme.io/4976dc3-image.png" className="border" />

After you have provided your PIN, you will be given a Transaction Key to use for transactions in Recurly.

**Step 3: Configure Your Authorize.net Account in Recurly**

1. **Log in** to your Recurly account.

2. **Navigate** to `Configuration → Payment Gateways`.

3. **Select** `Add a Gateway` and choose `Authorize.net`.

4. **Enter** your API Login ID and Transaction Key from Authorize.net.

<Image align="center" border={true} width="75% " src="https://files.readme.io/060ff09-image.png" className="border" />

5. You can **select** which Card Types you wish to accept. This will depend on which card types you are approved to accept. Speak to your representative at Auth.net if you have questions.

<Image align="center" border={true} width="75% " src="https://files.readme.io/73811e6-image.png" className="border" />

6. You can also **change** which currencies your Auth.net gateway can accept. Please choose from available currencies depending on which you are approved to accept.

<Image align="center" border={true} width="50% " src="https://files.readme.io/c4a227a-image.png" className="border" />

7. Lastly, Auth.net accepts a zero dollar authorization (verification) for card types. Please **choose** which you would like to accept ZDA-style transactions for. ZDA transactions are good for checking the validity of a card without billing a dollar amount.

<Image align="center" border={true} width="75% " src="https://files.readme.io/b4559de-image.png" className="border" />

8. Once your configuration is set up the way you would prefer, **click** ‘Add Payment Gateway’. If you are editing your implementation, the button will state ‘Update Payment Gateway’.

**Step 4: Set Up Address Verification Service (AVS)**

1. In your Recurly account, **navigate** to `Configuration → Payment Settings`.
2. **Scroll** to the `Address Verification Check` section.
3. **Select** your desired AVS rules (e.g., Enabled (default) or Disabled).

If ‘Enabled’, if Recurly receives information in the transaction response that the Address provided does not match what the Issuer has on file, the transaction will be rejected. **Please not**e, these settings apply to all supported gateways and will not be Auth.net specific.

4. **Click** `Save Changes`.

**Step 5: Enable Card Code Verification (CCV)**

1. In your Recurly account, **go to** `Configuration → Payment Settings`.
2. **Scroll** to the `Credit Card Verification Code Check` section.
3. **Set** the Radio Button option to ‘Enabled’. When Enabled, invalid or mismatched CVV code submissions will be rejected based on feedback from the card Issuer.
4. **Click** `Save Changes`.

<Image align="center" border={true} width="75% " src="https://files.readme.io/9306094-image.png" className="border" />

**Please note**, these settings apply to all supported gateways and will not be Auth.net specific.

**Step 6: Test your integration**

1. In your Recurly account, **navigate** to `Configuration → Payment Gateways → Authorize.net`.
2. **Click** on `Test Configuration` to ensure that Recurly can successfully communicate with your Authorize.net account.

   <Image align="center" border={true} src="https://files.readme.io/f5ff63a-image.png" className="border" />

   If you have provided your API Login ID and Transaction Key correctly, you will see this confirmation message.

**Step 7: Go Live!**

1. Once you’ve successfully tested the integration, you are ready to accept real transactions.
2. Monitor your transactions in Recurly and Authorize.net to ensure everything is working smoothly.

> **Note:** Ensure that you comply with PCI regulations when handling sensitive credit card information.

# Fraud Settings

## Address verification service (AVS)

If your company accepts payments from international customers, it is crucial to be aware of certain limitations associated with the Address Verification Service (AVS). Currently, AVS fails to match zip codes if the zip code contains letters. While US Zip Codes are exclusively numeric, numerous international postal codes contain letters, resulting in failed matches when verifying zip codes. To effectively leverage AVS with international credit cards, Recurly recommends allowing the transaction to proceed if either the street address _or_ zip code aligns accurately.

## Card code verification (CVV)

Upon the creation of a new subscription or the update of a credit card number, Recurly submits both the card number and the CVV (Card Code Verification) to Authorize.net. In compliance with PCI regulations, storing CVV values is strictly prohibited, regardless of encryption measures. As such, the CVV can only be utilized for the initial request. Submitting the CVV along with the first request enhances the likelihood of transaction approval and serves as a robust deterrent against fraudulent activities. Banks generally permit subsequent transactions to process smoothly if previous transactions by the same merchant have been conducted without issues.

# Final Thoughts

This guide is designed to walk you through the process of integrating Authorize.net with Recurly, configuring key features, and ensuring that everything is set up to start processing payments securely and efficiently. Always consult with your Authorize.net representative or Recurly support for any specific questions or issues related to your integration.