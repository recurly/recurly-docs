---
title: Ebanx (APAC and LATAM)
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

## Required plan

This feature or setting is available to all customers on any Recurly subscription plan.

## Limitations

### UPI / India

- Customer mandates cannot be migrated to Recurly if they exist on another platform. Customers must cancel those mandates and resubscribe per RBI and NPCI rules. Why? Enrollments are tightly coupled with the acquiring partner, merchant, and the consumer. During a migration, typically the acquiring partner will change, thus requiring re-enrollment.
- RBI mandates limit individual transactions to 15000 INR without going through a consumer two-factor flow.
  - This flow is on the Bank's specific UPI application and is not customizable in any way. 2FA will be handled in the manner that app has deemed compliant with RBI regulations.
  - Plans or the combined amount of plans, if sent in the same purchase signup request, should be at or below this amount to avoid rejections on renewals.
  - Read more about the UPI App in [UPI AutoPay](https://docs.recurly.com/recurly-subscriptions/docs/upi-autopay#/) documentation.
- Billing Info updates are not supported with UPI AutoPay. If customers need to update their VPA (see definitions below) or bank accounts, they must cancel their existing mandate/subscription and re-subscribe.

### General Limitations

- Ad-hoc or One-Time customer-initiated purchases and merchant-initiated Force Collections are not supported.
- Recurly.js is not supported with UPI AutoPay or Pix Automatico. Use our API to facilitate requests.
- Refunds through Ebanx must be the **full** amount.
- Chargebacks are not reflected / supported at this time.
- See individual Payment Method pages for additional limitations.
- UPI App Deep Links do not support free trials at the moment.&#x20;

# Definition

Ebanx is a full-service payment management platform focused on upcoming markets such as India and Latin America. When configured with Recurly, it allows you to securely manage your transactions. You will need a relationship with Ebanx to enable this integration.

# Key details

| Feature                         | Description                                                                                                                                                                                                                             |
| ------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Services that work with Recurly | Payment Processing, Subscriptions, [Automatic Subscription Cancellation](https://docs.recurly.com/recurly-subscriptions/docs/expire-subscription#/auto-cancellation-of-a-subscription)                                                  |
| Supported Operations            | Subscription Mandate Enrollment, Recurring Transactions, Refunds                                                                                                                                                                        |
| Supported Payment Types         | [UPI - AutoPay](https://docs.recurly.com/docs/upi-autopay#/), [Pix Automatico](https://docs.recurly.com/recurly-subscriptions/docs/pix-automatico#/), [Mercado Pago](https://docs.recurly.com/recurly-subscriptions/docs/mercadopago#/) |
| Supported Card Brands           | N/A                                                                                                                                                                                                                                     |
| Gateway Specific 3DS2 Supported | No                                                                                                                                                                                                                                      |
| Card On File Supported          | No                                                                                                                                                                                                                                      |
| Regions                         | UPI AutoCollect for India, Pix Automatico and Mercado Pago in Brazil, and Mercado Pago in Mexico, Chile, Uruguay, and Argentina.                                                                                                        |
| Currencies                      | INR, BRL, ARS, CPL, MXN, or UYU                                                                                                                                                                                                         |

# Configuring Ebanx in Recurly

Follow these steps to integrate Ebanx with Recurly. Ensure you use the correct site mode (Sandbox or Production) and valid Ebanx credentials for a smooth setup.

## Step 1: Obtain Ebanx Credentials

1. **Log in to your Ebanx Account**. This will require you to engage with Ebanx and address any appropriate contracts/applicable fees separate from Recurly.

- Switch your Ebanx Dashboard to **Production mode** for production keys.
- Switch to **Sandbox mode** for sandbox keys.

2. **Go to Account Settings**: Click your name in the top-right corner and choose **Account Settings**.
3. **Select Integration**: From the four tabs in Settings, pick **Integration**.
4. **Copy your Integration Key**.

- Only the **Integration Key** will work with Recurly. The Public Integration Key will not function.

## Step 2: Enter Credentials in Recurly

1. Log in to your **Recurly** account and go to **Configuration → Payment Gateways**.
2. Click **Add a New Gateway** at the top-right.
3. From the list, choose **Ebanx**.
4. Paste your **Integration Key** into the “Integration Key” field.


<Image src="https://files.readme.io/36f169d074f9f16c9524fb217cb56bac7150d1a642e731905cbf254b1bcdcc62-Ebanx-Credentials.png" align="center" width="75% " border={true} />


## Step 3: Set Your Payment Methods

- Under **Accepted Card Types**, you won’t see any card options since this gateway currently supports regional APMs.
- Enable **UPI AutoPay**, **Pix Automatico**, and/or **Mercado Pago**under **Alternative Payment Methods**.

## Step 4: Enable Currencies

Ensure you are enabling the correct currencies per payment method.

- UPI: INR Only
- Pix Automatico: BRL Only
- Mercado Pago: BRL, ARS, CPL, MXN, or UYU.


<Image src="https://files.readme.io/1c0bc5faff0d392f4bb496f251bca479cdca5d1f461e9a5bf49865c97799879c-Ebanx-PaymentMethod-Currency.png" align="center" width="80% " border={true} />


## Step 5: Save and Enable the Gateway

1. Click **Add Payment Gateway** at the bottom.
2. You’ll see Ebanx added to your list of Production Gateways in Recurly with a status of **Enabled**.

## Step 6: Test the Configuration (Recommended)

- Perform a test transaction to confirm the integration works. It’s best to test in **development mode** on your Recurly sandbox site before going live.

## Step 7: Modify your Dunning Settings (Recommended)

- Ensure your Dunning settings do not immediately expire invoices in order to allow Retries to function properly. If the invoices are set to immediately expire a subscription, retries will not occur. Learn more about Retries on Ebanx payment methods in our [Static Retries documentation](https://docs.recurly.com/recurly-subscriptions/docs/static-retries).

## Step 8: Go Live

1. Once testing is successful, you’re ready to accept live payments through Ebanx.
2. Make sure your **Production Credentials** are entered in Recurly and your Ebanx account is in **Production mode**.
3. Make sure you have Ebanx production webhooks enabled prior to launch. See configuration steps below.

> **Pro Tip:** Keep your Ebanx credentials secure. Only authorized personnel should have access. **Note:** Always consult with your Ebanx representative or Ebanx support to ensure your account is in good standing and you’re meeting all relevant regulations.

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

<Callout icon="❗️" theme="error">
  ### Warning

  Enrollment, Mandate Status, and Payment Updates will not occur properly without webhook setup. Please follow these steps in both production and test environments in Ebanx.
</Callout>

# Other Notes

## Integrating with Ebanx

Below you will find helpful Integration Guides for payment methods supported on Ebanx. As of today, only UPI AutoPay is available.

- [UPI AutoPay Integration Guide](https://docs.recurly.com/recurly-subscriptions/docs/upi-autopay-integration-guide#/)
- [Pix Automatico Integration Guide](https://docs.recurly.com/recurly-subscriptions/docs/pix-automatico-integration-guide#)
- [Mercado Pago Integration Guide](https://docs.recurly.com/recurly-subscriptions/docs/mercado-pago-integration-guide)

## Required Fields

Ebanx will require a minimum of fields to create a mandate for a recurring subscription. The minimum required fields to submit a transaction are as follows:

### UPI AutoPay

- VPA (UPI AutoPay) (PGR Array)
- For QR / App Intent, send Payment Type / Authentication Type and omit VPA (PGR Array)
- Customer Email Address
- Customer First and Last Name
- Customer Billing Address (Street Address, City, Region/State, Country, Postal Code / PIN Code)
  - Regional Mapping:
    - Street Address is the House/Street Name and Number (EX: HOUSE NO. 32, MG ROAD)
    - City is the Locality and City in India (Ex: VILLAGE OF AMARPUR, NEW DELHI)
    - State is the State or Union Territory in India (ex: MAHARASHTRA)
    - Postal Code is the PIN Code (ex: 110019)
    - Country is the Country (ex: IN)
- Customer Phone Number

## Pix Automatico and Mercado Pago

These payment methods will require you always send certain data:

- Customer Name
- Customer Billing Address
- Customer Email Address
- Customer Phone Number
- Tax ID / Tax ID Type when the Region requires it (Brazil)

## Mandate Preferences

Payment methods on Ebanx use subscription-level **mandate IDs** assigned to a consumer’s subscription upon signup. Consumers can revoke or pause (in UPI's case) this mandate from their bank apps, which can affect the subscription in Recurly. This will be configurable in the future. Presently, consumers cancelling or pausing their mandates in their banking app will be automatically handled.

- Note: Pausing and Resuming Subscriptions in a banking app is only supported with UPI at this time.

# Subscription Behavior

## Retries and Dunning

Retries are supported on UPI AutoPay, Pix Automatico, and Mercado Pago when your Dunning Settings are **not** set to Expire Subscriptions immediately. Ensure you have your Dunning Settings loosened to avoid immediately expiring subs, so that retries can function properly.

Read more about retries on each individual methods page, and our [Static Retries](https://docs.recurly.com/recurly-subscriptions/docs/static-retries#/) documentation.

## Transaction, Invoice, and Subscription Status

When processing with  [UPI AutoPay](https://docs.recurly.com/docs/upi-autopay#/) and [Pix Automatico](https://docs.recurly.com/recurly-subscriptions/docs/pix-automatico#/), as with any asynchronous payment method in Recurly, subscriptions are immediately active, but transactions and invoices will be in a scheduled/processing state respectively until the pre-renewal notification receives an update and the payment is triggered. If customers do not authorize a subscription enrollment or payment via their respective Banking App, transactions will fail and subscriptions will be expired upon consumer rejection.

See documentation for each payment method for more information.

## Subscriptions and Transactions Limitations

There are certain behaviors that Ebanx payment methods support -- they are listed below.

- Trial Subscriptions _with payment data_ -- trials without a prior UPI enrollment will not function. Force-converting is not supported.
- Non-Trial Subscriptions
- Renewals

## Features that will not work with Ebanx APMs

### General Limitations

- Transaction type of Authorize and Capture, and Void. Ebanx transactions must be refunded.
- Subscription upgrades: Mandates stored on a consumer's Bank app control the amount and frequency. Changing this on the recurly side could cause declines.
- Trials without Payment data (payment data on file)
- Trials while using App Deep Links / Intents&#x20;
- Non-Net-0 Terms: Certain Ebanx APMs must be charged on the specific day noted in the mandate, so terms above Net-0 can cause payment failures.
- One-time transactions are not supported at this time as these payment methods support renewals only, and cannot be used for one-time transactions, merchant or customer driven.
- Account hierarchy: Mandates associated with a parent or child account will not be used in a recurring subscription – changing the hierarchy won’t affect existing subscriptions as a result.
- Aggregated / Calendar Invoicing: Taking existing subscriptions and combining them is against mandate-regulations in India, and therefore cannot be allowed.
- Bundling Subscriptions: See calendar aggregation.
- Multiple Subscriptions on a Single Account: Each individual subscription uses a mandate ID, and only one mandate ID is allowed per account.
- Merchant Admin-created Subscriptions: due to pre-debit notification and enrollment verification/consumer authentication that occurs in the consumer's app, MIT subscription enrollments are not allowed per NPCI regulations in India and Brazilian / LATAM Banking institutions.

### UPI / APAC Specific

- Billing Info Updates: Billing Info updates must be done by customers in the UPI App.

# Troubleshooting FAQs

### **Q: My UPI subscription is failing. How can I fix this?**

- Confirm the subscription price hasn’t changed without re-engaging the customer.
- Make sure the customer is responding to UPI app push notifications, especially for charges above **15000 INR**.

### **Q: I updated my customer’s VPA, but the original account was charged. How do I fix this?**

- **Billing Info Updates** made through Recurly APIs aren’t supported with UPI AutoPay. If a customer has a new VPA, they must re-enroll in the subscription.
  - Cancel the current subscription and have your customer re-subscribe using their new VPA.
  - If Customers only need to update their bank details, they can do so in the UPI App directly.

### **Q: A subscription renewal failed, and I cannot attempt collection. Why?**

- **Merchant-initiated one-time transactions** such as one-time invoices and force collections aren’t supported with UPI AutoPay. Reach out to your customer about payment options.

### Q: I converted a Pix Trial early and it declined. Why?

- **Pix Automatico** transactions have a waiting period between consumer authentication and the start date you can charge the first renewal transaction. This is sent initially in the signup request and cannot be modified. It is best to avoid forced or early conversions for Trial subscriptions on Pix.

<br />
