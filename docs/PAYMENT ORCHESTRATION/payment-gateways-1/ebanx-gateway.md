---
title: Ebanx (UPI AutoPay)
excerpt: >-
  Ebanx Gateway: A secure and innovative payment platform enabling seamless
  transactions, advanced data analytics, and enhanced customer experiences for
  businesses wanting to expand internationally.
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

* Customer mandates cannot be migrated to Recurly if they exist on another platform. Customers must cancel those mandates and resubscribe per RBI and NPCI rules. Why? Enrollments are tightly coupled with the acquiring partner, merchant, and the consumer. During a migration, typically the acquiring partner will change, thus requiring re-enrollment.
* RBI mandates limit individual transactions to 15000 INR without going through a consumer two-factor flow.
  * This flow is on the Bank's specific UPI application and is not customizable in any way. 2FA will be handled in the manner that app has deemed compliant with RBI regulations.
  * Plans or the combined amount of plans, if sent in the same purchase signup request, should be at or below this amount to avoid rejections on renewals.
  * Read more about the UPI App in [UPI AutoPay](https://docs.recurly.com/recurly-subscriptions/docs/upi-autopay#/) documentation.
* Ad-hoc or One-Time customer-initiated purchases and merchant-initiated Force Collections are not supported with UPI AutoPay.
* Billing Info updates are not supported with UPI AutoPay. If customers need to update their VPA (see definitions below) or bank accounts, they must cancel their existing mandate/subscription and re-subscribe.
* Recurly.js is not supported with UPI AutoPay. Use our API to facilitate requests.
* Refunds through Ebanx must be the **full** amount.
* See the [UPI AutoPay payment method](https://docs.recurly.com/docs/upi-autopay#/) for additional restrictions and information.

# Definition

Ebanx is a full-service payment management platform focused on upcoming markets such as India. When configured with Recurly, it allows you to securely manage your transactions. You will need a relationship with Ebanx to enable this integration.

# Key details

| Feature                         | Description                                                                                                                                                                            |
| ------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Services that work with Recurly | Payment Processing, Subscriptions, [Automatic Subscription Cancellation](https://docs.recurly.com/recurly-subscriptions/docs/expire-subscription#/auto-cancellation-of-a-subscription) |
| Supported Operations            | Subscription Mandate Enrollment, Recurring Transactions, Refunds                                                                                                                       |
| Supported Payment Types         | [UPI - AutoPay](https://docs.recurly.com/docs/upi-autopay#/)                                                                                                                           |
| Supported Card Brands           | N/A                                                                                                                                                                                    |
| Gateway Specific 3DS2 Supported | No                                                                                                                                                                                     |
| Card On File Supported          | No                                                                                                                                                                                     |
| Regions                         | India                                                                                                                                                                                  |
| Currencies                      | INR                                                                                                                                                                                    |

# Configuring Ebanx in Recurly

Follow these steps to integrate Ebanx with Recurly. Ensure you use the correct site mode (Sandbox or Production) and valid Ebanx credentials for a smooth setup.

## Step 1: Obtain Ebanx Credentials

1. **Log in to your Ebanx Account**. This will require you to engage with Ebanx and address any appropriate contracts/applicable fees separate from Recurly.

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

<Image align="center" border={true} width="75% " src="https://files.readme.io/36f169d074f9f16c9524fb217cb56bac7150d1a642e731905cbf254b1bcdcc62-Ebanx-Credentials.png" className="border" />

## Step 3: Set Your Payment Methods

* Under **Accepted Card Types**, you won’t see any card options since this gateway currently supports **UPI AutoPay** only.
* Enable **UPI AutoPay** under **Alternative Payment Methods**.

## Step 4: Enable Currencies

Recurly only supports INR, so no selection is necessary.

<Image align="center" border={true} width="80% " src="https://files.readme.io/1c0bc5faff0d392f4bb496f251bca479cdca5d1f461e9a5bf49865c97799879c-Ebanx-PaymentMethod-Currency.png" className="border" />

## Step 5: Save and Enable the Gateway

1. Click **Add Payment Gateway** at the bottom.
2. You’ll see Ebanx added to your list of Production Gateways in Recurly with a status of **Enabled**.

## Step 6: Test the Configuration (Recommended)

* Perform a test transaction to confirm the integration works. It’s best to test in **development mode** on your Recurly sandbox site before going live.

## Step 7: Go Live

1. Once testing is successful, you’re ready to accept live payments through Ebanx.
2. Make sure your **Production Credentials** are entered in Recurly and your Ebanx account is in **Production mode**.
3. Make sure you have Ebanx production webhooks enabled prior to launch. See configuration steps below.

> **Pro Tip:** Keep your Ebanx credentials secure. Only authorized personnel should have access.
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

> ❗️ Warning
>
> Enrollment, Mandate Status, and Payment Updates will not occur properly without webhook setup. Please follow these steps in both production and test environments in Ebanx.

# Other Notes

## Required Fields

Ebanx and UPI AutoPay together require a minimum of fields to create a mandate for a recurring subscription. The minimum required fields to submit a UPI AutoPay transaction are as follows:

* VPA
* Email Address
* Customer First and Last Name
* Customer Billing Address (Street Address, City, Region/State, Country, Postal Code / PIN Code)
  * Regional Mapping:
    * Street Address is the House/Street Name and Number (EX: HOUSE NO. 32, MG ROAD)
    * City is the Locality and City in India (Ex: VILLAGE OF AMARPUR, NEW DELHI)
    * State is the State or Union Territory in India (ex: MAHARASHTRA)
    * Postal Code is the PIN Code (ex: 110019)
    * Country is the Country (ex: IN)
* Phone Number

## Mandate Preferences

**UPI – AutoPay** uses a **mandate ID** assigned to a consumer’s subscription upon signup. Consumers can revoke or pause this mandate from their UPI app, which can affect the subscription in Recurly. This will be configurable in the future. Presently, consumers cancelling or pausing their mandates in the UPI app will be automatically handled.

# Testing in Sandbox

When in sandbox ONLY, the response will contain a response URL for simulating interactions with the UPI Application. This interaction would typically take place with the customer directly via push notifications on their phone. For testing purposes, use the URL to accept or reject the mandate enrollment request.

## Transaction, Invoice, and Subscription Status

When processing with  [UPI AutoPay](https://docs.recurly.com/docs/upi-autopay#/), as with any asynchronous payment method in Recurly, subscriptions are immediately active, but transactions and invoices will be in a scheduled/processing state respectively. If customers do not authorize a subscription enrollment or payment via the UPI App, transactions will fail and subscriptions will be expired upon consumer rejection.

See documentation for the payment method [UPI AutoPay](https://docs.recurly.com/docs/upi-autopay#/) for more information.

## Confirming High Amount Renewals in Sandbox

When processing with UPI, any amount over 15K INR, a push notification would go to the consumer in a Production environment. In Sandbox, you will need to follow these instructions:

* Search for the Pending Payment in the Ebanx dashboard (Navigate to 'Payments' and choose the Pending Payment), click on the associated payment (or search via the Reference/ Hash), and choose the action you wish to take (Cancel or Confirm).
  * _Confirming_ the payment will create a Approval in Recurly.
  * _Cancelling_ will cause the payment to decline and the invoice to enter dunning.

# Additional Information

## Subscriptions and Transactions that work with UPI AutoPay

* Trial Subscriptions _with payment data_ -- trials without a prior UPI enrollment will not function.
* Non-Trial Subscriptions
* Renewals / Purchase

## Features that will not work with UPI AutoPay

* Transaction type of Authorize and Capture, and Void. UPI AutoPay transactions must be refunded.
* Subscription upgrades: Mandates stored on the UPI app control the amount and frequency. Changing this on the recurly side could cause declines.
* Trials without Enrollment (payment data on file)
* Non-Net-0 Terms: UPI must be charged on the specific day noted in the mandate, so terms above Net-0 can cause payment failures.
* One-time transactions: VPAs cannot be used for one-time transactions.
* Billing Info Updates: Billing Info updates must be done by customers in the UPI App.
* Standard Retries: UPI can only be retried on the same day. UPI-specific retries are coming soon.
* Account hierarchy: VPAs associated with a parent or child account will not be used in a recurring subscription – changing the hierarchy won’t affect existing subscriptions as a result.
* Aggregated / Calendar Invoicing: Taking existing subscriptions and combining them is against mandate-regulations in India, and therefore cannot be allowed.
* Bundling Subscriptions: See calendar aggregation.
* Multiple Subscriptions on a Single Account: Each individual subscription uses a mandate ID, and only one mandate ID is allowed per account.
* Merchant Admin-created Subscriptions: due to pre-debit notification and enrollment verification/consumer authentication that occurs in the UPI app, MIT subscription enrollments are not allowed per NPCI regulations in India.
* Retries: While planned, our standard issue retries on failed renewals are not supported due to NPCI regulations around retry rules. As these rules do not follow card-brand retry rules, UPI AutoPay transactions will not retry using basic or intelligent retry logic.

# Troubleshooting FAQs

### **Q: My UPI subscription is failing. How can I fix this?**

* Confirm the subscription price hasn’t changed without re-engaging the customer.
* Make sure the customer is responding to UPI app push notifications, especially for charges above **15000 INR**.

### **Q: I updated my customer’s VPA, but the original account was charged. How do I fix this?**

* **Billing Info Updates** made through Recurly APIs aren’t supported with UPI AutoPay. If a customer has a new VPA, they must re-enroll in the subscription.
  * Cancel the current subscription and have your customer re-subscribe using their new VPA.
  * If Customers only need to update their bank details, they can do so in the UPI App directly.

### **Q: A subscription renewal failed, and I cannot attempt collection. Why?**

* **Merchant-initiated one-time transactions** aren’t supported with UPI AutoPay. Reach out to your customer about payment options.
