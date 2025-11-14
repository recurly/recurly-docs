---
title: Nuvei
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

### Required plan

This feature or setting is available to all customers on any Recurly subscription plan.

### Limitations

* Entry
* Entry

# Definition

**Definition**

For pricing and signup information for a new production Nuvei account, please check with your gateway provider point of contact.

| Features & Specifications       | Description / Availability                                                                                                                   |
| ------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- |
| Services that work with Recurly | Recurring Subscriptions, Payments (eCommerce and [MOTO](https://docs.recurly.com/recurly-subscriptions/docs/moto-transactions#/)), 3D Secure |
| Supported Operations            | Authorize and Capture, Purchase, Refund, Verify, Void                                                                                        |
| Supported Payment Types         | Credit Card, Apple Pay, Google Pay                                                                                                           |
| Supported Card Brands           | Visa, MasterCard, Amex, Discover, JCB, Diners Club, Union Pay                                                                                |
| Gateway Specific 3DS2 Supported | Yes                                                                                                                                          |
| Card on File Supported          | Yes                                                                                                                                          |
| Regions                         | Worldwide                                                                                                                                    |
| Currencies                      | All supported currencies.                                                                                                                    |

# Setup Nuvei with Recurly

To enable seamless communication between Recurly and your Nuvei account, it is essential to configure your API credentials within Recurly.

TBD Instructions

# 3D Secure Enablement Guide

This step-by-step guide will help you integrate your Nuvei with Recurly, enabling you to securely and efficiently process payments.

TBD Instructions

5. You can **select** which Card Types you wish to accept. This will depend on which card types you are approved to accept. Speak to your representative at Nuvei if you have questions.
6. You can also **change** which currencies your Nuvei gateway can accept. Please choose from available currencies depending on which you are approved to accept.

<Image align="center" border={true} width="50% " src="https://files.readme.io/c4a227a-image.png" className="border" />

7. Once your configuration is set up the way you would prefer, **click** ‘Add Payment Gateway’. If you are editing your implementation, the button will state ‘Update Payment Gateway’.

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

1. In your Recurly account, **navigate** to `Configuration → Payment Gateways → Nuvei`.
2. **Click** on `Test Configuration` to ensure that Recurly can successfully communicate with your Nuvei account.

   If you have provided your credentials correctly, you will see a confirmation message.

**Step 7: Go Live!**

1. Once you’ve successfully tested the integration, you are ready to accept real transactions.
2. Monitor your transactions in Recurly and  Nuvei to ensure everything is working smoothly.

> **Note:** Ensure that you comply with PCI regulations when handling sensitive credit card information.

This guide is designed to walk you through the process of integrating  Checkout.com with Recurly, configuring key features, and ensuring that everything is set up to start processing payments securely and efficiently. Always consult with your Authorize.net representative or Recurly support for any specific questions or issues related to your integration.

# Important Information 

## Address verification service (AVS)

If your company accepts payments from international customers, it is crucial to be aware of certain limitations associated with the Address Verification Service (AVS). Currently, AVS fails to match zip codes if the zip code contains letters. While US Zip Codes are exclusively numeric, numerous international postal codes contain letters, resulting in failed matches when verifying zip codes. To effectively leverage AVS with international credit cards, Recurly recommends allowing the transaction to proceed if either the street address _or_ zip code aligns accurately.

## Card code verification (CVV)

Upon the creation of a new subscription or the update of a credit card number, Recurly submits both the card number and the CVV (Card Code Verification) to Nuvei. In compliance with PCI regulations, storing CVV values is strictly prohibited, regardless of encryption measures. As such, the CVV can only be utilized for the initial request. Submitting the CVV along with the first request enhances the likelihood of transaction approval and serves as a robust deterrent against fraudulent activities. Banks generally permit subsequent transactions to process smoothly if previous transactions by the same merchant have been conducted without issues.
