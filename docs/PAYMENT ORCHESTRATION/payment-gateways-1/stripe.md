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

| Feature                         | Description                                                                                                  |
| ------------------------------- | ------------------------------------------------------------------------------------------------------------ |
| Services that work with Recurly | Payment processing, including Gateway Failover support, Stripe Elements (Payment, Express Checkout, LinkPay) |
| Supported operations            | Purchase, Auth and Capture, Void, Refund, Recurring Billing                                                  |
| Supported payment types         |                                                                                                              |
| Native Support                  | Credit/Debit Cards, Apple Pay, Google Pay                                                                    |
| Stripe Elements                 | Cards, Apple Pay, Google Pay, Link Pay (Cards), Cash App Pay, Revolut (UK/EU only)                           |
| Supported card brands           |                                                                                                              |
| Native Support                  | Visa, MasterCard, American, Express, Discover, JCB, Diners Club, Union Pay                                   |
| Stripe Elements                 | Visa, MasterCard, American, Express, Discover, JCB, Diners Club, Union Pay, Cartes Bancaires                 |
| Gateway Specific 3DS2 Supported | Yes                                                                                                          |
| Card on File Supported          | Yes                                                                                                          |
| Regions                         | Global, some APMs are not supported                                                                          |
| Currencies                      | Must match in both Stripe and Recurly when using Gateway Failover                                            |

## Authorization and capture

This gateway supports Recurly's authorization and capture feature, facilitating pre-authorization of funds and their subsequent capture. This process confirms fund availability before transaction completion, optimizing payment processing on the Recurly platform. For a detailed understanding of how this feature can benefit your transactions, we encourage you to visit our [dedicated page on authorization and capture](https://docs.recurly.com/docs/auth-and-capture).

#### **Integration with Stripe**

Stepping into a seamless financial operation is easy with Recurly's Stripe integration. Begin your journey by navigating to the [Recurly Payment Gateway Configuration](https://app.recurly.com/go/configuration/payment_gateways/new) page. Here, you can either log in using your existing Stripe account or initiate the process for a new account.

Stripe onboarding uses OAuth credential authentication. You will not need to copy/paste your credentials using this gateway.

#### **Understanding Stripe customer updates**

Recurly and Stripe work together to streamline subscription billing; however, **changes to billing or account information in Recurly do not currently sync automatically from Stripe.** If you process payments directly in Stripe, please verify and update the corresponding customer record there. For accuracy, remember to use the most recently created Stripe customer record.

> **Looking ahead**: We’re actively working on enhancements that will better sync Recurly and Stripe customer data, reducing the need for manual updates. Stay tuned for updates!

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

1. You can enable payment methods within your Stripe Dashboard. Keep in mind, if you are using Stripe Elements to process payments, only enable those that Recurly can support (see above). Enablement of a payment method not on the supported list will result in payment failures.

## Ongoing maintenance

#### **Regular customer information updates**

After integration, it's essential to regularly update your customers' billing information in Stripe. Changes made in Recurly do not automatically sync, so manual updates are necessary for each customer to ensure direct payments are processed correctly in Stripe.

#### **Monitoring and maintenance**

Keep a close eye on the performance and conduct regular checks to ensure smooth operations. Also, ensure to maintain the parity of the currency and card support settings in both Stripe and Recurly to avoid any disruptions in the payment processes.

#### **Stripe Dashboard Maintenance**

Keeping an eye on your Stripe transactions in the Stripe Dashboard should be common practice. Stripe can send notices on transactions that Recurly may not receive notice of. Additionally, MetaData that Recurly sends to Stripe will be visible here.

Ensure that you are not modifying any Recurly meta-data sent to Stripe, as we rely on this detail to ensure the integration functions properly. While Stripe does give merchants access to edit these details, it is important to keep the information intact and unedited.