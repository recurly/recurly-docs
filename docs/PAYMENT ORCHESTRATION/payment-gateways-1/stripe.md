---
title: Stripe
excerpt: >-
  Discover seamless financial transactions with Recurly's Stripe integration,
  allowing easy account setup and ensuring continuity with Gateway Failover for
  a streamlined payment process that adapts to your business needs.
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

This payment gateway or setting is available to all customers on any Recurly subscription plan.

### Prerequisites

* Access to Recurly Payment Gateway Configuration page.
* An active Stripe account (existing or newly created).
* Consistency in currency and card type support when utilizing Gateway Failover.

### Limitations

* Updates in the billing information on Recurly do not reflect automatically on Stripe customers.
* Necessitates manual search for the most recent Stripe customer while processing payments directly inside of Stripe.

# Definition

The integration of Stripe with Recurly facilitates a smooth pathway for managing your financial transactions. Whether you are a new user applying for a Stripe account or already hold one, the process is designed to be straightforward and efficient. It is essential to note that changes in billing information in Recurly accounts do not transfer automatically to Stripe, requiring manual updates for direct Stripe payments.

> **Note**: Visit our [guide on testing your gateway configurations ](https://docs.recurly.com/docs/how-to-test-your-gateway)in Recurly to ensure your payment processes are set up correctly-

# Key details

| Feature                             | Description                                                                                                                                                                                                                                                                                                                                                          |
| ----------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Services that work with Recurly** | Payment processing, including Gateway Failover support, Stripe Elements (Payment, Express Checkout, LinkPay), [Dynamic Descriptors](https://docs.recurly.com/docs/payment-descriptors#/), [MOTO](https://docs.recurly.com/recurly-subscriptions/docs/moto-transactions#/)  Processing                                                                                |
| **Supported operations**            | Zero dollar Verification, Purchase, Auth and Capture, Void, Refund, Recurring Billing                                                                                                                                                                                                                                                                                |
| **Supported payment types**         |                                                                                                                                                                                                                                                                                                                                                                      |
| Native Support                      | Credit/Debit Cards, Apple Pay, Google Pay                                                                                                                                                                                                                                                                                                                            |
| Stripe Elements                     | Cards, Apple Pay, Google Pay, Link Pay (Cards), Cash App Pay, Revolut (UK/EU only), ACH, SEPA, BACS, BECS, iDeal, and [Klarna](https://docs.recurly.com/recurly-subscriptions/docs/klarna-bnpl-pay-now-pay-later#/) (Pay Now, Pay Later, BNPL). [Financial Connections](https://stripe.com/financial-connections) is required for verifying bank information.        |
| **Supported card brands**           |                                                                                                                                                                                                                                                                                                                                                                      |
| Native Support                      | Visa, MasterCard, American, Express, Discover, JCB, Diners Club, Union Pay                                                                                                                                                                                                                                                                                           |
| Stripe Elements                     | Visa, MasterCard, American, Express, Discover, JCB, Diners Club, Union Pay, Cartes Bancaires                                                                                                                                                                                                                                                                         |
| **Gateway Specific 3DS2 Supported** | Yes                                                                                                                                                                                                                                                                                                                                                                  |
| **Card on File Supported**          | Yes                                                                                                                                                                                                                                                                                                                                                                  |
| **Regions**                         | Global, some APMs are not supported                                                                                                                                                                                                                                                                                                                                  |
| **Currencies**                      | See <a href="https://docs.recurly.com/docs/currency-support-by-gateway" target="_blank">all available.</a> Must match in both Stripe and Recurly when using Gateway Failover.                                                                                                                                                                                        |
| **Other Gateway Feature Support**   | [Level 2 Data, Level 3 Data](https://docs.recurly.com/recurly-subscriptions/docs/level-2-and-level-3-cedp-guide), Payment Elements, Payment Method Tokens, [India E-Mandates](https://docs.recurly.com/recurly-subscriptions/docs/e-mandates-with-cards-in-india#/) / [RBI Compliance](https://docs.recurly.com/recurly-subscriptions/docs/rbi-regulations-update#/) |

<br />

# Integrate Stripe with Recurly

## Setup

#### **Step 1: Your Stripe Account**

Ensure that you have an active Stripe account. If you don't have one, use <a href="https://stripe.com/legal/restricted-businesses" target="_blank" rel="noopener noreferrer">this list</a> to check that your business can process on the Stripe gateway. If your business is listed as a restricted or otherwise prohibited business type, you will not be able to use the Stripe gateway.

#### **Step 2: Access Recurly payment gateway configuration page**

Navigate to the [Recurly Payment Gateway Configuration page](https://app.recurly.com/go/configuration/payment_gateways/new).

#### **Step 3: Choose Stripe as your payment gateway**

On the Recurly Payment Gateway Configuration page, you'll find an option to select your preferred payment gateway. Choose "Stripe" from the list of available gateways.

#### **Step 4: Log in to or Create your Stripe account**

You will be prompted to log in to your Stripe account or you can enter your email and follow the prompts to set up a new Stripe account. Follow the prompts to complete this step.

#### **Step 5: Configure your settings**

After logging in to your Stripe account, you'll be redirected back to the Recurly platform where you can configure your payment settings according to your preferences and business requirements. This includes:

* Excluding this instance from Gateway Failover
* Setting up Alternative Payment Methods (Apple Pay or Google Pay)
* Setting up currency preferences

#### **Step 6: Review gateway failover settings**

If you plan to use the [Gateway Failover](https://docs.recurly.com/docs/gateway-failover) feature, review and ensure that the settings in both Stripe and Recurly match in terms of supported currencies and card types to facilitate seamless failover processes.

#### **Step 7: Test the integration**

Before going live, test the integration to ensure that everything is working correctly. Recurly offers a development environment where you can conduct test transactions to verify the setup.

#### **Step 8: Go live**

Once you have tested and confirmed that the integration works as expected, switch from sandbox to production environment to start processing real transactions.

**Notes:** Stripe does not require explicit zero dollar verification configured at Recurly.

## Payment Method Enablement

You can enable payment methods within your Stripe Dashboard. Keep in mind, if you are using Stripe Elements to process payments, only enable those that Recurly can support (see above). Enablement of a payment method not on the supported list will result in payment failures.

## Authorization and capture

This gateway supports Recurly's authorization and capture feature, facilitating pre-authorization of funds and their subsequent capture. This process confirms fund availability before transaction completion, optimizing payment processing on the Recurly platform. For a detailed understanding of how this feature can benefit your transactions, we encourage you to visit our [dedicated page on authorization and capture](https://docs.recurly.com/docs/auth-and-capture).

#### **Integration with Stripe**

Stepping into a seamless financial operation is easy with Recurly's Stripe integration. Begin your journey by navigating to the [Recurly Payment Gateway Configuration](https://app.recurly.com/go/configuration/payment_gateways/new) page. Here, you can either log in using your existing Stripe account or initiate the process for a new account.

Stripe onboarding uses OAuth credential authentication. You will not need to copy/paste your credentials using this gateway.

## Stripe Webhook Behavior

Recurly supports several webhooks with Stripe including gateway token lifecycle events, external Account Updater lifecycle events, and certain transaction lifecycle events. There is no additional configuration needed in your Stripe dashboard or Recurly site other than asking your Recurly contact to enable a feature flag on your behalf.

* **Payment method and Customer token lifecycle events**
  * Payment Method "Detach" Events: This webhook will disable billing infos in Recurly if a payment method token at Stripe is deleted within the Stripe Dashboard. This will cause active subscriptions to go into dunning if there is no additional payment method on file.
  * Customer Deletion Events: Similar to Payment Method "Detach" events, deleting a Stripe Customer from the Stripe dashboard will delete all associated payment methods stored at Stripe. Doing so will have a similar effect in that active subscriptions will no longer have valid billing info, and may go into dunning if there is no other payment method on file.
  * Payment Method "Update" Events: Certain elements of a Stripe gateway token can be updated within the Stripe Dashboard, such as an expiration date. When this occurs, Recurly will update the billing info expiration date on file automatically.
  * Account Updater Events: If you are using Account Updater at Stripe, Recurly will consume events driven by Stripe's Account Updater service to keep payment gateway tokens on file at Recurly up to date and in sync.
* **Transaction Lifecycle Events**
  * Expired Authorization Events: If you are using Auth and Capture logic with Stripe, uncaptured authorizations may expire if not captured within 7 days. In this case, the authorization will be updated to a Void status in Recurly and can no longer be captured.
  * Hard Decline Events: In certain cases, Stripe may update a charge to reflect new retry advice. In cases where Stripe deems it necessary, Recurly will stop retries on a previously soft-declined transaction.
  * Chargeback Dispute Events: If you receive a chargeback for a card payment, and you are using the early access Chargeback management feature, you will see Refund Invoices with an origin of Chargeback shown in your Recurly dashboard -- depending on your settings, the affected subscription can be automatically expired.
  * Radar Review Events: If you are setting up 'review' rules in Stripe Radar, we will return `approved_fraud_review` responses via API when these rules trigger in Stripe. If you have Stripe Webhooks enabled for Recurly (reach out to Recurly Support), when you close a review Recurly will take certain actions on the transaction. You can learn more about Stripe's Review process on their [documentation](https://docs.stripe.com/radar/reviews).
    * If you mark a Review as Closed with reason `canceled`, Recurly will **automatically void pending Auths, or Void/Refund Purchases.**
    * If you mark a Review as Closed with reasons of including `approved`, `redacted`, or `acknowledged`, Recurly will take no action on the transaction.

## Special Payment Method Handling

### India Mandates with Credit Cards

Recurly now supports creating e-mandates for usage with Subscriptions when processing recurring transactions for customers located in India. As related to the [RBI mandates](https://docs.recurly.com/recurly-subscriptions/docs/rbi-regulations-update#/), recurring e-mandates are required for customers in the India region. To use e-mandates with Stripe and Recurly, payment flows are very similar to standard card subscription management, but with some key differences including:

* **Integration Style**: Since India **requires** all CIT/ Subscription Signups to go through 3DS, it is recommended to **combine** your subscription creation and customer interactions into a single step instead of adding the billing information via verification and setting. up a subscription in two steps. See our [integration guide for Cards in India](https://docs.recurly.com/recurly-subscriptions/docs/e-mandates-with-cards-in-india#/) for more details.
* **Public Preview / BETA**: E-mandates in India is in Public Preview at Stripe, which may come with some unintended issues until the implementation is stable at the gateway. Please be aware and conscientious of issues that may arise without notice. Our support team is happy to field escalations in the event of an issue.
* **Single Subscription per Account**: Since e-mandates are stored at the Customer Account level at Recurly, only one active subscription can be present on an account at one time, or you will risk invalidating older subscriptions. It is advised that you do not add multiple subscriptions to a customer account if they are located in India.
* **Transactions are asynchronous**: Due to the pre-renewal notification requirement in India, card transactions using an e-mandate will go into a Scheduled state with a Pending invoice for a period of 26 hours after submission to Stripe. Within this timeframe, customers will be notified via their bank application of choice of a pending mandate creation or payment request. At that time, they can approve the mandate or payment request, or they may decline it. You listen for updates, you will want to make use of payment and invoice webhooks for status updates.
* **Subscriptions can be cancelled automatically**: If a customer cancels their mandate through their banking app of choice, when Recurly submits a transaction to Stripe on renewal, we may receive an indicator that the mandate was cancelled by the customer. In these cases, we will cancel the subscription immediately. You may work with the customer to update their payment method, or revoke their access to services within your environment.
* **Billing country requirements**: To trigger an e-mandate for an India customer, ensure you are sending their full billing address, including the country (IN) so that we can request the mandate from Stripe effectively. Without the India country indicator, an e-mandate may not be requested, and renewals will likely fail.
* **Webhook requirements**: Since payments are asynchronous, you will need to ensure your Recurly site is set up to receive Stripe webhooks. Please contact Recurly Support about enabling async status updates for Stripe. See [Stripe Webhook Behavior](https://docs.recurly.com/recurly-subscriptions/docs/stripe#/stripe-webhook-behavior) details for more information.
* **Mandate Amounts** are calculated based on your plan amount, plus taxes, plus an 18% addition to allow for plan amount changes over the lifetime of a subscription. Mandate amounts to not include any discounts to avoid undervaluing the overall mandate amount.
* **Customer interaction indicator** is visible in the UI when a transaction in a Scheduled state. This indicates whether or not a customer needs to interact with their banking application, and when they must respond by, or risk the mandate / transaction going into a failed state. If customers do not respond to bank push notifications in a timeline fashion, subscription signups and renewal payments can be marked failed if their interaction is required.
* **3DS Requirement**: RBI mandates all customer-in-session payments be validated via 3DS including subscription signups and one-time transactions. If, for any reason, a renewal triggers a 3DS verification response, ensure you have the [3DS Dunning Email ](https://docs.recurly.com/recurly-subscriptions/docs/dunning-configuration-for-3ds-2-declines#/)enabled and a valid customer email address on file to ensure customers can come into session and resolve any consumer authentication requirements. 3DS usage on Stripe will require an integration with our Recurly.js product. If you are not integrated today, please look through our [implementation guide on 3DS processing](https://docs.recurly.com/recurly-subscriptions/v1.1/docs/3d-secure-20-integration-guide#/).

## Ongoing maintenance

#### **Regular customer information updates**

After integration, it's essential to regularly update your customers' billing information in Stripe. Changes made in Recurly do not automatically sync, so manual updates are necessary for each customer to ensure direct payments are processed correctly in Stripe.

#### **Monitoring and maintenance**

Keep a close eye on the performance and conduct regular checks to ensure smooth operations. Also, ensure to maintain the parity of the currency and card support settings in both Stripe and Recurly to avoid any disruptions in the payment processes.

#### **Stripe Dashboard Maintenance**

Keeping an eye on your Stripe transactions in the Stripe Dashboard should be common practice. Stripe can send notices on transactions that Recurly may not receive notice of. Additionally, MetaData that Recurly sends to Stripe will be visible here.

Ensure that you are not modifying any Recurly meta-data sent to Stripe, as we rely on this detail to ensure the integration functions properly. While Stripe does give merchants access to edit these details, it is important to keep the information intact and unedited.
