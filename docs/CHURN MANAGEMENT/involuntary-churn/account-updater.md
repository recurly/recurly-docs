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

This guide explains how to configure Recurly’s Account Updater service, including direct integration with American Express® Cardrefresher. Merchants with OptBlue or gateway‐generated SE numbers cannot use AMEX Cardrefresher through Recurly; a direct Amex merchant account and SE number are required.

### Prerequisites & limitations

* Integration with Recurly’s platform.
* Activation of the Account Updater feature in the Recurly payment settings page.
* For American Express® Cardrefresher, an American Express® merchant account is required, and your business must be located in the United States. OptBlue merchant accounts (gateway‐provided SE numbers) are not supported.
* One-time transactions are not submitted to the Account Updater service.
* Account Updater will not work for merchants using exclusively gateway tokens where Recurly does not have access to actual card data. Work with your gateway partner to enable Account Updater if needed.

# Definition

Recurly’s Account Updater is a proactive service that automatically monitors and updates stored credit card details through integrations with Mastercard®, Visa®, American Express®, and Discover®. By keeping billing info fresh, it reduces failed payments and subscriber churn.

# Credit card support

Stay ahead of subscriber churn with [Recurly’s Account Updater](https://recurly.com/blog/how-automated-credit-card-account-updaters-fight-subscriber-churn/). This feature integrates with Account Updater programs from Mastercard®, Visa®, American Express®, and Discover®. The cardholder’s bank —not Recurly—determines participation, sending account‐change events to each network. Additionally, Recurly now supports card updates in Europe in certain cases.

# Configuration & availability

Account Updater is available on all Recurly plans. As of October 26, enabling Account Updater is even simpler via its dedicated page under [Payments Settings](https://recurly.recurly.com/configuration/payments_settings). Remember: although you can enable Account Updater in any environment, updates only occur when your site is in production mode.

# Enabling Account Updater in Recurly

1. **Login to Recurly:** Sign in to your Recurly account.
2. **Access Payments Settings:** Navigate to the Payments Settings page from the dashboard.
3. **Locate Account Updater:** Find the Account Updater box at the top.
4. **Enable the Feature:** Click **Enable**.
5. **Enter MCC and SE Number:** In the prompt, provide:

   * **Mastercard® Merchant Category Code (MCC)** (required to enable Mastercard® updates)
   * **10-digit American Express® SE number** (required to enable Cardrefresher)
     Enter these accurately.

   <br />

   <Image align="center" border={true} width="75% " src="https://files.readme.io/79af8f5-image.png" className="border" />
6. **Confirm Charges:** Check the box to authorize the monthly Account Updater fee. If you lack MCC or SE number, you can still enable Visa® and Discover® only.
7. **Completion:** Click **Enable**. Your status will update to show you’re enabled for Visa®, Mastercard®, Discover®, and American Express®.

<Image align="center" border={true} width="75% " src="https://files.readme.io/17be4e7-image.png" className="border" />

> **Note:** Ensure the SE number is correct. Gateway‐provided (OptBlue) SE numbers will not work—only direct Amex SE numbers are supported.

# Triggers

Account Updater runs on a publish/subscribe model for Mastercard®, Visa®, American Express®, and Discover®:

* **Updated Expiration Date:** Automatically updates expiration in billing info.
* **Updated Credit Card Number:** Replaces the the entire card number. 
  * In rare cases, this can mean a brand change. In these instances, customers must come back into session to ensure continued recurring transaction processing as the card networks do not generally share Network Transaction ID formatting.
* **Credit Card Account Closed:** Flags billing info as invalid to prevent further charges.

Each of these events fires the **Update Billing Info** webhook.

## Lifecycle Behavior

### Pre-renewal for Subscriptions

Account Updater runs pre-renewal on subscriptions with outdated information roughly 1 week before renewal date. In certain cases, we look ahead farther than 1 week in the case of cards that have long-running subscriptions, such as quarterly, bi-annual, or annual subscriptions. _Note:_ This fetch capability is only supported on file-based Account Updater services, and does not apply to event-based services such as Amex CardRefresher and MasterCard ABU.

### Dunning Behaviors

**Post initial-decline**

After a card declines, we will send cards, or query services (as available) for card updates to check for any missed updates pre-renewal. This is effective in the event of a timing issue pre-renewal or if the card was updated/changed after the initial data request. This is especially effective for MasterCard, who will return information in advice codes on when new information is available that could save a subscription from churning.

**No Change Requeuing**

In the event that a request for new card details is returned as 'No Change', 'No Response', 'Contact Cardholder', or 'No Match', we requeue data to see if there is any change in the status of a card during the dunning timeframes for a given invoice, especially if it is past due.

We will keep requesting updates until dunning is completed and the invoice is failed/closed. If the consumer has other active subscriptions that are up for renewal, or past due, we will continue to query for updates.

For certain cards, event-based Account Updater services will accept new billing info updates outside of these specific scenarios since Recurly does not control the timing on events received from third parties.

# American Express® integration with Recurly

Recurly’s American Express® Cardrefresher integration provides an automated solution to keep Amex card details up-to-date. By connecting to the Amex Account Updater (Card Refresher), Recurly ensures stored card details remain current, reducing payment failures. However, to use this service, you must have a direct American Express® merchant account and SE number. **OptBlue (gateway) SE numbers are not supported**—Recurly cannot process them.

# Account activity

Monitor credit‐card billing info updates by Account Updater under an Account’s **Activity** section.

# Excluding an account’s billing information

If you prefer not to update billing info for certain customers, you can opt them out:

1. **Navigate** to the specific customer account in Recurly.
2. **Scroll** to the **Billing Info** section on the right.
3. **Toggle** the Account Updater setting as needed.

# Disabling Account Updater in Recurly

> 🚧 If you disable Account Updater, you cannot re-enable it for 10 business days.

1. **Navigate** to Payments Settings and click **Disable** in the Account Updater box’s upper right.
2. A pop-up will appear—confirm you want to disable.

<Image align="center" border={true} width="75% " src="https://files.readme.io/133d86c-image.png" className="border" />

3. **Check** all three boxes and click **Disable**.

# Notes

1. Account Updater applies only to stored credit cards; it’s not visible for non-card payment methods.
2. Only users with billing-info editing rights can access these settings.
3. Once enabled, all billing info is submitted to the Account Updater service by default.

# FAQs

### **Q: How does Recurly’s Account Updater work?**

A: When enabled, Recurly periodically checks with participating card networks to refresh stored payment details, helping avoid declined transactions due to outdated card information.

### **Q: Which card brands participate in Recurly’s Account Updater?**

A: Participation varies, but major brands like Visa, Mastercard, and American Express are supported. Discover® is also included.

### **Q: Do I need to do anything after enabling Account Updater?**

A: No. Once enabled, Recurly handles all checks and updates automatically. You’ll see improved authorization rates as stale card details are replaced.

### **Q: What if I have Account Updater enabled at both Recurly and another gateway?**

A: There’s no guarantee which system updates first. Maintaining both can lead to temporary data mismatches and extra costs, since Recurly can’t see updates made by another gateway.

### **Q: When is it better to enable Account Updater at another gateway instead of Recurly?**

A: If you store only gateway tokens (not full card data) in Recurly, updating card info at the gateway level may be necessary. However, this won’t refresh data within Recurly itself—so customer billing info in Recurly may remain outdated.
