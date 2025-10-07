---
title: Supported credit card gateways
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
> 📘 Gateway Specific Updates for PSD2
>
> If you are in-scope of the [PSD2 mandate](https://docs.recurly.com/docs/revised-payment-services-directive-psd2), there may be specific configuration changes required on your gateway account. [Learn more.](https://docs.recurly.com/docs/gateway-specific-updates)

## Gateway Support

The gateways supported by your Recurly site is dependent on your business location. Please see [our gateway page](http://recurly.com/gateways) for the specific gateways supported in your country.

## Accepted Payment Types

[Learn why offering Alternative Payment Methods is important for your subscription businesses.](https://recurly.com/blog/why-offering-alternative-payment-methods-is-important-for-subscription-businesses/)

Recurly supports credit / debit payments from most card types approved by your merchant bank account and payment gateway. However, Maestro cards cannot be used for recurring transactions, so Recurly does not support this card type.

## Level II Card Data Support

By default, all transactions are processed at level I rates. For most of the gateways, Recurly also supports level II card data, which will allow you to qualify for lower interchange rates when processing qualified transactions **as a US merchant**. This involves the inclusion of the following data fields:

* Sales tax amount
* Customer code / PO number
* Merchant zip code

**What you need to do to benefit from level II card data support**: Recurly will include necessary data fields automatically when formatting your transaction requests to the gateways called out above. Given this, you'll simply need to ensure that sales tax is being collected / calculated through Recurly to ensure that your gateway can submit transactions to your processor with the appropriate level 2 data fields. If the transaction qualifies for level 2 rates, this would be addressed while the transaction is processed by the card network.

## Supported Credit Card Gateways

[Adyen](https://docs.recurly.com/docs/adyen)
[Authorize.net](#section-authorize-net)
[AmazonPay](https://docs.recurly.com/recurly-subscriptions/docs/amazon-pay-v2#/)
[Braintree](#section-braintree)
[CardConnect](https://docs.recurly.com/docs/cardconnect)
[CommerceHub by Fiserv](https://docs.recurly.com/recurly-subscriptions/docs/commerce-hub#/)
[Chase Paymentech Orbital](#section-chase-paymentech-orbital)
[CyberSource](#section-cybersource)
[PayPal Complete](https://docs.recurly.com/recurly-subscriptions/docs/paypal-complete#/)
[Stripe](#section-stripe)
[TSYS](#section-tsys)
[Vantiv](#section-world-pay-us-e-commerce-formerly-vantiv)
[Worldpay](#section-worldpay)

## Authorize.net

For pricing and signup information for a new production Authorize.net account, please visit <a href="http://authorize.net/">Authorize.net</a>.

#### Address Verification Service (AVS)

If your company accepts payments from international customers, you need to be aware of some the AVS shortcomings. Currently, AVS fails to match zip codes if the zip code contains letters. US Zip Codes are numeric but many international postal codes will contain letters and will fail to match on the zip code. In order to use AVS with international credit cards, we recommend allowing the transaction to proceed if the street address OR zip code matches.

#### Card Code Verification (CCV)

When a subscription is first created or a credit card number is updated, Recurly will submit the card number and CCV to your payment gateway. PCI regulations do not allow anyone to store CCV values (regardless of encryption), so it can only be used for the first request. Submitting the CCV with the first request increases the likelihood that the transaction will be approved and will reduce fraud. Banks typically allow subsequent transactions to process if previous transactions have been processed by the same merchant without problem.

#### API Login ID and Transaction Key

Recurly needs your API Login ID and Transaction Key in order to communicate with your Authorize.net account. Within your Authorize.net account, navigate to **Account → Settings → API Login ID and Transaction Key**.

Once you have obtained your credentials, please enter them into Recurly's Payment Gateway configuration.

## Bambora

To configure Recurly with a Bambora account, you will need:

* API username, also known as a Merchant ID
* username
* API password

The API username and password are configured under **Administration → Account Settings → Order Settings → Use username/password validation against transaction**. You'll need to check that checkbox and then create a username and password.

**Note:** The API user for Recurly is different than the normal user accounts configured in the Bambora User Manager. This is an important distinction as the API user credentials are required for proper authentication. While regular login details may work for certain transactions, you may have issues in the future unless the appropriate API credentials are used. We recommend taking one of the following steps to appropriately configure these credentials:

1. Read through [Bambora's documentation](https://help.na.bambora.com/hc/en-us/articles/360001524528-Enabling-Username-Password) on setting up the appropriate API authentication values, then update your Bambora configuration in Recurly with these values.
2. Contact Bambora's Customer Experience team for assistance in setting up those API values, then update your Bambora configuration in Recurly appropriately.

#### American Express

Please note: American Express prevents Canadian merchants from accepting USD American Express unless you have an entity located within the United States.

## Braintree

#### Braintree & Multi-currency

Merchants wishing to use Braintree and multi-currency must configure multiple Braintree gateways - one for each currency. Please use your Merchant ID, Merchant Account ID, public key and private key. The Merchant Account ID identifies the currency that is available.

Merchants can find their merchant account IDs by logging into the control panel, clicking "Account→Processing" (in the upper right-hand corner of the page), then scrolling to the bottom of the page. The merchant account IDs available will be found in the 'Merchant Account ID' column in that table.

#### Processing Paypal transactions through Braintree

Recurly now supports PayPal transactions to be processed through Braintree. Please make sure that your Braintree merchant account is configured correctly to accept PayPal transactions.

We recommend that you use Recurly.js v4 to launch the PayPal one-touch checkout flow. See the [Recurly.js PayPal section](https://developers.recurly.com/reference/recurly-js/index.html#paypal) for more details.

Please note that you will notice subtle differences in how the payment method information for the transaction details displayed in Recurly Admin -- primarily because Recurly receives and stores Braintree’s vault token (and not the actual PayPal Billing Agreement). Recurly will use Braintree’s vault token for all subsequent payment transactions.

## Chase Paymentech Orbital

Recurly supports the Chase Paymentech Orbital, Salem Platform. In order for Recurly to connect to your Orbital account, you must configure a few steps on both Chase and Recurly to get the integration working correctly.

1. To start you must be on the Chase Paymentech Orbital, Salem Platform for the integration to work correctly. Chase offers a few different processing platforms, at this time we only support the Salem Platform.

2. Configuring Chase: Recurly is a certified Orbital Submitter; not just a certified integrator of the gateway.  To set up your chase account you would want to reach out to Chase directly and ask them to setup your Chase account to allow connections from Recurly, a Certified Orbital Submitter on the Salem Platform. If Chase asks for our submitter ID that can be found here [https://docs.recurly.com/docs/chase-orbital-gateway-setup](https://docs.recurly.com/docs/chase-orbital-gateway-setup). Generally that is sufficient information for chase to allow connections, in some cases they might ask for specific IP addresses that are used to sent transactions from Recurly to chase, if they require the IP addresses those can be found here [https://docs.recurly.com/docs/ip-allowlist](https://docs.recurly.com/docs/ip-allowlist)

3. You would want to obtain your Merchant Account ID, Username, and Password from Chase so that when you go to add the Chase gateway in your Recurly site you can fill out those fields to correctly connect your Recurly site to your Chase Paymentech gateway.

#### Currencies

The **Tampa** platform only supports US Dollars and Canadian Dollars. Due to this limited currency support, Recurly does not support this platform.

The **Salem** platform supports many more currencies. Please contact Chase for more information.

#### China UnionPay

Recurly supports China UnionPay via Chase Orbital. Please contact Chase Support to have this card brand enabled before enabling China UnionPay as an accepted card type within your Chase Orbital gateway configuration in Recurly.

<Image border={false} src="https://files.readme.io/b9beb8e-cup_enablement.png" title="cup_enablement.png" />

## CyberSource

To configure the CyberSource gateway you'll need your **MerchantID** for the Login, and a Transaction Security Key for the SOAP Toolkit API.

To get a Transaction Security Key, do the following:

1. [Log into your CyberSource business gateway][2]

2. Navigate to **Account Management → Transaction Security Keys → Security Keys for the SOAP Toolkit API**.

3. Click on **Generate Key**.

4. Copy the new key into the password field of your [Payment Gateway configuration][1] in Recurly.

#### Address Verification System (AVS) Settings

Merchants using CyberSource have the option to enable AVS checks for all transactions, only US/Canada transactions, or to disable AVS checks altogether. Recurly recommends enabling AVS for US and Canada only (this setting can be found when configuring/editing a CyberSource gateway).

AVS checks typically work best for the US and Canada, and are sometimes inconsistent or not supported in other countries. CyberSource has the ability to decline transactions based on the AVS result, and the above options allow you to choose whether or not to bypass AVS checks for certain countries.

#### Cybersource Processor

Cybersource requires different integrations based on the processor used for a given Cybersource account. In order for Recurly to set the correct parameters, you'll need to set the main processor for your account in the "CREDIT CARD PROCESSOR" selector.

[2]: https://ebc.cybersource.com/

## First Data Global Gateway e4 (GGe4)

Recurly supports First Data’s GGe4 gateway for US merchants. In order to connect to your First Data account, you will need the following:

* Gateway ID
* Password
* HMAC Key ID
* HMAC

#### User for Results API

We strongly recommend that you create a separate account for Recurly to automatically query the transaction status. This is useful when 1) the GGe4 gateway is unresponsive or 2) there is a network issue after a transaction is submitted. Enter the credentials for the read-only user in the gateway configuration page. First Data [docs](https://support.payeezy.com/hc/en-us/articles/203731249-Real-time-Payment-Manager-RPM-User-Guide#3) on Results API.

## IMPORTANT NOTES:

* **'Results API' credentials expire every 60 days. Be sure to update your credentials prior to the deadline.**
* **Failure to update the 'Results API' credentials will result in requests with an invalid_credentials error. If there are 12 of these bad requests made in 15 minutes, the entire integration may be shut down due to an "IP-Lockout" scenario.**

In order to create a read-only user:

1. Log into the First Data GGe4 Gateway portal at
   [https://globalgatewaye4.firstdata.com/?lang=en](https://globalgatewaye4.firstdata.com/?lang=en).
2. Click on the "Administration" tab on the far right
3. Click "Create New User" link
4. Create a user name
5. Under the "Login" tab, give the user the "read only" role
   First Data's documentation on how to create an account [here](https://support.payeezy.com/hc/en-us/articles/203731249-Real-time-Payment-Manager-RPM-User-Guide#3).

After the user is created, please click the user and then visit the "Merchant / Terminal Restrictions" tab to verify the user has access to the terminals that Recurly uses to create transactions on your behalf.

#### AVS Settings

When adding a new credit card in Recurly, a transaction is created and the provided billing address is submitted to the payment gateway alongside other transaction information. An AVS (Address Validation System) response is then returned to Recurly. AVS checks generally work for US and Canada addresses, but can be inconsistent or unsupported for other countries. This can lead to transactions from customers outside the US/Canada being rejected due to their billing address.

The First Data GGe4 gateway gives you the option to require a partial match on AVS responses for transactions (recommended), or to ignore the AVS response altogether (in which case transactions will not be rejected due to any AVS issues). If the **partial match** option is enabled, transactions with an AVS response of "N" (_No Match_) will be rejected. All other AVS responses will be allowed.

> 📘 Credentials
>
> To enable your Vantiv gateway, you will need to enter the MID for your Vantiv gateway on the credentials page within Recurly.

**Please note:** AVS responses are only validated on initial transactions (ie; when a credit card is first added in Recurly). AVS responses for recurring transactions will be ignored.

## WorldPay US eCommerce (formerly Vantiv)

Recurly supports WorldPay US eCommerce (Vantiv - Litle platform) for US merchants. Before Recurly can connect to your WorldPay US eCommerce account, you must first ask WorldPay to allow Recurly to connect.

#### WorldPay Automatic Account Updater

Recurly supports Account Updater regardless of your gateway. If you additionally choose to enable WorldPay's (formerly Vantiv) Automatic Account Updater, please indicate it in your gateway settings. This enables Recurly to submit one additional attempt after a hard decline in order to pick up any potential updates from WorldPay.

<Image border={false} src="https://files.readme.io/faa14a7-image.png" title="image.png" />

#### Fraud Filtering

WorldPay (formerly Vantiv) provides a suite of products that assist in the discovery of fraud. Recurly highly recommends that merchants using WorldPay enable this feature. Please contact your WorldPay account manager for more information.

## Merchant eSolutions

Recurly supports Merchant eSolutions (MeS) for US merchants. In order to connect to your Merchant eSolutions account, you will need to know your `Profile` and `Profile Key` from MeS.

#### Address Verification Service (AVS)

Merchant eSolutions runs AVS on recurring transactions. This allows their merchants to get the lowest interchange rate on card-not-present transactions.

## Payeezy

Recurly supports First Data’s Payeezy gateway. In order to connect to your Payeezy account, you will need the following:

* API Key
* API Secret
* Merchant Token

After you setup your Payeezy credentials, Recurly will verify your credentials.

<Image border={false} src="https://files.readme.io/c79e595-payeezy-api-credentials.png" title="payeezy-api-credentials.png" />

<Image border={false} src="https://files.readme.io/fec7532-payeezy-credentials2.png" title="payeezy-credentials2.png" />

#### CVV Settings

CVV is a basic yet effective way to block fraudulent transactions. Recurly can easily distinguish between a subscription signup and a renewal transaction. Please disable CVV checks in Payeezy and enable them in Recurly.

## PayPal Payflow Pro

PayPal Payflow Pro is a payment gateway only product. Recurly supports Payflow Pro in the US, UK, Canada, and Australia for credit card payments.

Enter the details that you use to access [https://manager.paypal.com/](https://manager.paypal.com/) as follows:

* Vendor: The MERCHANT LOGIN you use to access [https://manager.paypal.com/](https://manager.paypal.com/)
* Password: The PASSWORD you use to access [https://manager.paypal.com/](https://manager.paypal.com/)
* User: The MERCHANT LOGIN you use to access [https://manager.paypal.com/](https://manager.paypal.com/)
* Partner: Optional (PayPal may supply you with this)

Please note, these are _not_ the details from your standard PayPal account (your email) or your API credentials.

## PayPal Payments Pro

Recurly can use PayPal's [Payments Pro][3] to process credit cards. WebSite Payments Pro acts as a payment gateway for credit card processing and merchant account in one.

[3]: https://merchant.paypal.com/cgi-bin/marketingweb?cmd=_render-content&content_ID=merchant/wp_pro

To get started with PayPal's Payments Pro, you only need to sign up for their base account. You do not need their Recurring Payments feature---that's completely handled by Recurly.

_Payments Pro only works for merchants located in the US, Canada, and UK. Due to PayPal restrictions, we cannot integrate with PayPal Website Payments Pro in any other country._

#### Card Security Code (CSC)

Some PayPal accounts are required to present the Card Security Code (CSC) for every transaction. After you setup your PayPal credentials, Recurly will verify your credentials. If Recurly determines your account requires CSC for every transaction, you will need to contact PayPal to disable this requirement before your account can be used with Recurly.

_Important Note:_ By default, Recurly requires the CSC (also known as CVV) to start a new subscription or transaction. Due to PCI requirements, Recurly cannot store the CSC. Therefore, Recurly submits recurring transactions without the CSC, and your PayPal account must be configured to not require this value.

#### Configuring Recurly to use PayPal

Recurly requires the PayPal API Username, API Password, and Signature (preferred) or PEM Certificate to connect to your PayPal [Payments Pro][3] account. To retrieve your Signature from PayPal, follow these steps:

1. Log in to your PayPal account at [paypal.com][5]

2. On the **My Account** tab, click on the **Profile** sub-tab.

3. Click on **API access** or **Request API credentials**, depending on your PayPal account type.

4. PayPal will present two options: granting API permissions (Option 1) and requesting API credentials (Option 2). Select option 2. It may say **View API Signature** or **View API Credentials**.

5. If you have already requested an API Signature, you will now see your API credentials. Otherwise,

6. The final page will display your API username, password and signature. All three pieces are required to connect Recurly to your PayPal Website Payments Pro account.

[5]: https://www.paypal.com/

#### PEM versus Signature

Recurly supports connecting to your PayPal account using the PEM or signature for credit card transactions. If in the future you wish to support payments via PayPal (in addition to credit cards), you must use the signature API credentials. If you have created a PEM certificate, you will need to delete the PEM certificate and walk through the process of choosing the signature credentials.

#### Canada and American Express

Please note, PayPal Website Payments Pro in Canada does not support American Express.

#### Address Requirements

PayPal Payments Pro requires full address information to be submitted for every transaction. If you are using PayPal WPP, please set Recurly to require the full billing address (name, phone, street address, city, state/province, postal/zip, and country).

## Stripe

To integrate with Stripe, please access the <a href="https://app.recurly.com/go/configuration/payment_gateways/new">Recurly Payment Gateway Configuration</a> page. You may either log in with your existing Stripe account, or apply for a new Stripe account.

Recurly's Stripe integration will not update Stripe customers as accounts update their billing information. Should you choose to process any payments directly inside of Stripe, please search for the most recently created Stripe customer.

If you use Stripe and [Gateway Failover](https://docs.recurly.com/docs/gateway-failover), you must make sure the two gateways match the same currency and card type support.

## TSYS

The TSYS Gateway can connect to over 400 merchant account banks in the United States

Please ask your merchant bank to create a TSYS Merchant Profile using Host Capture (Summit platform) for Recurly, version 1.0. Once the profile is created, please send the merchant profile along with your POS ID, Authentication Code, and zip code to [support@recurly.com](mailto:support@recurly.com).

**Getting started**
To get started, Recurly needs to know how to connect to your merchant account. If you have a merchant account, see the instructions for connecting to an existing merchant account. Otherwise, start with creating a new merchant account.

**Database Name**

TSYS requires a database name of at least 5 characters. This can be set in the site settings page of Recurly. If no database name is entered, it will default to the site name. Please ensure at least 5 characters or all transactions will fail.

**New Merchant Accounts**
If you need a merchant account, we can help you get started. Create a Recurly account, or log into your existing account, and the payment gateway setup process will walk you through the application for a new merchant account.

**Existing Merchant Accounts**
If you have an existing merchant account, please ask your merchant bank to create a TSYS Merchant Profile using Host Capture (Summit platform).

Your merchant bank account provider will need to contact Recurly with your Authentication code, POS ID, merchant zip code, and approved payment methods. POS ID should be 15 numbers and Authentication code is 6-10 letters/numbers. Once this data is received, you can expect to have the Recurly gateway configured on your site in one business day.

**Important Note:** If you ever change address or phone number, make sure to contact your merchant account provider ahead of time to check if you need an updated merchant profile. Changing your address sometimes requires updated merchant account credentials, and if you don't update your TSYS gateway configuration with those credentials you may experience downtime until a new VAR sheet is generated.

#### Advanced

**Multi Currency**
Today, the TSYS integration is only available for US merchants and for US Dollars. You may combine with other gateways to accept additional currencies.
**Merchant Geography**
TSYS can process credit cards from customers around the world. However, it is only available today for merchants with a US based presence.
**Address Requirements**
TSYS has no minimum address requirements.
**CVV Requirements**
Because TSYS is designed to handle recurring billing, there is no Card Security Code configuration needed.

[1]: https://app.recurly.com/go/configuration/payment_gateways

[4]: http://recurly.com/gateways/

## WorldPay

#### Configuring WorldPay WPG for international processing

1. Contact WorldPay to configure your merchant account.
2. Login to the WorldPay portal and allow Recurly's IP addresses. See our [IP Allowlist documentation](https://docs.recurly.com/docs/ip-allowlist) for the full list of IPs to supply.
3. While logged into WorldPay, set the Capture delay to **1-Day**.
   a. Configure callbacks with the urls [https://callbacks.recurly.com/worldpay](https://callbacks.recurly.com/worldpay), and select which notifications you'd like to receive. If your data is hosted in our European Union (EU) data centers you must use this url instead: [https://callbacks.eu.recurly.com/worldpay](https://callbacks.eu.recurly.com/worldpay)
4. We also recommend that you configure WorldPay notifications to be sent to Recurly. This will help keep Recurly's transaction status in sync with WorldPay's status.

#### Configuration in Recurly

1. Go to the “Payment Gateways” page in your Recurly app. Click on “Add Payment Gateway” and then choose the WorldPay gateway.
2. Enter your WorldPay _MerchantCode_, **XML** _UserName_ and **XML** _Password_ credentials. Please keep in mind that the UserName and Password details will not be the ones you use to log into your WorldPay merchant account.
3. Choose the currencies and card types you want to support.
4. If necessary, select the card types you'd like to apply Zero Dollar Authorizations to.
5. Click "Save".
6. Once the gateway configuration is saved, you can verify the settings by clicking the “Test Configuration” option associated with the gateway.

> 📘 Credentials
>
> Worldpay Payment Gateway (WPG) requires you to enter XML credentials obtained from Worldpay.

**Voids and Refunds**
Void (also known as 'cancel') and Refund order modifications are processed asynchronously by WorldPay. There is a remote chance that WorldPay may reject a Void or Refund request 5 to 45 minutes after receiving receiving it.

**Billing Address**
At Recurly, we want to submit as much information (including the billing address) to WorldPay as possible. WorldPay, however, requires four mandatory fields - _Address line1, City, Postal code_ and _Country_. If not provided, Recurly may use default values for these fields.

For example: If a customer has only provided a postal code we will submit the provided Postal code, use the country from their IP address, and default the City to “city” and Address line1 to “address”. If we don't have the Country (or can’t derive the country from the IP address) a billing address will not be submitted for the transaction.
