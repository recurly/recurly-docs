---
title: Ebanx (UPI AutoPay)
excerpt: >-
  Ebanx Gateway: A secure and innovative payment platform enabling seamless
  transactions, advanced data analytics, and enhanced customer experiences for
  businesses wanting to expand internationally.
deprecated: false
hidden: true
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

* Customer mandates cannot be migrated to Recurly if they exist on another platform. Customers must cancel those mandates and resubscribe per RBI rules.
* RBI mandates limit individual transactions to 15000 INR without going through a consumer two-factor flow. Plans or the combined amount of plans, if sent in the same purchase signup request, should be at or below this amount to avoid rejections on renewals.
* Ad-hoc or One-Time customer-initiated purchases and merchant-initiated Force Collections are not supported with UPI AutoPay.
* Billing Info updates are not supported with UPI AutoPay. If customers need to update their VPA (see definitions below) or bank accounts, they must cancel their existing mandate/subscription and re-subscribe.

# Definition

Ebanx is a full-service payment management platform focused on upcoming markets such as India. When configured with Recurly, it allows you to securely manage your transactions. You will need a relationship with Ebanx to enable this integration.

# Key details

| Feature                         | Description                                             |
| ------------------------------- | ------------------------------------------------------- |
| Services that work with Recurly | Payment Processing                                      |
| Supported Operations            | Subscription Mandate Enrollment, Recurring Transactions |
| Supported Payment Types         | UPI - AutoPay                                           |
| Supported Card Brands           | N/A                                                     |
| Gateway Specific 3DS2 Supported | No                                                      |
| Card On File Supported          | No                                                      |
| Regions                         | India                                                   |
| Currencies                      | INR                                                     |

# Configuring Ebanx in Recurly

Follow these steps to integrate Ebanx with Recurly. Ensure you use the correct site mode (Sandbox or Production) and valid Ebanx credentials for a smooth setup.

## Step 1: Obtain Ebanx Credentials

1. **Log in to your Ebanx Account**.

* Switch your Ebanx Dashboard to **Production mode** for production keys.
* Switch to **Sandbox mode** for sandbox keys.

2. **Go to Account Settings**: Click your name in the top-right corner and choose **Account Settings**.
3. **Select Integration**: From the four tabs in Settings, pick **Integration**.
4. **Copy your Integration Key**.

* Only the **Integration Key** will work with Recurly. The Public Integration Key will not function.

## Step 2: Enter Credentials in Recurly

1. Log in to your **Recurly** account and go to **Configuration → Payment Gateways**.
2. Click **Add a New Gateway** at the top-right.
3. From the list, choose **Ebanx**.
4. Paste your **Integration Key** into the “Integration Key” field.

<Image align="center" className="border" border={true} width="75% " src="https://files.readme.io/36f169d074f9f16c9524fb217cb56bac7150d1a642e731905cbf254b1bcdcc62-Ebanx-Credentials.png" />

## Step 3: Set Your Payment Methods

* Under **Accepted Card Types**, you won’t see any card options since this gateway currently supports **UPI AutoPay** only.
* Enable **UPI AutoPay** under **Alternative Payment Methods**.

## Step 4: Enable Currencies

Recurly only supports INR, so no selection is necessary.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/1c0bc5faff0d392f4bb496f251bca479cdca5d1f461e9a5bf49865c97799879c-Ebanx-PaymentMethod-Currency.png" />

## Step 5: Save and Enable the Gateway

1. Click **Add Payment Gateway** at the bottom.
2. You’ll see Ebanx added to your list of Production Gateways in Recurly with a status of **Enabled**.

## Step 6: Test the Configuration (Recommended)

* Perform a test transaction to confirm the integration works. It’s best to test in **development mode** on your Recurly sandbox site before going live.

## Step 7: Go Live

1. Once testing is successful, you’re ready to accept live payments through Ebanx.
2. Make sure your **Production Credentials** are entered in Recurly and your Ebanx account is in **Production mode**.

> **Pro Tip:** Keep your Ebanx credentials secure. Only authorized personnel should have access.\
> **Note:** Always consult with your Ebanx representative or Ebanx support to ensure your account is in good standing and you’re meeting all relevant regulations.

<br />

# Configuring Webhooks in Ebanx

## Step 1: Set Recurly Callback Endpoint in Ebanx

To successfully receive required webhooks for Enrollments and Payments from Ebanx in sandbox and production, follow the below steps:

**Note**: The state of your Ebanx dashboard (sandbox or production) will determine which Service URLs are are updated. Ensure your service URL is pointed at the correct Recurly site.

Ebanx sandbox URLs should point at Recurly sandbox sites, and the same goes for Production.

1. Log into your Ebanx Dashboard
2. Click on your User in the top right and choose **Account Settings**
3. Choose the **Integration** tab and enter your site callback URL in the **Status change notification URL**
   1. Example: [https://callbacks.recurly.com/ebanx/subdomain](https://callbacks.recurly.com/ebanx/subdomain)
4. Click **Save integration settings** at the bottom of the page.

> 📘 Warning
>
> Enrollment and Payment Updates will not occur properly without webhook setup. Please follow these steps in both production and test environments in Ebanx.

## Mandate Preferences

**UPI – Recurring** uses a **mandate ID** assigned to a consumer’s subscription upon signup. Consumers can revoke or pause this mandate from their UPI app, which can affect the subscription in Recurly. Depending on your settings, the subscription may become past due, expire, or pause.

### Configuring Mandate Preferences

Go to **Configuration → Invoice Templates → Invoice Settings** to pick one of two approaches:

1. **Automatically Handle Subscriptions**

* **Automatically Cancel the Subscription**: If the customer cancels their UPI mandate in the UPI app, the subscription in Recurly will auto-expire instead of going into dunning.
* **Automatically Pause the Subscription**: If the customer pauses their UPI mandate, the subscription in Recurly will auto-pause rather than continue billing.

2. **Manually Handle Subscriptions**

* **Manually Process Mandate Revocations/Pauses**: If a customer pauses or cancels their UPI mandate, you’ll receive webhooks about the subscription’s status. You decide how to handle the subscription (cancel, pause, etc.).

***

## UPI Retries

Due to UPI’s charge window constraints, Recurly handles retries if an Ebanx transaction fails:

1. **First retry** occurs **10 minutes** after the initial failure.
2. **Second through final retries** (up to eight more) occur **hourly** on the hour.
3. A total of **nine retries** plus the **original attempt** = **10 total attempts**.\
   If the transaction remains unsuccessful after the final retry, the subscription may move into a past-due or canceled state, depending on your settings.

***

## Troubleshooting FAQs

### **Q: My UPI subscription is failing. How can I fix this?**

* Confirm the subscription price hasn’t changed without re-engaging the customer.
* Verify your **Mandate Management** settings. If they’re set to manual, you may need to act on a webhook to update the subscription status.
* Make sure the customer is responding to UPI app push notifications, especially for charges above **15 INR**.

### **Q: I updated my customer’s VPA, but the original account was charged. How do I fix this?**

* **Billing Info Updates** aren’t supported with UPI AutoPay. Cancel the current subscription and have your customer re-subscribe using their new VPA.