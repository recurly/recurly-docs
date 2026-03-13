---
title: Apple Pay on the Web
excerpt: >-
  Enable seamless transactions on your web pages with Recurly's Apple Pay on the
  Web integration. Offer your customers a secure, fast, and streamlined payment
  experience with just a touch or a glance.
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

### Use cases

* E-commerce platforms looking to enhance user experience with a swift and secure payment method.
* Subscription services aiming to streamline the payment process for their customers.
* If you need multi-domain support, please talk with Support about enabling the Merchant Registration API capability.
* While not natively supported in Recurly.js, if you want ApplePay to function in Chrome you may load the [latest version of Apple in your environment](https://developer.apple.com/documentation/applepayontheweb/loading-the-latest-version-of-apple-pay-js#Load-the-auto-updating-version-of-the-SDK).

### Prerequisites & supported gateways

To integrate Apple Pay on the Web, ensure you have:

* An Apple Developer's Account and a verified domain.
* Recurly.js v4 or <a href="https://docs.recurly.com/docs/checkout" target="_blank">Checkout</a>.
* Recurly currently supports Apple Pay transactions through [Adyen](https://docs.recurly.com/docs/adyen), [Stripe](https://docs.recurly.com/docs/stripe), [Braintree](https://docs.recurly.com/docs/braintree), [Vantiv](https://docs.recurly.com/docs/vantiv), [Worldpay](https://docs.recurly.com/docs/worldpaydlocal-latam-support), CommerceHub, Chase [Orbital](https://docs.recurly.com/docs/chase-paymentech-orbital), and [Cybersource](https://docs.recurly.com/docs/cybersource) as gateways.
* This payment method allows using [Zero Dollar Authorizations](https://docs.recurly.com/docs/payment-gateways#/zero-dollar-authorizations-zda).

### Definitions

* **FPAN**: An acronym for "Funding Primary Account Number". This is referencing the actual credit card number that is physically printed on the card itself. This is also referred to as just 'PAN' as well.
* **DPAN**: The acronym for "Device Primary Account Number". Some may also use 'Digital' in place of 'Device'. A DPAN is referring to the tokenized credit card number created by adding a consumer credit card to a Phone or Device "Wallet" system (such as iPhone Apple Wallet) and is sent to gateways and processors in place of an actual FPAN.
  * The DPAN is tied to that specific device, for example, the specific iPhone or iPad and typically is accompanied by a Cryptogram when a customer is in session.
  * DPANs are full card numbers that have different set of numbers from the FPAN which can be exposed on receipts and other UI elements.
  * DPANs are invalidated when a consumer removes the card from their device, and a new DPAN is created if they re-add the same card, or add a new card to their device. Subscriptions using a DPAN can fail due to this consumer-driven behavior and are non-recoverable. Apple has deployed a solution to improve subscription behavior using an MPAN (see below) which is not tied to the consumer device in this way.
* **MPAN**: Merchant-level Token used for Apple Pay. This type of token is not tied to the specific device like a DPAN, and is associated with the Merchant instead. MPANs are not transferrable between Merchants and thus are not suitable for M&A-related data migrations. MPANs are full card numbers that have different set of numbers from the FPAN which can be exposed on receipts and other UI elements.
  * MPANs are not invalidated if a consumer removes their card from a specific phone, iPad, or other Apple device, thus making them "subscription-friendly".
  * MPANs benefit from expiry date forwarding features, though card number changes are not received from Apple through any Account Updater feature today. Apple may receive new FPAN details themselves, but the MPAN on file will be unchanged in Recurly's system.
* **Cryptogram**: A one-time use authentication value that is created in the processing of using Apple Pay to authorize a transaction. Cryptograms are not stored and must be sent on all customer-initiated transactions.

### Best Practices and Compliance

> ❗️ Important
>
> Apple has provided guidance that merchants should migrate from DPANs to MPANs when creating recurring subscriptions. This is a requirement for Visa recurring payments, and your Recurly.js integration should be updated to accommodate this requirement.

* For return customers, please use Recurly.js even if an existing account code or billing info exists, as Recurly.js handles collecting device-related data (cryptograms) necessary for customer-initiated transactions through Apple Pay.
* Always request Merchant-level tokens (**MPANS**) for Apple Pay, to comply with Visa MPAN requirement regulations. After July, 2025, Merchants should request MPANs in their Apple Pay implementations to avoid declines. DPANs are grandfathered in, but are not guaranteed to continue functioning forever.
  * Usage of MPAN vs DPAN is exposed on the payment method by `apple_pay` or `apple_pay_merchant_token`
  * Not all issuers support returning MPANs, so not receiving one is not always an indicator of an integration issue. The consumer's Issuer may not be returning one for various reasons including lack of support at the bank level, merchant fraud concerns, or other issues downstream.
* It is up to you, the integrator, to request merchant tokens in your configuration by [specifying the recurring payment request.](https://developer.apple.com/documentation/apple_pay_on_the_web/applepaypaymentrequest/3955946-recurringpaymentrequest) in one of two ways:
  * Simple Labeling: Add the recurring flag to the ApplePay constructor. See [Recurly.js documentation](https://recurly.com/developers/reference/recurly-js/#apple-pay) for more information.
  * Advanced Labeling: Configure the RecurringPaymentRequest. See [Apple Documentation](https://developer.apple.com/documentation/apple_pay_on_the_web/applepayrecurringpaymentrequest) for more information.

### Limitations

* Not available on Recurly <a href="https://docs.recurly.com/docs/hosted-payment-pages" target="_blank">Hosted Payment Pages (HPP)</a>.

# Description

Recurly supports Apple Pay on the Web, allowing a smooth and secure payment process on your web pages. Before initiating the integration, familiarize yourself with Apple's [getting started guide](https://developer.apple.com/apple-pay/get-started/) .

![Apple Pay on the Web](https://files.readme.io/3a0f547-ApplePay-Docs2x.png)

<br />

## Checkout flow

Once you have completed the prerequisites, contact **Recurly Support** to initiate the following actions:

1. **Enable the Apple Pay Web Payments feature flag** for your site.
   * After enabling the feature flag, a new **Apple Pay** checkbox will appear in your **Gateway Settings**. Make sure this box is checked so you can upload keys and certificates under **Configuration→Apple Pay** in your Recurly site.

2. **Generate Merchant ID and Payment Processing Keys**
   Recurly Support will provide the keys you need for Apple Pay integration.

3. **Generate Certificate Signing Requests (CSRs)**
   These CSRs are required to create the **Apple Pay Payment** and **Merchant Identity** certificates. Each CSR is unique to your merchant account, so allow several business days for these files to be generated by Recurly Support. **You must use the Recurly-provided CSRs** to ensure the integration functions correctly.

## Configuration in Apple and Recurly

After receiving the necessary **keys** and **CSRs** from Recurly Support, follow these steps to create certificates in the **Apple Developer** portal and configure them in Recurly:

1. **Request an “Apple Pay Certificate”** in the Apple Developer portal.
2. **Select the correct Merchant ID** on the following page.
3. **Upload the CSR** named `payment.csr`.
4. Repeat the above steps, but this time choose **“Merchant Identity Certificate”** and upload the `merchant_id.csr` file.

> **Tip**:
>
> * The **Merchant Identity Certificate** authenticates your merchant sessions with Apple Pay servers.
> * The **Apple Pay Certificate** (Payment Processing Certificate) is used to process transactions through Apple Pay.

### Upload certificates and finalize setup in Recurly

1. **Open the Recurly console** and select **Configuration→Apple Pay** to begin setup.
2. **Enter your verified domain** in the format `www.DOMAIN.com`.
   * **Important**: Do not use the domain listed under the `cert_UID` field. This is a common mistake. Always use your actual store domain.
3. **Input your store name**, as it should appear to customers during checkout.
4. **Provide a link** where customers can update billing information, e.g., `https://www.DOMAIN.com/login`.
   * If you use **Hosted Pages Account Login**, Recurly can determine this URL automatically.
5. **Upload the keys and certificates** in the corresponding fields:
   * **Payment Processing Key** → _Payment Processing Private Key_
   * **Merchant ID Key** → _Merchant ID Private Key_
   * **Merchant Identity Certificate** → _Merchant ID Certificate_
   * **Apple Pay Certificate** → _Payment Processing Certificate_

Once these steps are complete, you’ll be able to accept Apple Pay transactions via your Recurly site. If you have any questions or encounter issues, contact **Recurly Support** for assistance.

### Braintree Setup

Setting up Recurly's Apple Pay integration with Braintree differs from other gateways and involves coordination between Recurly and Braintree.

#### 1. Enable Apple Pay on Braintree

Adhere to the guidelines provided in <a href="https://developer.paypal.com/braintree/docs/guides/apple-pay/configuration/javascript/v3#domain-registration" target="_blank">the Braintree documentation</a>.

Update the Recurly.js V4 checkout page to incorporate Apple Pay with Braintree client authorization as delineated in Recurly's developer documentation.

#### 2. Enable Apple Pay on Recurly

1. Contact Recurly to activate the **Feature Flag for Enable Apple Pay Web Payments**.
2. Select the **Enable Apple Pay** option on the Gateway Configuration page for Braintree within Recurly.

Note: When using Apple Pay with Braintree, there is no need for additional certificate configurations in Recurly under **Configuration → Apple Pay**.

# FAQs

#### 1. What is Apple Pay on the Web?

Apple Pay on the Web is a payment method that allows customers to make secure and fast payments on websites using Apple Pay. It is supported through Recurly.js v4 and can be integrated into your web pages for a streamlined checkout experience.

#### 2. What are the prerequisites for integrating Apple Pay on the Web with Recurly?

Before integrating Apple Pay on the Web with Recurly, you need to:

* Create an Apple Merchant ID and sign up for an Apple Developer's Account.
* Verify the domain where your checkout page will reside.
* Upgrade to Recurly.js v4.
* Add a supported payment gateway to your Recurly site.

#### 3. How do I enable Apple Pay on the Web for my website?

To enable Apple Pay on the Web, follow the detailed guide in the "Getting Started" section of the user guide. It involves setting up your Apple Developer's account, configuring settings in both the Apple and Recurly platforms, and working closely with Recurly Support to enable necessary features and obtain Certificate Signing Request (CSR) files.

#### 4. What are Apple Pay Certificates and why are they necessary?

Apple Pay Certificates, including the Merchant Identity Certificate and Payment Processing Certificate, are essential for authenticating your merchant sessions with Apple Pay servers and processing transactions on your behalf. They ensure secure and smooth transactions through Apple Pay on your website.

#### 5. How do I set up Apple Pay with Braintree?

Setting up Apple Pay with Braintree involves a different process compared to other gateways. You need to follow Braintree's Apple Pay documentation to enable it on Braintree, and then enable the feature flag for Apple Pay web payments on Recurly. There is no need for additional configurations under "Configuration → Apple Pay" in Recurly when using Apple Pay with Braintree.

#### 7. Can I use Apple Pay on the Web with Recurly hosted payment pages?

No, Apple Pay on the Web is currently not supported on Recurly hosted payment pages. It is designed to be integrated into your web pages through Recurly.js v4. However, Checkout uses Recurly.js v4 and therefore you can use Apple Pay on the Checkout pages. See [Checkout](https://docs.recurly.com/docs/checkout) for more info.

#### 8. How do I contact Recurly Support for assistance?

For assistance with setting up Apple Pay on the Web or any other inquiries, you can reach out to [Recurly Support](https://support.recurly.com/)  through their support page.

#### 9. Where can I find detailed documentation for integration?

You can find detailed documentation and guidelines for integration in the [Recurly.JS documentation](https://developers.recurly.com/reference/recurly-js/#apple-pay) .

#### 10. What do I do when my CSRs are about to expire?

Reach out to Recurly Support to have them generate new CSRs for you. At this stage, we recommend you delete and add all files yourselves to control any downtime that may occur once the old files are removed. This way you can minimize any potential impact that may occur for the customers who use Apple Pay.
