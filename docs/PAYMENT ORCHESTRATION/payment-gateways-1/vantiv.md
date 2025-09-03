---
title: WorldPay US eCommerce (formerly Vantiv)
excerpt: >-
  Experience secure and efficient payment processing with Recurly’s integration
  for WorldPay eCommerce (formerly known as Vantiv). Leverage the potential of
  an established platform offering account update automation and fraud
  filtering, ensuring a smooth payment experience.
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

* A WorldPay eCommerce (formerly Vantiv) merchant account
* WorldPay's approval for Recurly connection
* Configuration settings adjusted to incorporate WorldPay's automatic account updater (if required)

### Limitations

* Merchants need to initiate the connection by requesting WorldPay to allow Recurly access
* Fraud filtering and account updater functionalities rely on individual gateway settings and WorldPay account manager's guidance.
* Check if your business is on Worldpay's list of [Prohibited Business types](http://support.worldpay.com/support/kb/gg/billdesk/content/prohibitedmerchantcategories.htm).

> 🚧 Warning
>
> If you don’t have a Vantiv/Litle Merchant ID and instead have a Worldpay username and password, use [these directions](https://docs.recurly.com/docs/worldpaydlocal-latam-support) instead.

# Definition

The WorldPay eCommerce (formerly known as Vantiv or the Litle platform) facilitates reliable payment processes through Recurly, offering additional functionalities like automatic account updating and fraud filtering to enhance payment security and efficiency.

> **Note**: Visit our [guide on testing your gateway configurations ](https://docs.recurly.com/docs/how-to-test-your-gateway)in Recurly to ensure your payment processes are set up correctly.

# Key details

| Feature                         | Description                                                                                                |
| ------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| Services that work with Recurly | Credit Cards                                                                                               |
| Supported operations            | Transaction Processing (Verify, Purchase, Separate Authorize and Capture, Void, Refund)                    |
| Supported payment types         | Credit Card, Apple Pay, SEPA, ACH                                                                          |
| Supported card brands           | Visa, MasterCard, Amex, Discover, UnionPay, JCB, Diners Club                                               |
| Gateway Specific 3DS2 Supported | No                                                                                                         |
| Card on File Supported          | Yes                                                                                                        |
| Regions                         | US and Canada                                                                                              |
| Currencies                      | See <a href="https://docs.recurly.com/docs/currency-support-by-gateway" target="_blank">all available.</a> |

Recurly is compatible with **WorldPay eCommerce**, previously known as the Vantiv or Litle platform. Before initializing the connection between your Recurly account and WorldPay eCommerce, it is mandatory to procure authorization from WorldPay to facilitate Recurly's connectivity.

#### WorldPay automatic Account Updater

Recurly extends support to the Account Updater across all gateways. Optionally, you can leverage WorldPay's specialized Automatic Account Updater by enabling it in your gateway settings. This functionality grants Recurly the ability to undertake an additional transaction attempt post a hard decline, enhancing the chances of obtaining any prospective updates available through WorldPay.

<Image align="center" className="border" border={true} src="https://files.readme.io/faa14a7-image.png" />

#### Fraud filtering

Entrust your payment safety to the fraud filtering capabilities orchestrated by WorldPay (previously referred to as Vantiv/Litle). This array of products is designed meticulously to assist in identifying and averting fraud, a feature strongly advocated for WorldPay users by Recurly. To extract more information and activate this service, we encourage you to reach out to your designated WorldPay account manager.

For a comprehensive understanding and an effortless setup process, consult with your WorldPay account manager and employ the additional security layers, guaranteeing a fortified transaction environment. Stay ahead with enhanced security measures brought to you by the collaborative effort of Recurly and WorldPay eCommerce.

### Enable gateway

Setting up your WorldPay eCommerce (formerly Vantiv) with Recurly is a seamless process. Follow the steps outlined below to establish a robust payment solution for your business:

1. **Merchant account setup**
   * If you don't already have a WorldPay eCommerce merchant account, establish one.
2. **Request connection permission**
   * Reach out to WorldPay to request permission for Recurly to access and connect to your WorldPay eCommerce account.
3. **Recurly setup**
   * **Log in** to your Recurly account.
   * **Navigate** to the payment gateways configuration section.
   * **Select** ‘Vantiv’ from the available options and proceed to configure it as your payment gateway.
4. **Gateway settings**
   * **Visit** the gateway settings in your Recurly dashboard.
   * **Select** your accepted card types from the available list under Accepted Credit Card Types.
   * In the Acceptance Currencies section, **use** the dropdown menu in the left section under Available Currencies and add all currencies associated with your Worldpay/Vantiv account(s).
   * In the same Accepted Currencies section, to the right, **enter** your Worldpay / Vantiv Merchant ID associated with each selected currency under Merchant IDs for Selected Currencies’.
   * If your Worldpay Account is set up to accept Zero Dollar Authorizations, **select** which card types are authorized under ‘Zero Dollar Authorizations (Advanced)’.
   * If desired, **enable** WorldPay's Automatic Account Updater. This allows Recurly to make an additional attempt after a hard decline to obtain potential updates from WorldPay.
   * **Click** ‘Add Payment Gateway’ when complete.
5. **Test the integration**
   * Once configured, **perform** test transactions to ensure the integration is functioning correctly.
   * **Review** transactions and monitor for any errors to correct them promptly.
6. **Fraud filtering**
   * **Contact** your WorldPay account manager to discuss the available fraud filtering options and to activate the features best suited for your business needs.
7. **Go live**
   * After confirming that the setup is correctly functioning during tests, you are ready to go live.
   * Continuously monitor the gateway’s performance and make necessary adjustments to optimize the setup.
