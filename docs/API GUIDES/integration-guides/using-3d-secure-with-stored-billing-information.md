---
title: 3D secure 2.0 with stored Billing Information
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

This guide shows you how to use the Verification Endpoints to reverify card details already stored in Recurly for new subscriptions using cards stored on file, such as prior to resuming or reactivating a subscription. We’ll also illustrate how to integrate [Recurly.js](https://docs.recurly.com/v1.2/docs/3d-secure#/re-authenticating-existing-billing-information) for secure tokenization where required.

There are several reasons to use customer authentication or reverification flows outside of subscription lifecycle management. You may use this guide as a way to accomplish reverification of consumer card details for items such as: 

* Regulatory 3DS requirements when unpausing or resuming a subscription
* Combat account takeover in scenarios such as stale accounts, suspected fraud, and more.
* Acquire a new NTID after a card brand change from Account Updater

## Prerequisites & limitations

* Familiarity with Recurly’s API and basic REST concepts including:
  * Verify without CVV:  [Verify an account's credit card billing info](https://recurly.com/developers/api/v2021-02-25/index.html#operation/verify_billing_info)
  * Verify with CVV:  [Verify an account's credit card billing cvv](https://recurly.com/developers/api/v2021-02-25/index.html#operation/verify_billing_info_cvv)
* [Completed the Quickstart Guide](https://docs.recurly.com/v1.1/docs/quick-start-guide#/) and [3DS integration guide](https://docs.recurly.com/v1.1/docs/3d-secure-20-integration-guide#/versions)
* Conditional usage of [Recurly.js](https://docs.recurly.com/v1.2/docs/3d-secure#/re-authenticating-existing-billing-information) depending on your supported gateway:
  * Cybersource and WorldPay gateways require use of Recurly.js to complete this integration guide

***

# Definition

**Stored Billing Information** refers to card data stored in Recurly's systems and referenced via API by sending in an account code, or specify a billing ID when using Recurly Wallet.

**PSD2** refers to the EU mandate for SCA, or Strong Customer Authentication, and is applicable to EU merchants mostly. Read more about [PSD2 in our compliance documentation](https://docs.recurly.com/docs/revised-payment-services-directive-psd2#/) for 3DS, SCA, and PSD2.

**Reactivating** a cancelled Subscription is referring to the API path in Recurly APIs where a customer's cancelled subscription is reactivated and resumes renewal billing again. You can view documentation on [reactivating a cancelled subscription via API](https://recurly.com/developers/api/v2021-02-25/index.html#operation/reactivate_subscription) in our developer hub.

**Resuming** a paused Subscription is referring to the API path in Recurly APIs where a customer's paused subscription is resumed and starts billing again. You can view documentation on [resuming a paused subscription via API](https://recurly.com/developers/api/v2021-02-25/index.html#operation/resume_subscription) in our developer hub.

**Account Takeover** describes a process where a bad actor acquires credentials to an account they do not own and attempts to abuse the information stored within it, such as payment information. To avoid usage of stored payment details by a fraudulent user, you can use these flows to require entry of a CVV or 3DS Authentication, which the fraudster is unlikely to complete successfully.

**"Warming" a MID** refers to a process where after an account migration, such as from another provider, you acclimate the issuers of your current customer base to your new Merchant ID. This can help reduce churn related to issuers declining renewals post-import. You may handle this process in any way you wish, but the ultimate goal will be to have the customer re-enter session if their subscription has experienced a few declines post-import.

**Customer Authentication** can have many avenues -- this can mean 3DS, it can also mean Apple and Google Pay verifications. This can also be used as an avenue for consumers to verify their info after a card brand update, if 3DS declines start happening during renewals, or in rare cases, when Account Updater returns a brand new card from an entirely different card network!

**Regional requirements** can require 3DS authentication when a customer is initiating a payment, whether the card is on file or not. For example, all CIT transactions in Brazil require 3DS when using a credit card, thus even when a consumer has their billing info stored at Recurly, a simple API call without 3DS involvement is not enough and payments can be declined.

***

# 3DS Processing for Stored Card Details

## Authenticating the customer for subscription changes or new transactions

### Step 1: Submit a Verification Request via API

When a customer who has a paused subscription requests that subscription is resumed, prior to resuming that subscription, use the API to request billing info verification using an account code, or a billing info ID if using Recurly Wallet, that is attached to that subscription.

You can do this in one of two ways depending on your preference:

* With CVV: [Verify an account's credit card billing cvv](https://recurly.com/developers/api/v2021-02-25/index.html#operation/verify_billing_info_cvv)
* Without CVV: [Verify an account's credit card billing information](https://recurly.com/developers/api/v2021-02-25/index.html#operation/verify_billing_info)

Once you've done this, if 3DS challenge is required, you will receive a `three_d_secure_action_token_id` as documented in the [3DS integration guide](https://docs.recurly.com/v1.1/docs/3d-secure-20-integration-guide#/versions). From here, follow the flows outlined in the [3DS integration guide](https://docs.recurly.com/v1.1/docs/3d-secure-20-integration-guide#/versions) to complete 3DS for re-verification.

Use [Recurly.js](https://docs.recurly.com/v1.2/docs/3d-secure#/re-authenticating-existing-billing-information) to submit the 3DS action token and resubmit the verification using the action result token. Once you have a successful re-verification transaction response from the gateway, you may move on to Step 2.

**Note:** If you are using [Cybersource](https://docs.recurly.com/docs/cybersource#/) or [WorldPay](https://docs.recurly.com/docs/worldpaydlocal-latam-support#/), you will want to _start_ this process with Recurly.js and pass in the billing info ID or account code to Recurly.js and pass in a `token_id` to one of the above two endpoints. This is because Cybersource and WorldPay require a data collector to capture consumer information for 3DS to function properly on those platforms.

* For Cybersource and WorldPay, you'll need to configure your risk options to include a `billingInfoId`.
* If passing the CVV, tokenizing the cvv element will also be required.

See more detailed information for supporting known billing infos in Recurly.js  in our development hub.

* [CVV Element Tokenization](https://docs.recurly.com/v1.2/docs/elements)
* [Billing Info ID Tokenization](https://docs.recurly.com/recurly-subscriptions/v1.2/docs/3d-secure#/)

#### Handling Re-verification and 3DS Authentication Failures

Consumers can fail SCA for a multitude of reasons including cancelling out of the challenge window, browsers blocking pop-up modals, account takeover / fraudulent attempts, and more. You may offer consumers multiple chances to resume their subscription as per your own business needs. It is recommended to request new billing information after a few attempts to reverify existing billing information.

If you only needed to authentication a consumer for a new subscription, or verification for non-subscription changes, you're done! If you need to resume or reactivate a subscription, see the next steps.

### Step 2: Resume or Reactivate the Subscription

**Resuming a Paused Subscription**: If successful, you can [resume the paused subscription](https://recurly.com/developers/api/v2021-02-25/index.html#operation/resume_subscription) by implementing the Resume Subscription endpoint and reference the subscription ID in your path.

Read more about subscription lifecycles in our dedicated [Subscription lifecycle documentation](https://docs.recurly.com/docs/subscription-lifecycle#/).

**Reactivating a Cancelled Subscription** If successful, you can [reactivate the cancelled subscription](https://recurly.com/developers/api/v2021-02-25/index.html#operation/reactivate_subscription) by implementing the Reactivate Subscription endpoint and reference the subscription ID in your path.

Read more about subscription lifecycles in our dedicated [Subscription lifecycle documentation](https://docs.recurly.com/docs/subscription-lifecycle#/).

### Step 3: Verify and finish

After a successful verification and resume/reactivation, you can confirm the details via the Recurly Admin UI or by calling Recurly’s API to list your new account, subscription, or invoice.

***

## Next steps

Now that you can reverify billing information and manage paused or cancelled subscriptions, explore the [Subscription Management](https://docs.recurly.com/v1.1/docs/managing-subscription-methods-guides#/) guide to learn additional methods to modify subscriptions after the initial purchase.
