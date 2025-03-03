---
title: Ebanx (UPI AutoPay)
excerpt: ''
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

## Limitations

* Customer mandates cannot be migrated to Recurly if they exist on another platform. Customers must cancel those mandates and resubscribe per RBI rules.
* RBI mandates limit individual transactions to 15000 INR without going through a consumer two-factor flow. Plans or the combined amount of plans, if sent in the same purchase signup request, should be at or below this amount to avoid rejections on renewals.
* Ad-hoc or One-Time customer-initiated purchases and merchant-initiated Force Collections are not supported with UPI AutoPay.
* Billing Info updates are not supported with UPI AutoPay. If customers need to update their VPA (see definitions below) or bank accounts, they must cancel their existing mandate/subscription and re-subscribe.

# Configuring Ebanx gateway in Recurly

### Step 1: Obtain your Ebanx credentials

* Log into your Ebanx Account. If you do not have an account, you will need to sign up for one through Ebanx.
  * For Production Keys, ensure you have toggled your Ebanx Dashboard to Production mode.
  * For Sandbox Keys, ensure you have toggled your Ebanx Dashboard to Sandbox mode.
* Click on your name in the upper right corner and select **Account Settings**
* Within your Settings page, there will be four tabs. Choose **Integration**.
* Obtain your **Integration Key** from your Ebanx dashboard.
  * Click 'Copy' next to **Integration Key**. Your Public Integration Key will not function in Recurly.

<Image align="center" src="https://files.readme.io/a958a60c6c1cc4451b3e12567d98fbc415ffe3cef3eedfb1a4c49c4b65a72055-Screenshot_2024-10-08_at_1.43.49_PM.png" />

### Step 2: Enter Ebanx credential in Recurly

* Log into your Recurly account and navigate to the Payment Gateways page.
* Click on the "Add a New Gateway" button at the top right of the Payment Gateways page.
* Select “Ebanx” from the list of available gateways.
* Enter your **Integration Key** into the “Integration Key” field.

### Step 3: Set your payment methods

* Under the ‘ACCEPTED CARD TYPES’ header, you will not see any card options as this gateway supports UPI - AutoPay only at the moment.
* Enable 'UPI - AutoPay' under Alternative Payment Methods.

### Step 4: Enable currencies

* Use the selection tool on the left to add the currencies your Ebanx gateway accepts.
* If you are accepting UPI, enable 'INR'.

### Step 5: Save and enable the gateway

* After entering all the required information, click on the "Add Payment Gateway" button at the bottom of the page.
* You will see that Ebanx has been added to your list of Production Gateways in Recurly with a status of "Enabled".

### Step 6: Test the configuration (recommended)

* Make a test transaction to ensure that the integration is working correctly. This can be done in development mode for your sandbox site in Recurly before moving to a live environment.

### Step 7 Go live

* After testing, if everything is working as expected, you are ready to accept live payments through the Ebanx gateway via Recurly.
* Ensure, once you go live, that you enter Production Credentials to your Recurly Site, and have Ebanx in production mode.

**Pro Tip:** Keep your Ebanx credentials secure and ensure only authorized personnel have access to this information.\
*Please note:* Always consult with your Ebanx account representative or support resources to ensure that your account is in good standing and that you are compliant with all relevant regulations and requirements.

# UPI - AutoPay on Ebanx Best Practices

UPI, or Unified Payments Interface, is a real-time payment system in India that allows users to transfer money between bank accounts, businesses, and individuals. UPI is a mobile-based system that combines multiple bank accounts into a single app, allowing users to make payments using a variety of methods including a VPA or Virtual Payment Address. A VPA is a digital ID that takes the place of banking details.

### What is a VPA?

VPA IDs are structured like so:`payer@bankname`

Within the UPI application, consumers have the ability to pause or cancel their subscriptions without interacting with a Recurly user interface. They are also required to confirm payments that are equal to or higher than 15.00 INR amounts. Consumers have 1 hour from initial push notification of a 15.00+ INR charge to confirm the payment.

Consumers also receive a pre-renewal push notification to the UPI app between 24 and 48 hours ahead of their charge-date. Consumers can pause or cancel at that time through their UPI app.

### Recommended Integration

UPI AutoPay is a highly regulated payment method, and not all of Recurly's API functionality will work with this payment method.

* **Creating Subscriptions**: You can use the subscription or purchase endpoints to create subscriptions using UPI AutoPay VPAs. You must reference the VPA value in our `payment_gateway_references` object and provide the VPA as the `token` value and the `reference_type` should be `upi_vpa`.
  * Enrollment actions will result in a Pending transaction that will be later updated after the customer interacts with the UPI application. This transaction will move into a Approved state if the customer confirms the enrollment successfully. If the customer does not confirm the subscription enrollment *or* the enrollment encounters an error, the Transaction will be failed.
  * Keep in mind, the VPA will still exist on the Billing Info, so if it needs to be updated, the Billing Info should be deleted and re-added during a second sign up attempt. Otherwise, send the Account Code or Billing Info ID with the existing VPA to have the customer re-attempt enrollment.
* **Billing Information Updates**: If a customer needs to update their VPA, their current subscription must be cancelled and the consumer must re-enroll with their new VPA. Updating the VPA on file will not change the mandate or bank account associated with their subscription. If the customer is not updating their VPA, they can update their bank details in the UPI app itself.
* **Cancellations**: If a customer cancels their subscription within the UPI App, ensure you're listening to Recurly webhooks to update your own records. Subscriptions will be automatically cancelled in these instances.
* **Paused Subscriptions**: If a customer pauses their subscription within the UPI App, ensure you're listening to Recurly webhooks to update your own records. Subscriptions will be automatically paused in these instances.
* **Resumed Subscriptions**: If a customer resumes their subscription after cancellation within the UPI App, ensure you're listening to Recurly webhooks to update your own records. Subscriptions will be automatically resumed in these instances. If you do not wish to accept subscriptions that go through this flow (pause, resume), you can cancel subscriptions using Recurly APIs when you receive a pause webhook on a given subscription.

### Gateway Tokens

UPI requires using Recurly's gateway token management, as UPI uses a 'Virtual Payment Account' identifier that a consumer sets up within their UPI application. It may look like this: **payer\@bankname**. Ensure your integration to Recurly allows for sending this value to Recurly via`payment_gateway_references` and `gateway_code` in the V3 API only.

See Recurly's API documentation for more information on how to use these values in your integration.

### Net Terms and Subscription Updates

Since UPI charge windows are very limited, it is advised to **avoid using non-zero Net Terms** other than '0' to avoid failed payments.

Additionally, UPI mandates for monthly, *fixed*-price subscriptions require cancellation and customer-engagement to recreate the mandate. Subscription price updates for fixed-price subscriptions are not supported with UPI - Recurring.

### Mandate Preferences

UPI - Recurring makes use of a mandate ID that is assigned to a consumer's subscription upon signing up. Consumers have the ability to revoke or pause that mandate from the UPI app outside of Recurly's system. This capability can cause subscriptions to become past due, expire or pause depending on the settings you select:

Selecting your Mandate Preferences in **Invoice Settings** will require going into Configuration > Invoice Templates > Invoice Settings and configuring one of two options:

* Automatically handle Subscriptions:
  * Automatically Cancel the Subscription: This will, if the customer has cancelled their UPI mandate within the UPI App, allow subscriptions in Recurly to auto-expire rather than going into dunning.
  * Automatically Pause the Subscription: This will, if the customer has paused their UPI mandate within the UPI App, allow subscriptions in Recurly to auto-pause rather than continue to bill.
* Manually handle Subscriptions:
  * Manually process mandate revocations and pauses: This will, if a customer either pauses or cancels their UPI mandate, allow you to drive actions against subscriptions yourself. This option will only send webhooks for subscription lifecycle events and will not automatically take action on subscriptions.

## Recommended Webhooks

Since UPI - Recurring customer actions are outside of Recurly's view, our Ebanx integration supports notifying Recurly when a customer has cancelled or paused their UPI mandate. It is recommended to listen for certain Recurly webhooks if you have selected 'Manual' in your Mandate Preferences settings.

* [Cancelled Subscription](https://recurly.com/developers/reference/webhooks/#canceled-subscription): Will be sent if the customer cancels their UPI mandate externally.
* [Paused Subscription](https://recurly.com/developers/reference/webhooks/#paused-subscription) Will be sent if the customer pauses their UPI mandate externally.
* [Resumed Subscription](https://recurly.com/developers/reference/webhooks/#resumed-subscription) Will be sent if the customer unpauses their UPI mandate externally.

### UPI Retries

UPI, given the constraints around charge windows, will retry upon failure event from Ebanx in the following flow:

1. First retry 10 minutes after initial failure
2. Second through final (up to 8) retries every hour, on the hour, after the first retry.

UPI transactions can be retried up to 9 times after the initial failure, for a total of 10 attempts. If after the 9th retry

## Troubleshooting FAQs

#### Q: My UPI Subscription is failing, how can I fix this?

* Ensure the subscription price has not changed without customer-engagement to re-subscribe.
* Ensure your Mandate Management settings are set properly. If they are set to manual, you may have missed a webhook that requires a change to the subscription status.
* Ensure your customer is responding to the UPI application push notifications when pre-renewal notifications are sent or on charges that are above 15 INR.

#### **Q: I updated my customer's VPA, but the original bank account was charged. How do I fix this?**

* Billing Info Updates are not supported when using UPI AutoPay. Cancel the current subscription and have your customer resubscribe with their new VPA.