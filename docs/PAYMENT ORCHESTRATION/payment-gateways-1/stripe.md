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

| Feature                             | Description                                                                                                                                                                                                                                                                                                                                                                     |
| ----------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Services that work with Recurly** | Payment processing, including Gateway Failover support, Stripe Elements (Payment, Express Checkout, LinkPay), [Dynamic Descriptors](https://docs.recurly.com/docs/payment-descriptors#/)                                                                                                                                                                                        |
| **Supported operations**            | Verification, Purchase, Auth and Capture, Void, Refund, Recurring Billing                                                                                                                                                                                                                                                                                                       |
| **Supported payment types**         |                                                                                                                                                                                                                                                                                                                                                                                 |
| Native Support                      | Credit/Debit Cards, Apple Pay, Google Pay                                                                                                                                                                                                                                                                                                                                       |
| Stripe Elements                     | Cards, Apple Pay, Google Pay, Link Pay (Cards), Cash App Pay, Revolut (UK/EU only), ACH, SEPA, BACS, BECS, iDeal. [Financial Connections](https://stripe.com/financial-connections) is required for verifying bank information. [Klarna BNPL (Recurring)](https://docs.recurly.com/update/docs/klarna-bnpl-pay-now-pay-later#/) is in private preview (BETA), but is supported. |
| **Supported card brands**           |                                                                                                                                                                                                                                                                                                                                                                                 |
| Native Support                      | Visa, MasterCard, American, Express, Discover, JCB, Diners Club, Union Pay                                                                                                                                                                                                                                                                                                      |
| Stripe Elements                     | Visa, MasterCard, American, Express, Discover, JCB, Diners Club, Union Pay, Cartes Bancaires                                                                                                                                                                                                                                                                                    |
| **Gateway Specific 3DS2 Supported** | Yes                                                                                                                                                                                                                                                                                                                                                                             |
| **Card on File Supported**          | Yes                                                                                                                                                                                                                                                                                                                                                                             |
| **Regions**                         | Global, some APMs are not supported                                                                                                                                                                                                                                                                                                                                             |
| **Currencies**                      | See <a href="https://docs.recurly.com/docs/currency-support-by-gateway" target="_blank">all available.</a> Must match in both Stripe and Recurly when using Gateway Failover.                                                                                                                                                                                                   |

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

## Ongoing maintenance

#### **Regular customer information updates**

After integration, it's essential to regularly update your customers' billing information in Stripe. Changes made in Recurly do not automatically sync, so manual updates are necessary for each customer to ensure direct payments are processed correctly in Stripe.

#### **Monitoring and maintenance**

Keep a close eye on the performance and conduct regular checks to ensure smooth operations. Also, ensure to maintain the parity of the currency and card support settings in both Stripe and Recurly to avoid any disruptions in the payment processes.

#### **Stripe Dashboard Maintenance**

Keeping an eye on your Stripe transactions in the Stripe Dashboard should be common practice. Stripe can send notices on transactions that Recurly may not receive notice of. Additionally, MetaData that Recurly sends to Stripe will be visible here.

Ensure that you are not modifying any Recurly meta-data sent to Stripe, as we rely on this detail to ensure the integration functions properly. While Stripe does give merchants access to edit these details, it is important to keep the information intact and unedited.