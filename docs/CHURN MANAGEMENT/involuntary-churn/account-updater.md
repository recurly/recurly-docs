---
title: Account updater
excerpt: >-
  Recurly’s Account Updater service monitors your customers’ Mastercard®, Visa®,
  Discover®, and American Express® credit cards for changes, making updates in
  Recurly's records whenever necessary. Maximize revenue retention with
  Recurly's Account Updater—keeping customer payment details always up-to-date.
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

This feature may not be included in the Starter or Pro plans. If you are interested, please contact [Recurly Sales](https://recurly.com/demo/contact-sales/) to discuss upgrade options.

### Additional cost

This feature requires an additional cost. Please reach out to your Recurly account manager or [support@recurly.com](mailto:support@recurly.com) for more pricing details.

### Prerequisites

* Account Updater must be activated on the [Payments Settings](https://recurly.recurly.com/configuration/payments_settings) page in Recurly
* To enable Mastercard® updates, a Mastercard® Merchant Category Code (MCC) is required
* To enable American Express® Cardrefresher, a direct American Express® merchant account and SE number are required. Your business must be located in the United States
* For Adyen Real Time Account Updater (RTAU), Adyen must be your primary gateway and you must be processing raw card data through Recurly (not gateway tokens or network tokens)

### Limitations

* Account Updater only applies to stored credit cards — it's not available for non-card payment methods
* One-time transactions are not submitted to the Account Updater service
* Account Updater does not work for merchants using exclusively gateway tokens where Recurly doesn't have access to actual card data
* OptBlue merchant accounts (gateway-provided SE numbers) are not supported for American Express® Cardrefresher
* Updates only occur when your Recurly site is in production mode
* If you disable Account Updater, it cannot be re-enabled for 10 business days
* Only users with billing info editing rights can access Account Updater settings
* Adyen's RTAU has limited card brand support — it covers Visa, Mastercard, and Amex in certain regions only. Recurly recommends keeping both Adyen RTAU and Recurly Account Updater enabled to cover all cases

***

# Definition

Recurly's Account Updater is a proactive service that automatically monitors and refreshes stored credit card details through integrations with Mastercard®, Visa®, American Express®, and Discover®. By keeping billing information current, it reduces failed payments and subscriber churn — without any manual effort on your end.

***

# Key details

## Credit card support

Account Updater integrates with card update programs from Mastercard®, Visa®, American Express®, and Discover®. The cardholder's issuing bank — not Recurly — determines participation and sends account-change events to each network. Recurly also supports card updates in Europe in certain cases.

***

## Enabling Account Updater

1. Log in to your Recurly account
2. Navigate to **Configuration → Payments Settings**
3. Locate the **Account Updater** box at the top of the page
4. Click **Enable**

<Image align="center" border={true} width="75%" src="https://files.readme.io/58055d35475f35584a90ade8832f4e02c9109ed87d86372edc742e62bbdf268d-image.png" className="border" />

5. In the prompt, enter the following as applicable:
   * **Mastercard® Merchant Category Code (MCC)** — required to enable Mastercard® updates

   * **10-digit American Express® SE number** — required to enable Cardrefresher
   > **Note:** If you don't have an MCC or SE number, you can still enable Visa® and Discover® updates only. Gateway-provided (OptBlue) SE numbers will not work — only direct Amex SE numbers are supported.

6. Check the box to authorize the monthly Account Updater fee

7. Click **Enable**

Once enabled, your status will update to reflect which card networks are active for your account.

<Image align="center" border={true} width="75%" src="https://files.readme.io/5bf7f2b5b2ab5b22bd9431fbad6cf72ff6123582cd8ec096c7f3c22a04397a32-image.png" className="border" />

***

## How Account Updater works

Account Updater runs on a publish/subscribe model across all four supported card networks. There are four billable Account Updater event outcomes:

* **Updated expiration date** — automatically updates the expiration date stored in billing info
* **Updated card number** — replaces the full card number with the new one. In rare cases, this can include a card brand change. When that happens, customers must return to session to re-authenticate their card, since card networks don't share Network Transaction ID (NTID) formatting across brands. Recurly recommends proactively reaching out to affected customers and having them reauthenticate, which will run a verification and update the NTID on file. See [Verify stored card information](https://docs.recurly.com/recurly-subscriptions/v1.1/docs/using-3d-secure-with-stored-billing-information#/) for details
* **Credit card account closed** — flags the billing info as invalid to prevent further charges
* **Contact cardholder** — indicates that the customer should update or verify their payment information

Each of these events triggers the **Update Billing Info** webhook.

### Pre-renewal behavior

Account Updater runs pre-renewal for subscriptions with outdated billing information approximately one week before the renewal date. For subscriptions with longer billing cycles — quarterly, bi-annual, or annual — Recurly looks ahead further than one week.

> **Note:** Pre-renewal fetch is only supported on file-based Account Updater services. It does not apply to event-based services such as Amex Cardrefresher and Mastercard ABU.

### Dunning behavior

**Post initial decline**

After a card declines, Recurly queries available card update services to check for any missed updates before renewal. This is especially useful if the card was updated after the initial data request. Mastercard in particular returns advice codes that indicate when new card information is available — helping prevent a subscription from churning.

**No-change requeuing**

If a card update request returns as "No Change," "No Response," "Contact Cardholder," or "No Match," Recurly requeues the card to check for status changes throughout the dunning period — continuing until the invoice is failed or closed. "Contact Cardholder" is also a billable Account Updater event outcome.

If the customer has other active or past-due subscriptions, Recurly continues querying for updates across those as well. For event-based Account Updater services, Recurly may also receive updates outside of these specific scenarios, since the timing of third-party events is outside of Recurly's control.

***

## American Express® Cardrefresher integration

Recurly's Cardrefresher integration keeps Amex card details up to date automatically by connecting directly to the American Express® Account Updater service. This reduces payment failures caused by outdated card details.

To use this service, you must have a direct American Express® merchant account and SE number. OptBlue (gateway-provided) SE numbers are not supported.

***

## Adyen Real Time Account Updater integration

[Adyen Real Time Account Updater](https://docs.recurly.com/recurly-subscriptions/docs/adyen#adyen-realtime-account-updater) (RTAU) returns card update responses in real time, inline with transaction processing. This helps keep card details current during authorization and can reduce renewal declines caused by outdated information.

To use Adyen RTAU with Recurly, you must meet all of the following:

* Adyen is your primary gateway
* You're processing raw card data through Recurly (not gateway tokens or network tokens)
* You're processing card payments (RTAU doesn't apply to non-card payment methods)

For full setup instructions, see the [Adyen Real Time Account Updater documentation](https://docs.recurly.com/recurly-subscriptions/docs/adyen#adyen-realtime-account-updater).

***

## Monitoring account activity

You can monitor credit card billing info updates made by Account Updater in the **Activity** section of any customer account.

***

## Excluding a customer from Account Updater

To opt a specific customer out of Account Updater:

1. Navigate to the customer's account in Recurly
2. Scroll to the **Billing Info** section on the right
3. Toggle the Account Updater setting off

***

## Disabling Account Updater

> **Warning:** If you disable Account Updater, you cannot re-enable it for 10 business days.

1. Navigate to **Payments Settings** and click **Disable** in the upper right of the Account Updater box
2. Confirm the action in the pop-up that appears

<Image align="center" border={true} width="75%" src="https://files.readme.io/4363213dc7065784de3edcfb27b0d5dd9c0de96b604a8e5d9600b51b78b5fd30-image.png" className="border" />

3. Check all three confirmation boxes and click **Disable**

***

# FAQs

**How does Recurly's Account Updater work?**

When enabled, Recurly periodically checks with participating card networks to refresh stored payment details, helping avoid declined transactions caused by outdated card information.

**Which card networks does Account Updater support?**

Recurly's Account Updater integrates with Visa®, Mastercard®, American Express®, and Discover®. Participation is determined by the cardholder's issuing bank, not Recurly.

**Do I need to do anything after enabling Account Updater?**

No. Once enabled, Recurly handles all checks and updates automatically. You should see improved authorization rates as stale card details are refreshed.

**What if I have Account Updater enabled at both Recurly and another gateway?**

There's no guarantee which system updates first. Running both simultaneously can lead to temporary data mismatches and additional costs, since Recurly can't see updates made by another gateway.

**When should I enable Account Updater at a gateway instead of through Recurly?**

If you store only gateway tokens — not full card data — in Recurly, updating card info at the gateway level may be necessary. Keep in mind this won't refresh billing data within Recurly itself, so customer records in Recurly may remain outdated.

<br />