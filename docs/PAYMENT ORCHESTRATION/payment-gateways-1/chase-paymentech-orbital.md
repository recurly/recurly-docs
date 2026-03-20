---
title: Chase Paymentech Orbital
excerpt: >-
  Effortlessly integrate Recurly with Chase Paymentech Orbital, Salem Platform
  to optimize your payment processing capabilities.
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

### Limitations

* Only supported via the Stratus/Salem platform. Tampa merchant accounts are not supported.
* Recurly does not support lifecycle webhooks or post-auth webhooks from the Gateway. If you are using gateway-level fraud review systems, or are making transaction actions at the gateway, there is risk that Recurly and the gateway could be out of sync. It is advised to keep an eye on gateway-level fraud services, and ensure you are capturing, voiding, and processing refunds from Recurly instead of at the gateway.
* Chase returns certain response codes that mean two-separate things, though the code is mapped to one code in our system. The list is below: 
  * C5 / Over Frequency Limit -- this can mean two different things, but looking at the gateway message is important. It may mean Over Frequency Limit unless the card brand is MasterCard, in which case it may mean that 3DS / SCA is required.

# Definition

Recurly provides seamless support for the Chase Paymentech Orbital, specifically for the Salem Platform. This integration allows merchants to effortlessly connect their Recurly account with Chase Paymentech Orbital to facilitate secure and efficient payment processing.

# Key details

| Field Name                      | Description                                                                                                                                                                                                                                                                                                                                                                                                              |
| ------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Services that work with Recurly | Processing, Recurring Billing, [MOTO](https://docs.recurly.com/recurly-subscriptions/docs/moto-transactions#/)  Processing                                                                                                                                                                                                                                                                                               |
| Supported Operations            | Authorize & Capture, Purchase, Recurring, Refund, Verify, Void                                                                                                                                                                                                                                                                                                                                                           |
| Supported Payment Types         | Credit Cards                                                                                                                                                                                                                                                                                                                                                                                                             |
| Supported Card Brands           | Visa, MasterCard, American Express, Discover, China UnionPay, Apple Pay, Google Pay                                                                                                                                                                                                                                                                                                                                      |
| Gateway Specific 3DS2 Supported | Yes                                                                                                                                                                                                                                                                                                                                                                                                                      |
| Card on File Supported          | Yes                                                                                                                                                                                                                                                                                                                                                                                                                      |
| Regions                         | US, Canada, Australia, Germany, France, UK, Italy                                                                                                                                                                                                                                                                                                                                                                        |
| Currencies                      | USD, ARS, AUD, BRL, CAD, CHF, CLP, CNY, COP, CZK, DKK, EUR, YER, XOF, XCD, UAH, TZS, TTD, SCR, RSD, QAR, MUR, MOP, MNT, MKD, MAD, LRD, LBP, LAK, KZT, KES, JMD, EGP, DZD, DOP, BZD, BWP, BSD, BND, BMD, BAM, AZN, ALL, AFN, BDT, BBD, AED, LKR, SAR, RON, PKR, NGN, HNL, BGN, IDR, UYU, PYG, PAB, GTQ, CRC, BOB, MYR, PEN, TRY, GBP, HKD, HRK, HUF, ILS, INR, JPY, KRW, MXN, NOK, NZD, PLN, RUB, SEK, SGD, ZAR, TWD, PHP |

To integrate Recurly with Chase Paymentech Orbital, Salem Platform, it is essential to modify a few configurations in both Chase and Recurly. This ensures the integration functions optimally.

### Initial requirements

1. **Platform selection**
   * To begin, you must operate on the Chase Paymentech Orbital using the Salem (sometimes referred to as ‘Stratus’) Platform. Chase offers various processing platforms, but at this time, Recurly only supports integration with the Salem Platform through the Orbital Gateway front end. A direct Salem processing MID will not suffice. Merchant accounts through the Tampa platform are not supported.
2. **Configuring chase**
   * Recurly is a certified Orbital Submitter, signifying a trusted integration level beyond just a gateway connector. To initiate setup, contact Chase directly and request configuration of your account to permit connections from Recurly, a Certified Orbital Submitter on the Salem Platform. If Chase requests the Recurly's submitter ID, it can be accessed [here](https://docs.recurly.com/docs/chase-orbital-gateway-setup). Typically, this information suffices, but if Chase requires specific IP addresses used by Recurly for transaction routing, they can be obtained [here](https://docs.recurly.com/docs/ip-allowlist).
3. **Connection details**
   * Acquire your Merchant Account ID, Username, and Password from Chase. These credentials are necessary to accurately link your Recurly site to your Chase Paymentech gateway.

### Supported currencies

* **Salem platform**: The Salem platform accommodates a wider range of currencies. For detailed information, it is advisable to directly contact Chase.

### China UnionPay integration

Recurly extends support for **China UnionPay** through the Chase Orbital gateway. To activate this feature, you must have China Unionpay enabled on your Chase Orbital instance. Once it is an accepted card brand on your Chase Orbital instance, you can configure China UnionPay as an accepted card type within your Chase Orbital gateway settings in Recurly.

# Integrating Chase Paymentech Orbital with Recurly

### Step 1: Confirm your chase platform

* Ensure that you are operating on the **Chase Paymentech Orbital, Salem Platform**. Chase offers various processing platforms, but Recurly currently supports integration only with the Salem Platform.

### Step 2: Configure Chase

* Contact **Chase Paymentech Support** and request to set up your Chase account to permit connections from Recurly, a Certified Orbital Submitter on the Salem Platform.
* If Chase asks for Recurly’s submitter ID, provide the ID found [here](https://docs.recurly.com/docs/chase-orbital-gateway-setup).
* If Chase requires specific IP addresses used by Recurly for transaction routing, provide the IPs found [here](https://docs.recurly.com/docs/ip-allowlist).

### Step 3: Obtain Chase credentials

* Request your **Merchant Account ID**, **Username**, and **Password** from Chase. These will be necessary to link Recurly to your Chase Paymentech gateway.

### Step 4: Add Chase gateway in Recurly

* Log in to your **Recurly Admin Console**.

* Navigate to **Configuration→Payment Gateways**.

* Click **Add Gateway** and select the icon for **Chase**.

<Image align="center" border={true} src="https://files.readme.io/bc89bf8-image.png" className="border" />

* In the 'Credentials' section, enter your **Username**, and **Password** obtained from Chase in Step 3. You may optionally also provide:
  * JPMPP Merchant ID
  * JPMPP Username
  * JPMPP Password

### Step 5: Enable accepted credit card types and currencies

* Within the Chase Paymentech Orbital gateway configuration in Recurly, enable the specific **currencies** and **card brands** you would like to support. If you would like to support Google Pay, it can be selected under Alternative Payment Methods.
* For each additional currency provided, you must enter your Merchant ID associated with that currency. You can enter your Merchant ID under the header ‘Merchant IDs for Selected Currencies’ in the Accepted Currencies section.

<Image align="center" border={true} width="50% " src="https://files.readme.io/280b6d8-image.png" className="border" />

### Step 6: Mark gateway as enabled

* Ensure that you mark the gateway as '**Enabled for New Transactions**'. This setting activates the gateway, allowing you to start processing transactions via your Chase Paymentech Orbital gateway.

### Step 7: Configure China UnionPay (if necessary)

* If you wish to accept China UnionPay, contact **Chase Support** to enable this card brand at the gateway level. After this step, you may enable China UnionPay as an accepted card type within your Chase Orbital gateway settings in Recurly.

### Step 8: Configure zero dollar authorizations (advanced)

* It is recommended to enable Zero Dollar Authorizations where possible, though you will need to work with Chase directly to ensure your Merchant account is set up to do so. Do not enable Zero Dollar Authorizations if your gateway cannot support it.
* Once set up properly with **Chase Support**, you may enable ZDA support in your Recurly settings for each supported card type.

### Step 9: MOTO transaction type settings

* Do not enable this if your business runs recurring and ecommerce transactions where the customer is directly present in your checkout flow. This setting should only be used on sites or gateway instances that are used in a back office environment where an employee at your location is submitting transactions on behalf of your customer.

### Step 10: Partial AVS validations

* On one-time transactions and subscription sign ups, Customers should enter their full and correct Billing Address. However, sometimes customers make mistakes and in other scenarios, the transaction may be fraudulent. In these cases, to fully protect your business against potential fraud, Recurly has introduced a setting to enable automatically rejecting (voiding) transactions where the Address Verification code received from Chase is not a **full** match.
* Enabling this setting will only take effect if you have also enabled the Address Verification Check in Payment Settings. Address Verification Check by itself will also protect you but will only reject (void) transactions if the AVS code indicated a full mismatch (both Address and Zip Code did not match).
* Transactions rejected by AVS Checks will appear as declines in reporting.

**Note**: This feature is not fully rolled out. To gain access, please contact Customer Support.

### Step 11: Review and save

* Review all the settings to ensure they are correct, then click the **Save Changes** button.

### Step 12: Test the integration

* After saving, conduct a series of test transactions to confirm the integration is working as expected.

### Step 13: Monitor transactions

* Once live, routinely check Recurly and Chase Paymentech Orbital dashboards to ensure transactions are processing smoothly.
