---
title: GoCardless
excerpt: GoCardless gateway integration documentation, configuration, implementation.
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

This feature **may not be included** in the Starter or Pro plans. If you are interested, please contact [Recurly Sales](https://recurly.com/demo/contact-sales/) to discuss upgrade options.

### Limitations

* **Transaction limits:** GoCardless imposes varying minimum and maximum transaction thresholds based on the payment method. Ensure alignment with your business requirements by reviewing the details [here](https://support.gocardless.com/hc/en-us/articles/115002831125-Transactions-and-fees-FAQs#transaction_limits).
  * Minimum ACH transaction value of $2.
* **Address requirements:** Specific payment methods demand minimum address details; ensure to gather these during the checkout process.
* Hosted Gift Card pages do not support GoCardless.
* Direct debit transactions can move from past\_due to processing status under certain conditions.
* See GoCardless' website for their list of restricted activities and business models: [https://gocardless.com/legal/restrictions/](https://gocardless.com/legal/restrictions/)
* No ability to import existing direct debit billing info via the API. However, this is possible with a professional services engagement.

# Definition

Recurly’s integration with GoCardless enables merchants to utilize the robust GoCardless platform for direct debit payment schemes in harmony with Recurly’s subscription management system.

# Key details

| Features                        | Availability                                       |
| ------------------------------- | -------------------------------------------------- |
| Services that work with Recurly | GoCardless                                         |
| Supported operations            | Charge, Recurring Billing, Refund                  |
| Supported payment types         | SEPA, ACH, BACS, BECS                              |
| Supported card brands           | N/A                                                |
| Gateway Specific 3DS2 Supported | N/A                                                |
| Card on File Supported          | N/A                                                |
| Regions                         | Europe, United Kingdom, Australia, United States   |
| Currencies                      | EUR (SEPA), USD (ACH), GBP (BACS), and AUD (BECS). |

## GoCardless + Recurly: Gateway integration

Recurly’s integration with GoCardless allows merchants to harness the robust capabilities of the GoCardless direct debit payment schemes, offering international coverage to charge customers directly from their bank. This integration requires attention to GoCardless’s transaction minimums and maximums based on payment method, ensuring alignment with your business needs. Learn about GoCardless transaction limits [here](https://support.gocardless.com/hc/en-us/articles/115002831125-Transactions-and-fees-FAQs#transaction_limits).

### Recurly integration details

SEPA and ACH are currently available through various Recurly integration points, while BACS and BECS are supported on Recurly.js, API V2, and V3. For BACS, BECS, and ACH, please contact support to enable this feature.

> \*\*Note on credentials:\*\*Merchants are encouraged to use distinct sets of GoCardless credentials across Recurly sites to avoid transaction processing issues.

## API documentation

> 📘 **GoCardless Compliance Review Required**
>
> If you are planning to utilize the API to customize your own checkout pages, be aware that this will necessitate a review and approval from GoCardless. It is essential to incorporate this review time into your development cycle. For approval, please reach out to your GoCardless partner manager or the support team.

### API versions and supported features

1. **API V3:**
   * API V3 allows for the transmission of local bank details, including:
     * IBAN bank details (SEPA)
     * Account number and routing number (ACH)
     * Account code, sort code, and type (BACS)
     * Account code and BSB code (BECS)
   * These details are included within the `billing_info` parameter.
   * [Learn more about API V3](https://developers.recurly.com/api/v2019-10-10/index.html#operation/update_billing_info).
2. **API V2:**
   * Similar to API V3, API V2 supports sending local bank details, including:
     * IBAN bank details (SEPA)
     * Account number and routing number (ACH)
     * Account code, sort code, and type (BACS)
     * Account code and BSB code (BECS)
   * These details are included within the `billing_info` parameter.
   * [Learn more about API V2](https://dev.recurly.com/docs/create-an-accounts-billing-info-bank-account).
3. **Recurly.js:**
   * Recurly.js enables the sending of tokenized bank account information to Recurly.
   * **Important:** To have bank account fields available, ensure you are using Recurly.js version 4.
   * [Learn more about Recurly.js](https://dev.recurly.com/docs/recurlyjs).

### Required information

* Please note that GoCardless mandates the provision of both the first and last names of the account holder when processing transactions.
* Mandate creation on GoCardless requires sending the consumer IP address in your payload or mandate creation will fail.

This API documentation is designed to provide clear and concise information about the capabilities of different API versions and the requirements set by GoCardless. Always ensure compliance with GoCardless requirements and stay updated with the latest API documentation for smooth and secure operations.

## Handling Automated Retries with GoCardless

Recurly supports automated retries for SEPA payments on GoCardless. [Learn more about SEPA Retries](https://docs.recurly.com/docs/sepa-retries) by visiting our documentation on the feature.

## Handling refunds with GoCardless

Managing refunds effectively is crucial for maintaining customer satisfaction and trust. Here is how refunds are handled when using GoCardless as your payment gateway:

### 1. Safer Refund Period

* GoCardless offers a feature known as the **Safer Refund Period**. This feature prevents refunds from being initiated within 7 days of the original payment request. This function is designed to enhance security and is **OFF by default**.
* [Learn more](https://developer.gocardless.com/api-reference/#refunds-create-a-refund) about the Safer Refund Period and how to create a refund with GoCardless.\
  **To Enable the Safer Refund Period:**
* If you wish to activate this feature, contact your GoCardless account manager or support team.
* It is important to adjust your billing flows to account for this delay in payment confirmations when issuing refunds.

### 2. Refund limitations

* A single GoCardless invoice can be refunded a maximum of **five times**, through partial refund amounts.
* If an attempt is made to refund an invoice more than five times, both GoCardless and Recurly will return an error, preventing further refunds on that invoice.

**Examples and scenarios:**

* Individual line items on an invoice can be returned, with a maximum of five refunds allowed for a single invoice.
* **Refunds with Credit Invoices:** If a refund is accepted by Recurly but ultimately fails due to the GoCardless Safer Refund feature, this will be treated as a gateway failure and a credit memo will be generated on the account. This credit memo can later be refunded externally if the intent is to return the money to the end customer.
* **Refunds WITHOUT Credit Invoices:** Similar to the above scenario, the account will receive credits that can be consumed rather than invoices. These credits can also be refunded externally.

### Recommendations

* If the 7-day Safer Refund feature is enabled, it is highly recommended to integrate this waiting period into your refund process. This proactive step helps to avoid conflicts and ensures a smoother refund experience for both your team and your customers.\
  By understanding and effectively utilizing GoCardless' refund features and limitations, you can create a more secure and customer-friendly refund process.

# GoCardless integration with Recurly

### Step 1: Enable GoCardless in Recurly

1. Log in to Recurly.
2. Navigate to the ‘Payment Gateways’ page and select ‘GoCardless’ from the list of available gateways under Alternative Payment Solutions.

<Image align="center" className="border" border={true} width="75% " src="https://files.readme.io/7c1c289-image.png" />

3. On the popup, select either ‘Production’ or ‘Development’ depending on your intentions for this gateway.

### Step 2: Connect with GoCardless

1. You will be redirected to the GoCardless onboarding OAuth flow to begin. If you do not have a GoCardless merchant account and credentials, you can create one during this step or click ‘Sign In’ to provide your existing credentials.
2. If you’ve chosen ‘Sign In’, enter your GoCardless credentials and choose ‘Connect Account’. Once you have been successfully authenticated, you will be redirected back to your Recurly admin dashboard.

<Image align="center" className="border" border={true} width="60% " src="https://files.readme.io/82c67b7-image.png" />

3. If you do not already have a GoCardless account, complete the onboarding process with GoCardless and wait until your account is approved by GoCardless. **Important**: Do not proceed to the next steps until your account with GoCardless is fully approved.
4. Once redirected back to Recurly, you will see a GoCardless gateway instance with a ‘Status’. If the status is not approved, you will need to contact GoCardless, or log into your GoCardless account to satisfy any further requirements. The account could be listed as ‘Action Required’ for a handful of reasons, including but not limited to:

* You have not verified your account with GoCardless.
* You have not selected a GoCardless package.
* You have not provided GoCardless with additional information about your business.

### Step 3: Configure currencies and payment methods in Recurly

1. Go to Recurly dashboard - Configuration - Currency.
2. Enable the relevant currencies for your site (SEPA - EUR, ACH - USD, BACS - GBP, BECS - AUD). If you don’t see your desired currency or payment method, please contact [support@recurly.com](mailto:support@recurly.com) to enable it for you.
3. .3. Enable GoCardless Late Failure and Chargeback notification webhooks. Recurly has automated Late Failure handling for SEPA payments, so that your gateway and GoCardless accounts are in sync. If you do not enable these webhooks, Recurly will be unaware of transaction failures within your reporting.

### Step 4: Set up Recurly plans

1. Make sure that the relevant currencies are enabled for your plan.
2. In Recurly, navigate to - Configuration - Currencies - Enable relevant currencies.

### Step 5: Configure address requirements

1. Based on the payment methods you will be using, ensure that you are collecting the required address fields during checkout (e.g., ACH requires a full address and name).

### Step 6: Configure Checkout and Hosted Pages (optional)

1. Create checkout configurations to collect payment from your customers.
2. Enable both Hosted Payment Pages and Hosted Account Management Pages in your ‘Hosted Pages’ configuration if you will be using them.
3. Make sure to collect the first and last name on your hosted pages as these are required for GoCardless transactions.

### Step 7: Set up email notifications

1. Set up and verify your email notifications for New Subscription, Subscription Change, and Payment Notification.
2. Check GoCardless documentation [here](https://support.gocardless.com/hc/en-us/categories/360000018969-Schemes) for the exact timing of your email communications based on the relevant payment methods.

### Step 8: Configure webhooks

1. Set up Recurly’s webhooks to stay updated with the status of your transactions.
2. [Learn more](https://docs.recurly.com/docs/webhooks) about setting up webhooks with Recurly.

### Step 9: Chargeback and late failure invoice setup

When SEPA payments experience a failure (typically when a customer disputes a charge) after merchant funding has occurred, Recurly can automate the chargeback process within your invoices and create a Refund Invoice marked as a chargeback. **Important**: Ensure you have ‘Webhook Options’ set to ‘Enabled’ for this feature to work.

1. Navigate to **Configuration → Invoice Templates → Invoice Settings** and scroll to a section titled **Chargebacks**.
2. Select either ‘Create a refund transaction when a chargeback is received (default)’ or ‘Manually process chargebacks’.

* Selecting the default will allow you to also select the option to Automatically expire subscriptions when a chargeback is received. You can choose to do this manually if you wish.
* Selecting the manual option will require you to create chargeback invoices on your own. Keep in mind, this will make your reporting at Recurly appear out of sync with GoCardless.

## Step 10: Test the integration (development mode)

10.1. Contact [support@recurly.com](mailto:support@recurly.com) and ask them to put your site in dev mode.\
10.2. Connect your Recurly Sandbox to GoCardless Sandbox and test your transaction flows.

### Step 11: Go Live

1. Once testing is successful and you are comfortable with the setup, switch your Recurly site from dev mode to live mode.
2. Begin processing real transactions through GoCardless.

# How to process a refund with GoCardless via Recurly

### Step 1: Review refund policies

1. Familiarize yourself with GoCardless’ Safer Refund Period feature and decide if you would like it enabled. [Learn more](https://developer.gocardless.com/api-reference/#refunds-create-a-refund) about this feature.

### Step 2: Initiate the refund

1. In your Recurly dashboard, locate the invoice for the transaction you want to refund.
2. Click on the “Refund” button, typically located at the top or bottom of the invoice page.

### Step 3: Specify refund details

1. Choose whether you want to issue a full or partial refund. If partial, specify the amount or items you want to refund.

### Step 4: Process the refund

1. Review the details and click the “Process Refund” button.
2. Wait for confirmation from GoCardless.
3. Note that GoCardless may impose a delay due to its Safer Refund feature.

### Step 5: Handle additional scenarios

1. If a refund fails due to GoCardless’ Safer Refund feature, a credit memo will be generated on the account in Recurly.
2. This can later be refunded externally if needed.