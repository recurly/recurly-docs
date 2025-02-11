---
title: Amazon Pay
excerpt: >-
  Elevate your Recurly site with Amazon Pay – an easy and trusted way for Amazon
  customers to subscribe to your plans, using information already stored in
  their Amazon accounts. Now available in the US, Europe, and the UK!
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

### Prerequisites & supported gateways

* Sign up for an [Amazon Pay account](https://payments.amazon.com/register?registration_source=SPPD\&spId=A35095BGBGQR66).
* Set up an Amazon application to authenticate users on your site.
* Enable Amazon Pay on your Recurly site.

### Limitations

* Doesn't support 3DS or PSD2 currently.
* Amazon Pay is available only in specific regions including the US, Europe, and the UK.

# Key details

| Feature                         | Description                                                     |
| ------------------------------- | --------------------------------------------------------------- |
| Services that work with Recurly | Amazon                                                          |
| Supported operations            | Authorize & Capture, Purchase, Refund, Verify, Void             |
| Supported payment types         | Amazon                                                          |
| Supported card brands           | Visa, MasterCard                                                |
| Gateway Specific 3DS2 Supported | Yes                                                             |
| Card on File Supported          | Yes                                                             |
| Regions                         | US, EU, and the UK                                              |
| Currencies                      | AUD, GBP, DKK, EUR, HKD, JPY, NZD, NOK, ZAR, SEK, CHF, and USD. |

# Description

Recurly facilitates a variety of transaction methods for your customers, leveraging the reliability and efficiency of Amazon Pay. By integrating Amazon Pay, you enable countless Amazon customers to easily subscribe to your plans using the information already stored in their Amazon account, without navigating away from your site. Setting up this feature on your Recurly site is a straightforward process.

Recurly has extended support for Amazon Pay to include Europe and the United Kingdom. You can find more details [here](https://docs.recurly.com/docs/amazon-payments#section-amazon-pay-support-in-europe-and-the-united-kingdom-).

Please note that, as of now, the Amazon Pay integration with Recurly does not support 3DS or PSD2, but support is coming.

![650](https://files.readme.io/bpZ0MwSZTmdQROvA5ikl_amzn-mocks.png "amzn-mocks.png")

# Use cases

* Facilitating easy subscriptions for Amazon customers without leaving your site.
* Allowing subscribers to manage their subscription, including payment and billing details through Amazon Pay integration.

## Integration

After configuring your Recurly site and establishing your Amazon Pay accounts, you can proceed to integrate the Amazon Pay library into your subscription checkout process.

<Image align="center" src="https://files.readme.io/3lOrtM3jSyypS3EE8Kxw_amzn-overview.png" />

Recurly offers a complimentary [JavaScript plug-in library](https://github.com/recurly/pay-with-amazon) to seamlessly incorporate Amazon Pay into your system. The library facilitates inline widget interactions which can be customized according to simple parameters. The only part of the process requiring navigation away from your site is the initial Amazon login. After login, customers are redirected to your site to confirm their address and payment details using the Amazon widgets.

![600](https://files.readme.io/Ant1pFYMSMizM7oZvKUR_amzn-widgets.png "amzn-widgets.png")

Include the following JavaScript in your document's `<head>` section:

```
<script src="pay-with-amazon.min.js"></script>
```

Still in the `<head>` section, call `PayWithAmazon` with your configuration details:

```
var payWithAmazon = new PayWithAmazon({
    sellerId: 'ABC',
    clientId: 'XYZ',
    button: { id: 'pay-with-amazon', [type], [color] },
    addressBook: { id: 'address-book', [width], [height] },
    wallet: { id: 'wallet', [width], [height] },
    consent: { id: 'consent', [width], [height] },
    region: 'eu' // Options are 'eu' or 'uk'
});
```

* It is essential to specify the region if not located in the US. EU or UK regions must specify this in each transaction request.

Upon customer confirmation of the Amazon payment details for the subscription, the Amazon Billing Agreement ID (`id`) will be generated. This ID can be utilized with Recurly's [create subscription API](https://docs.recurly.com/api/subscriptions#create-subscription) to establish the account's billing information.

While not obligatory, using [Recurly.js](https://js.recurly.com/) can enhance the integration of Amazon Pay with your Recurly account, providing features like accessing your plan and add-on details, and previewing a purchase with a pricing module. **Employing Amazon Pay along with Recurly.js v4 is advisable.** 

```
<?xml version="1.0" encoding="UTF-8"?>
<subscription>
    <plan_code>gold</plan_code>
    <currency>USD</currency>
    <account>
        <account_code>customer</account_code>
        <billing_info>
            <amazon_billing_agreement_id>abc-xyz</amazon_billing_agreement_id>
            <first_name>John</first_name>
            <last_name>Doe</last_name>
        </billing_info>
    </account>
</subscription>
```

### Case 1: Standard subscription

Below is a basic script demonstrating the default configuration for Amazon Pay widgets, displaying the respective address, payment, and consent widgets:

```
var payWithAmazon = new PayWithAmazon({
    sellerId: 'ABC',
    clientId: 'XYZ',
    button: { id: 'pay-with-amazon', type: 'large', color: 'DarkGray' },
    addressBook: { id: 'address-book', width: 400, height: 260 },
    wallet: { id: 'wallet', width: 400, height: 260 },
    consent: { id: 'consent', width: 400, height: 140 }
});
```

### Case 2: No address widget

To simplify the checkout experience, especially when dealing with digital goods where an account address is unnecessary, you can exclude the Amazon address widget as shown in the script below:

```
var payWithAmazon = new PayWithAmazon({
    sellerId: 'ABC',
    clientId: 'XYZ',
    button: { id: 'pay-with-amazon', type: 'large', color: 'DarkGray' },
    wallet: { id: 'wallet', width: 400, height: 260 },
    consent: { id: 'consent', width: 400, height: 140 }
});
```

For more guidance on usage and customization options, refer to  the [GitHub repository](https://github.com/recurly/pay-with-amazon).

## Subscription management

When leveraging Amazon Pay in your subscription checkout, customers will initiate the process by logging in using their Amazon credentials. Following authentication, they will see their securely stored address and payment details, facilitating a seamless billing agreement setup for their subscription plan.

Once the subscription is activated, Recurly retains the billing agreement and pertinent Amazon details. This agreement is automatically employed in subsequent subscription renewals, ensuring a hassle-free transaction cycle for your customers.

<Image align="center" width="50% " src="https://files.readme.io/AkKPBQK6TJapjcMRCJgW_amzn-flow.png" />

Customers retain the autonomy to alter their billing agreements through both Amazon and Recurly platforms:

* **Amazon Interface:** Customers can update payment methods or cancel the billing agreement directly from their Amazon account.
* **Recurly Interface:** As a service provider, you can refresh the billing information using a recently acquired Amazon Billing Agreement ID via this JavaScript library or alternate payment avenues such as credit cards or PayPal. Leverage the [update billing info API](https://docs.recurly.com/api/billing-info) for this. Additionally, Recurly integrates with Amazon's CloseBillingAgreement API, outlined in the [Amazon documentation](https://pay.amazon.com/us/developer/documentation/apireference/201752870), to facilitate billing agreement termination notifications. Enable this feature by contacting Recurly support.

> **Note:** Activities prompted by the user are logged in the account's activity feed.

# Recurly settings

## Sign up for Amazon

To get started, you'll need to create an **Amazon Pay** account. You can do this for free [online](https://payments.amazon.com/register?registration_source=SPPD\&spId=A35095BGBGQR66). If you are already an **Amazon Pay** account holder, simply [log in here](https://sellercentral.amazon.com/).

## Setup in Recurly

Once you have an Amazon Pay account, the next step is to configure your Recurly site to accept Amazon Pay for recurring subscriptions.

To activate Amazon Pay on your Recurly site, adhere to the instructions below:

2. In Recurly, navigate to the [Payment Gateways](https://app.recurly.com/go/configuration/payment_gateways/new) section available in the left-hand menu.
3. Choose Amazon Pay from the available payment service providers (please note, Amazon Pay is currently limited to the US, UK, and EU).
4. Prepare your Amazon MWS Access Key, Secret Access Key, and Merchant ID (or "Seller ID") to input in the designated fields, referring to the image above for help.
5. Decide whether to set the Amazon address as the default in your customer's Account Info (you will find an additional option to replace any pre-existing address in the Account Info, should you opt to enable this feature).
6. Click "Save Changes".
7. Before moving forward, validate the connection by using the "Test Configuration" button. Note that for Hosted Payment Pages, an Amazon Client ID is necessary, and your Recurly subdomain must be included in [Amazon's Security Profile](https://developer.amazon.com/docs/login-with-amazon/web-docs.html).

**Note**: Transactions will not be processed in Recurly's sandbox environment. However, Amazon Pay credentials are valid in both Recurly development and production accounts. To commence live transactions, your Amazon Pay account and Recurly account must be in production mode.

## Amazon Instant Payment Notification Messages (IPN)

Recurly supports the Amazon Pay Instant Payment Notification (IPN) feature, allowing you to receive notifications regarding successful payment refunds. To enable this feature and start receiving refund updates, follow these [instructions](https://pay.amazon.com/us/developer/documentation/lpwa/201909440). When activated, Recurly will obtain the necessary data to update the refund transaction status in your account.

Input your Merchant URL in the designated field in Amazon using the following format:\
[https://callbacks.recurly.com/amazon/](https://callbacks.recurly.com/amazon/)\<MERCHANT\_SUBDOMAIN>

> **Note:** For Recurly sites hosted in the European Union (EU) data centers, use [https://callbacks.eu.recurly.com/amazon/](https://callbacks.eu.recurly.com/amazon/)\<MERCHANT\_SUBDOMAIN> instead.

## Amazon Shipping Address

During the initiation of subscriptions paid through Amazon Pay, customers have the option to input a shipping address. Recurly allows the preservation of this address either as a Recurly Account Address or a Recurly Shipping Address, guided by your gateway configurations:

![](https://files.readme.io/a088525-Screen_Shot_2016-09-08_at_5.19.29_PM.png "Screen Shot 2016-09-08 at 5.19.29 PM.png")

Opting for the Recurly Shipping Address ensures the correct taxation based on the shipping location and the inclusion of the shipping details in the invoice. Learn more about managing [shipping addresses](https://docs.recurly.com/docs/shipping-addresses).

To prevent duplication, matching addresses with existing records in Recurly will be automatically linked to the new subscription.

### Handling customer names

It is imperative to collect both first and last names for storing a shipping address or processing a transaction in Recurly. However, Amazon demands only a singular name. In cases where Amazon does not furnish a last name, an error will be returned via API. To avoid this, encourage customers to supply both names. If a full name is unavailable, Recurly will attempt  to retrieve the full name from Amazon via API, but supplying the full name is recommended.

## Amazon references in Recurly admin

Within the Recurly Admin panel, under the Billing Info section of an Account Details page, you can find references to Amazon Pay engagements. This section provides access to the Amazon Billing Agreement ID, a crucial tool for customer service interactions.

<Image align="center" className="border" width="40% " border={true} src="https://files.readme.io/fdc8297-amzn-billing-info.png" />

Within the Recurly Admin panel, under the Billing Info section of an Account Details page, you can find references to Amazon Pay engagements. This section provides access to the Amazon Billing Agreement ID, a crucial tool for customer service interactions.

# Gateway settings

## Amazon Pay support in Europe and the United Kingdom

Recurly facilitates transactions in the subsequent regions and currencies:

* Europe region, transacting in Euros (€)
* The United Kingdom, transacting in Pounds Sterling (£)

To successfully integrate Amazon Pay in Europe and the UK, note the unique steps and credentials involved below:

### Credentials

Amazon Pay integration in the EU and the UK leverages the delegated authentication model for transaction request signatures. Contrary to the US integration where merchant access key, secret key, and Seller/Merchant ID are required, the EU/UK integrations use the Seller/Merchant ID in conjunction with an MWS Auth token.

## Initiating Amazon sign-up in the EU/UK

Begin by registering for an Amazon Pay account. Choose between an [EU or a UK account](https://sellercentral-europe.amazon.com/). Existing account holders should log in to their Amazon Pay account. Following account creation or login, perform the following:

1. Navigate to "Settings" and then "User Permissions."
2. Click "Visit Manage Your Apps."
3. Opt for "Authorize new developer."
4. Provide the "Developer's Name" and "Developer ID." 
   * **Developer's Name:** Can be any chosen value
   * **Developer ID:** Procure this from your Amazon representative
5. Consent to the MWS terms of service.

## Gateway addition

Amazon Pay EU/UK integrations are distinct gateways necessitating individual setups. Adhere to the instructions stipulated [above](https://docs.recurly.com/docs/amazon-payments#section-setup-in-recurly) for each gateway addition, utilizing your new MWS auth token.

## Specifying the Amazon Pay region

**Region Code** — It is imperative to relay the accurate region code during EU/UK Amazon Pay transaction requests to prevent default currency settings to USD in Recurly. Neglecting this could usher in potential declines for one-off transactions, initial subscription transactions, and renewal processes via the Recurly API, as transactions may not channel to the intended Amazon Pay region. Refer to the [developer documentation](https://dev.recurly.com/docs/create-an-accounts-billing-info-using-external-token) for guidance.

### Supplementary details

**Region-specific billing agreements:** Amazon Pay billing agreements retain validity exclusively in the originating region. Transitioning a user's region necessitates the establishment of a fresh billing agreement in the newfound region.
