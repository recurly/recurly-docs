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

### Prerequisites & supported gateways

To integrate Apple Pay on the Web, ensure you have:

* An Apple Developer's Account and a verified domain.
* Recurly.js v4 or <a href="https://docs.recurly.com/docs/checkout" target="_blank">Checkout</a>.
* Recurly currently supports Apple Pay transactions through [Adyen](https://docs.recurly.com/docs/adyen), [Stripe](https://docs.recurly.com/docs/stripe), [Braintree](https://docs.recurly.com/docs/braintree), [Vantiv](https://docs.recurly.com/docs/vantiv), [Worldpay](https://docs.recurly.com/docs/worldpaydlocal-latam-support), Chase [Orbital](https://docs.recurly.com/docs/chase-paymentech-orbital), and [Cybersource](https://docs.recurly.com/docs/cybersource) as gateways.

### Limitations

* Not available on Recurly <a href="https://docs.recurly.com/docs/hosted-payment-pages" target="_blank">Hosted Payment Pages (HPP)</a>. 

# Description

Recurly supports Apple Pay on the Web, allowing a smooth and secure payment process on your web pages. Before initiating the integration, familiarize yourself with Apple's [getting started guide](https://developer.apple.com/apple-pay/get-started/) .

![Apple Pay on the Web](https://files.readme.io/3a0f547-ApplePay-Docs2x.png)

# Checkout flow

Once you have completed the prerequisites described above, contact Recurly Support to initiate the following actions:

* Enable the Apple Pay feature flags for your site and gateway.
* Generate Certificate Signing Request files (CSRs), which will be used to create the necessary Apple Pay Payment and Merchant Identity Certificates. You **must** use the CSRs provided by Recurly for this integration to function correctly. Since each CSR is unique to a merchant account, allow several business days for the generation of the appropriate CSRs.

# Configuration in Apple and Recurly

After receiving the necessary CSRs from Recurly Support, proceed with the following steps to generate the appropriate certificates:

1. Navigate to the Apple Developer’s and request a “Apple Pay Certificate”.  
2. Choose the correct Merchant ID on the subsequent page.
3. Upload the CSR file labeled “payment.csr”.
4. Repeat the above steps, but select “Merchant Identity Certificate” and use the “merchant\_id.csr” file in the second iteration.

For your reference, the *Merchant Identity Certificate* authenticates your merchant sessions with Apple Pay servers, while the *Apple Pay Certificate* (also known as the Payment Processing Certificate) facilitates the submission and processing of transactions on your behalf through Apple Pay.

After generating the necessary certificates, upload them to your Recurly site and complete the remaining configuration fields as detailed below:

1. Open the Recurly console and select Configuration > Apple Pay to start the setup process.

2. Enter the verified domain of your store in the format: `www.DOMAIN.com`. Important Note: After generating the CSR and uploading it to your site, avoid using the domain name listed under the cert\_UID field. This is a common mistake among new merchants setting up Apple Pay; ensure you use the actual domain of your store.

3. Input the store name as it should appear to customers during the checkout process. This name will be visible to your customers and should accurately reflect your store's branding.

4. Provide the URL that customers can visit to update their billing information. This should be formatted like `https://www.DOMAIN.com/login`. Make sure this link directs your customers to the correct page where they can easily access and update their billing details.

   * If you are utilizing the Hosted Pages Account Login, Recurly can automatically determine the management URL for you.

5. Upload the certificates to the corresponding sections as outlined below:
   * Merchant Identity Certificate: Merchant ID Certificate section.
   * Apple Pay Certificate: Payment Processing Certificate section.

6. **Bypass the “Payment Processing Private Key” and “Merchant ID Private Key” sections.** Recurly will handle these entries.

### Braintree Setup

Setting up Recurly's Apple Pay integration with Braintree differs from other gateways and involves coordination between Recurly and Braintree. 

#### 1. Enable Apple Pay on Braintree

Adhere to the guidelines provided in <a href="https://developer.paypal.com/braintree/docs/guides/apple-pay/configuration/javascript/v3#domain-registration" target="_blank">the Braintree documentation</a>.

Update the Recurly.js V4 checkout page to incorporate Apple Pay with Braintree client authorization as delineated in Recurly's developer documentation.

#### 2. Enable Apple Pay on Recurly

1. Contact Recurly to activate the **Feature Flag for Enable Apple Pay Web Payments**.
2. Select the **Enable Apple Pay** option on the Gateway Configuration page for Braintree within Recurly.

Note: When using Apple Pay with Braintree, there is no need for additional configurations in Recurly under **Configuration → Apple Pay**.

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
