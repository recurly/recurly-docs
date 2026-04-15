---
title: Payment settings
excerpt: >-
  Enable AVS and CVV fraud rules to secure your account. Also, turn on Account
  Updater with user-friendly toggles. These features provide access to some of
  the best income recovery resources available in the industry.
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

### Additional cost

Account Updater requires an additional cost. Please reach out to your Recurly account manager or [support@recurly.com](mailto:support@recurly.com) for more pricing details.

### Prerequisites

To enable and activate AVS or CVV rejection rules, your Recurly account must have the following prerequisites:

* A gateway that supports returning AVS and CVV results on initial transactions.

To enable and activate Account Updater, your Recurly account must have the following prerequisites:

* A gateway that supports credit card payments
* An active Recurly subscription

### Limitations

Please be aware of the following limitations of **AVS** and **CVV** rejection rules:

* Gateways that do not return AVS or CVV results will not function with this feature.
* Only certain gateways are supported: Adyen, Authorize.net, Chase Orbital, PayPal Complete, Stripe, TSYS.
  * Cybersource's AVS rules are located in the gateway configuration page.
* Only applicable to Credit Card payments

Please be aware of the following limitations of **Account Updater**:

* Only applicable to Credit Card payments
* OptBlue Amex MIDs are not supported
* Merchants outside of the US using Amex will not be able to utilize Card Refresher

# Definition

This page offers various configurations for rejecting potentially fraudulent transactions via Address or Card Code Verification values that Recurly receives from our gateway partners. Additionally, Account Updater can be configured on this page.

## Examples

To better illustrate the functionality of AVS and CVV rules, we’ve provided a few examples across different industries:

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        Industry
      </th>

      <th>
        Best practices
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        **Streaming media, eLearning & Digital publishing**
      </td>

      <td>
        * _Account Updater:_* For recurring transactions, cardholder data can become stale for long-running accounts. Account Updater can update billing information to ensure subscriptions continue to run over a long period of time.
        * _AVS and CVV Rules:_* For initial sign-ups, ensure that fraudulent transactions are rejected in the event the billing or CVV code provided does not match Issuer data.
      </td>
    </tr>
  </tbody>
</Table>

# Key benefits

* **Improve payment processes:** Gain access to Account Updater to improve and optimize recurring transactions.
* **Enhance protection:** Protect yourself from fraudulent transactions by rejecting initial sign-ups where the customer’s address, zip code, or CVV code do not match what the Issuer has on file.

# Implementation guide

## Enabling account updater

To learn more about Account Updater, visit our dedicated page on the<a href="https://docs.recurly.com/docs/account-updater" target="_blank"> Account Updater</a> service.

1. If you have not yet signed up for a Recurly Plan, you will see this message.

<Image align="center" border={true} src="https://files.readme.io/f4acf3a-image.png" className="border" />

2. Once you have signed up for a Recurly subscription and have a credit card supported gateway enabled, you will see an Enable button in order to start the enrollment process.

<Image align="center" border={true} src="https://files.readme.io/e84bb21-image.png" className="border" />

3. **Click** ‘Enable’ and a modal will appear, and you will be required to provide additional information for certain Card Brands.

* MasterCard Account Updater requires your merchant MCC (Merchant Category Code) to enroll. Your MCC will be a 4 digit code that describes what your business does and provides. For example, 5942 relates to Book Stores.
* If you have a direct American Express account, and want to enable Account Updater for this card type, you must provide your SE (Service Establishment) Number. OptBlue accounts are not supported at this time.

<Image align="center" border={true} src="https://files.readme.io/0ed852b-image.png" className="border" />

If you choose not to enter the above information, only Visa and Discover will be enabled for your account.

4. Once you have filled in MasterCard and American Express information, check the box to confirm you understand the additional charges associated with Account Updater. **Click** ‘Enable’ once the checkbox is checked.

At this point, Account Updater will be enabled for your site, and cards that are expiring soon will be sent for updates.

<Image align="center" border={true} src="https://files.readme.io/0f44fa3-image.png" className="border" />

## Enabling CVV checks

1. **Click** on ‘Configuration’ → ‘Payment Settings’.
2. **Ensure** your gateway is listed in the supported list and is active in your gateways.
3. **Toggle** the setting to ‘Enabled’.

<Image align="center" border={true} src="https://files.readme.io/c8ea553-image.png" className="border" />

> **Note:** This is ‘Enabled’ by default on most accounts.
>
> Approved transactions that receive a mismatched CVV or AVS rule will be voided if enabled.

## Enabling AVS Checks

**Click** on ‘Configuration’ → ‘Payment Settings’
**Ensure** your gateway is listed in the supported list and is active in your gateways.
**Toggle** the setting to ‘Enabled’.

<Image align="center" border={true} src="https://files.readme.io/4d6fe1c5919f5fcde2426a87dc4bf43f0a7e16c22d96803d27a021bc5f8b4967-image.png" className="border" />

## Duplicate billing infos prevention

When the **[Wallet](https://docs.recurly.com/recurly-subscriptions/docs/wallet)** feature is enabled, an additional payments setting becomes available to prevent duplicate billing information from being saved. This control applies to credit cards (with PANs) and RJS tokens. By default, the setting is configured to allow duplicates. When set to block duplicates and a duplicate entry is made, an error will be returned in the Recurly UI or via the [billing infos](https://recurly.com/developers/api/v2021-02-25/index.html#operation/list_billing_infos) API.

<Image align="center" border={true} src="https://files.readme.io/d5fb633232ff5ac8ccc03566f54a76df4e1caa9caab01a8c96d5e7c1862da351-Screenshot_2026-04-15_at_12.42.35_PM.png" className="border" />

# FAQs

**Q: What if my customer does not provide an address on the initial transaction?**

**A:** Your gateway will still generate an AVS response code in such cases, which will likely result in a rejection due to the absence of address information. It's important to capture billing information for all transactions to prevent an increase in declines when this feature is enabled.

**Q: Does the Account Updater work on bank account details?**

**A:** No, the Account Updater service is exclusively for credit card payment methods. It is not necessary if you do not accept credit cards.

**Q: Will CVV be checked on recurring transactions?**

**A:** No, Recurly does not store CVV codes to comply with PCI standards and therefore does not include the CVV code in recurring transactions. The rules for both AVS and CVV codes apply only to initial transactions, such as a customer's first sign-up.
