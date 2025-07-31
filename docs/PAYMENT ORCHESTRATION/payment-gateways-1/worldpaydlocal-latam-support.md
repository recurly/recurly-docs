---
title: Worldpay - Global e-commerce
excerpt: >-
  Unlock the potential of the Global e-commerce landscape by integrating Recurly
  with WorldPay and Ebanx/dLocal. This powerful collaboration simplifies
  navigation through the region's complex payment ecosystem, offering robust
  support for local currencies and preferred card brands, facilitating seamless
  expansion.
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

* Established commercial agreements with WorldPay and Ebanx to facilitate local transactions.
  * WorldPay also supports dLocal but is not provisioning new accounts for that relationship. For merchants that do not already have a dLocal account, connect with Worldpay on an Ebanx solution.
* For **Argentinian** processing:
  * An active Recurly account with Argentine Peso (ARS) currency support
  * WorldPay payment gateway configured for ARS transactions.
  * A WorldPay merchant account optimized for handling ARS and capable of performing Zero Dollar Authorizations (ZDA).
* For **SEPA** processing:
  * An active Recurly account with Euros (EUR) currency support
  * WorldPay payment gateway configured for SEPA / EUR and mandate tokenization support.

### Limitations

* The Tarjeta Naranja card brand does not support ZDA; verifications for this card are processed with a one-dollar charge.
* Transactions require the submission of a CUIT (tax ID) with each transaction in Argentina.
* If you are using CUIT, CPF, or CNPJ tax types, you must specify the type via API, else send the tax ID without a`tax_identifier_type`.
* Certain regions require Sales Tax be applied to the transaction. Check with Worldpay for details and ensure you have Sales Tax configured in your Recurly Site. See our [sales tax documentation](https://docs.recurly.com/docs/tax#/) for instructions.
* WorldPay SEPA does not support free-trial subscriptions or verification transactions.
* WorldPay SEPA billing info updates must occur within the process of processing a transaction.
* Check if your business is on Worldpay's list of [Prohibited Business types](http://support.worldpay.com/support/kb/gg/billdesk/content/prohibitedmerchantcategories.htm).

> 🚧 Warning
>
> If you have a Vantiv/Litle Merchant ID, use [these directions](https://docs.recurly.com/docs/vantiv) instead.

> 📘 Online refunds
>
> WorldPay will be enabling Online Refunds for merchants in mid-late April to comply with Online refund compliance. Since refunds can now be 'authorized', banks can now decline refund attempts. You may see declined refunds, which will need to be resubmitted, or resolved outside of Recurly directly with your consumer if their bank will not accept the refund attempt.
>
> You may wish to check your Refund Invoice settings to avoid unintended behavior related to declined refunds. Read more about how Recurly handles failed refunds by default in our [dedicated documentation](https://docs.recurly.com/docs/credit-invoices#/4-handling-failed-refunds).

# Definition

Expand your business globally and in the dynamic global e-commerce sector with Recurly's integration with WorldPay. WorldPay x Recurly support Global payments processing including specialization in LATAM via Ebanx/dLocal. This solution offers a seamless way to navigate complex payment ecosystems, supporting local currencies, card brands, and distinct regional payment preferences.

WorldPay facilitates international transactions with configurable merchant accounts, while WorldPay, via partnerships with Ebanx/dLocal, caters specifically to global markets, optimizing payment processes by accommodating local currencies like the Argentine Peso (ARS) and the widely recognized card brand, Tarjeta Naranja.

Additionally, WorldPay x Recurly now support SEPA processing for direct debit subscriptions and transaction processing.

For a global reach, WorldPay allows merchants to configure their accounts for international processing, including IP allowlisting, capture delay settings, and callback configurations for seamless transaction synchronization. Recurly's integration ensures merchants can support a broad range of currencies and card types, including the application of Zero Dollar Authorizations if needed. With WorldPay's asynchronous processing for voids and refunds, and Recurly's commitment to submitting comprehensive transaction information, businesses are equipped to offer a robust and adaptable payment processing experience worldwide and specifically in the global market.

Supported Regions:

> **Note**: Visit our [guide on testing your gateway configurations ](https://docs.recurly.com/docs/how-to-test-your-gateway)in Recurly to ensure your payment processes are set up correctly.

# Key details

<Table>
  <thead>
    <tr>
      <th>
        Feature
      </th>

      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Services that work with Recurly
      </td>

      <td>
        WorldPay, Ebanx, dlocal (existing merchants only)
      </td>
    </tr>

    <tr>
      <td>
        Supported operations
      </td>

      <td>
        Transactions, Voids, Refunds (Online and Offline)
      </td>
    </tr>

    <tr>
      <td>
        Supported payment types
      </td>

      <td>
        Credit cards, local card brands including Tarjeta Naranja, Apple Pay and Google Pay, SEPA
      </td>
    </tr>

    <tr>
      <td>
        Supported card brands
      </td>

      <td>
        Visa, MasterCard, Discover, UnionPay, JCB, Diner's Club, American Express for most currencies. Tarjeta Naranja supported on ARS currency only.
      </td>
    </tr>

    <tr>
      <td>
        Gateway Specific 3DS2 Supported
      </td>

      <td>
        Yes, Depends on WorldPay configuration. Requires usage of Recurly.js in certain cases.
      </td>
    </tr>

    <tr>
      <td>
        Card on File Support
      </td>

      <td>
        Yes
      </td>
    </tr>

    <tr>
      <td>
        Regions
      </td>

      <td>
        Global with a focus on global, including the UK/EU, Argentina, Brazil, Chile, Colombia, Costa Rica, El Salvador, Guatemala, Mexico, Ecuador, Panama, Paraguay, Uruguay, Honduras, and Peru.
      </td>
    </tr>

    <tr>
      <td>
        Currencies
      </td>

      <td>
        * *ARS*\* (Visa, MC, Amex, Discover, JCB, Diner's Club, *Tarjeta Naranja*)
        * *Else*\*: USD, ANG, AUD, BRL, CAD, CHF, CLP, CNY, COP, CZK, DKK, EUR, KES, BDT, BBD, AOA, AED, VND, LKR, SAR, RON, PKR, NGN, HNL, BGN, IDR, UYU, PYG, PAB, GTQ, CRC, BOB, MYR, PEN, TRY, GBP, HKD, HRK, HUF, ILS, INR, ISK, JPY, KRW, MXN, NOK, NZD, PLN, RUB, SEK, SGD, THB, VEF, ZAR, TWD, PHP
        * *EUR*\* for SEPA processing.
      </td>
    </tr>
  </tbody>
</Table>

# Credentials

Worldpay Payment Gateway (WPG) requires you to enter XML credentials obtained from Worldpay. For SEPA, you will also need to provide additional information for SEPA mandate creation.

**Billing address**

At Recurly, we want to submit as much information (including the billing address) to WorldPay as possible. WorldPay, however, requires four mandatory fields - *Address line1, City, Postal code* and *Country*. If not provided, Recurly may use default values for these fields.

**Voids and refunds**

Void (also known as 'cancel') and Refund order modifications are processed asynchronously by WorldPay. There is a remote chance that WorldPay may reject a Void or Refund request 5 to 45 minutes after receiving it.

**For example:** If a customer has only provided a postal code we will submit the provided Postal code, use the country from their IP address, and default the City to “city” and Address line1 to “address”. If we don't have the Country (or can’t derive the country from the IP address) a billing address will not be submitted for the transaction.

# Navigating the Global  ecommerce landscape

Recurly has forged collaborations with WorldPay, Ebanx, and dLocal (no new dLocal accounts provisioned by Worldpay), endeavoring to offer merchants unparalleled support in global, a region harboring a booming ecommerce market amidst a complex payment ecosystem.

Find additional guidance in the [technical documentation](https://developers.recurly.com/), where the billing information block references the related tax ID documentation, such as CUIT. This vigilant approach ensures a smooth, compliant transaction process, embracing the specific needs of the global market.

# Configuring WorldPay WPG for international processing

1. Initiate the setup by contacting WorldPay to adjust your merchant account for international transactions.
2. Access the WorldPay portal to authorize Recurly's IP addresses. Refer to our [IP Allowlist documentation](https://docs.recurly.com/docs/ip-allowlist) for a comprehensive list of IPs to include.
3. While in the WorldPay platform, adjust the Capture delay setting to **1-Day**.\
   a. Implement callback configurations using the URLs [https://callbacks.recurly.com/worldpay](https://callbacks.recurly.com/worldpay) for notifications you wish to receive. For those with data in European Union (EU) data centers, utilize [https://callbacks.eu.recurly.com/worldpay](https://callbacks.eu.recurly.com/worldpay) instead.
4. It's advisable to set up WorldPay to forward notifications to Recurly, ensuring alignment between Recurly's transaction records and WorldPay's.

### Configuration in Recurly

1. Navigate to the “Payment Gateways” section within your Recurly application. Select “Add Payment Gateway” and choose WorldPay as your gateway.
2. Input your WorldPay *Merchant Code*, **XML** *Username*, and **XML** *Password*. Note: The Username and Password for this setup differ from your WorldPay account login credentials.
3. If you are accepting SEPA payments, input your WorldPay Mandate Prefix and Merchant ID. Ensure EUR is enabled.
4. If you are utilizing 3D Secure, input your Issuer ID, Unit ID, HMAC Key, and Challenge URL.
5. Specify the currencies and card types you plan to accept.
6. Optional: Designate which card types should undergo Zero Dollar Authorizations.
7. Finalize your setup by clicking "Add Payment Gateway".
8. Validate your configuration by selecting the “Test Configuration” feature for the gateway to ensure proper setup.

# Enable gateway for global support

Leveraging the WorldPay global gateway for your business involves a streamlined process. Follow the detailed steps below to enable this gateway seamlessly:

1. **Enable global currencies on your Recurly site**
   * Log in to your Recurly account.
   * Navigate to the currency settings and enable Argentine Peso (ARS) as a supported currency if you are processing in Argentina and wish to accept the Tarjeta Naranja card. Otherwise, add applicable global currencies to your account.
2. **Configure WorldPay as your payment Gateway**
   * Still in your Recurly dashboard, go to payment gateways.
   * Select and configure WorldPay as your payment gateway, ensuring it's set up to accept your supported currencies.
3. **Enable Tarjeta Naranja if applicable**
   * Within your WorldPay gateway settings in Recurly, find and toggle on the option to accept payments through Tarjeta Naranja.
4. **Enable SEPA if applicable**
   1. Ensure you are adding your **Worldpay Mandate Prefix** and **Worldpay Merchant ID** as provided by WorldPay. These two fields are necessary for making sure your SEPA mandates are generated properly.
   2. Ensure you have EUR currency enabled on your site, at WorldPay, and in the gateway configuration.
5. **Establish commercial relationships**
   * Set up commercial relationships with both WorldPay and either Ebanx or dLocal. If necessary, contact [partnerships@recurly.com](mailto:partnerships@recurly.com) for introductions.

### Settings on the Gateway Side

Setting up your WorldPay account correctly is crucial in ensuring smooth transactions. Here’s how you can go about it:

1. **Initiate WorldPay integration**
   * Reach out to the WorldPay integration team to kickstart the setup process for your WorldPay account.
2. **Enable local currencies and zero dollar authorizations**
   * Ensure that your WorldPay account is configured to support local currencies, including enabling zero-dollar authorizations (ZDA).
   * Understand the specifics about ZDA, especially in relation to Tarjeta Naranja, which does not support ZDA and processes verifications with a one-dollar charge.
3. **Integration with Ebanx or dLocal**
   * Establish a functioning relationship with Ebanx or dLocal, integrating them appropriately with your WorldPay account. You do not need to integrate *directly* to Ebanx or dLocal.
4. **Setting up transaction details**
   * Be prepared to collect tax ID information, such as the CUIT (tax ID) from your global customers during the initial transactions. If you are not using one of CUIT, CPF, or CNPJ, you can send the Tax ID field without a type definition.
   * Configure your system to include fields for the tax identifier and its type during the payment process, aligning it to send this information correctly with each transaction to comply with the Argentine regulations.
5. **Testing**

* Before going live, rigorously test the setup to ensure all elements work harmoniously and comply with the regional requirements.

By carefully following this step-by-step process, you will have the WorldPay global gateway up and running, ready to facilitate transactions in the global market efficiently. Ensure to refer to the [technical documentation](https://developers.recurly.com/) for any technical assistance during the setup.

### FAQs

**Q: Why is my WorldPay refund failing?**

**A**: Refunds can fail due to Online Refund Authorization behavior that WorldPay supports. In May 2025, this will become standard across all WorldPay accounts. Banks will 'authorize' refunds in realtime, which can cause errors if the account is closed, or the bank does not wish to authorize the refund for some reason. If this happens, you must coordinate with your customer to return funds in another manner.