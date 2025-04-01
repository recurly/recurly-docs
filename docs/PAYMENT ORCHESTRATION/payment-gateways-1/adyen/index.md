---
title: Adyen
excerpt: >-
  Harness the power of Adyen's global payment solutions, seamlessly integrated
  with Recurly, to elevate your business's payment experience.
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

> ❗️ Minimum processing requirements
>
> Adyen has minimum processing requirements and business models they do not support. Please visit [Adyen's website for more information](https://www.adyen.com/legal/list-restricted-prohibited?mkt_tok=MjIyLUROSy0zNzYAAAGPMM_PtMP-Xz-XaJOJB7kmd-DhumEcSErBEdAyqPULl6ckhuqb_dcb2htv_ePOEO4LvBDy9CQIeirlhX4uJtK2DXSbiiQADkUNnrcdA_b3BdSD-w) to see if your business qualifies. For questions involving minimum processing requirements, please reach out to Adyen directly.

* Asynchronous payment methods might take 48 hours or more (dependent on the payment method) for confirmation.
* Use Recurly.js or the Recurly API for credit and debit card transactions.
* SEPA supports only EUR payments. Ensure SEPA transactions are in EUR.

# Definition

Recurly's integration with Adyen allows businesses to leverage a robust, enterprise-level payment processor known for its extensive worldwide coverage. It simplifies credit/debit card processing, along with other payment methods, ensuring a frictionless experience for end-users.

> **Note**: Visit our [guide on testing your gateway configurations ](https://docs.recurly.com/docs/how-to-test-your-gateway)in Recurly to ensure your payment processes are set up correctly.

# Key details

| Feature                         | Description                                                                                                                                                                                                                                                                                                                   |
| ------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Services that work with Recurly | Credit/Debit cards, ACH, Boleto, iDeal, Sofort (Klarna Debit Risk), SEPA, BACS, Google Pay and Apple Pay, Cash App                                                                                                                                                                                                            |
| Supported operations            | Authorize & Capture, Purchase, Refund, Verify, Void                                                                                                                                                                                                                                                                           |
| Supported payment types         | Credit/Debit cards, ACH, Boleto, iDeal, Klarna Debit Risk (only existing merchants), SEPA, Google Pay and Apple Pay, Cash App. **Note:** Only a subset of payment methods are supported in the new Adyen Components Recurly.js support. Excluded payment methods are: All Direct Debit, Klarna Debit Risk, iDeal, and Boleto. |
| Supported card brands           | Visa, MasterCard, American Express, Discover, JCB, Diners Club, China Union Pay, ELO (BRL only), Hipercard (BRL only), Cartes Bancaires, Dankort, Bancontact                                                                                                                                                                  |
| Gateway Specific 3DS2 Supported | Yes                                                                                                                                                                                                                                                                                                                           |
| Card on File Supported          | Yes                                                                                                                                                                                                                                                                                                                           |
| Regions                         | Global                                                                                                                                                                                                                                                                                                                        |
| Currencies                      | <a href="https://docs.recurly.com/docs/currency-support-by-gateway" target="_blank">All available.</a> with special behavior for **ISK** and **CLP**.                                                                                                                                                                         |

## How asynchronous payments work

* Upon a successful purchase, the subscription is marked "active", but the invoice and transaction remain "processing" until Adyen confirms payment approval.
* Recurly sends a "processing payment" webhook to configured endpoints and a "payment processing" email to customers (if enabled).
* Adyen's initial return token post-billing is "unverified", awaiting bank payment approval.
* Within 48 hours, the token is "verified" after bank confirmation, enabling further transactions.
* The status of the transaction and invoice is updated in Recurly based on Adyen's feedback. Appropriate webhooks and emails are issued to businesses and customers respectively.
* **Dunning and Retries:** Asynchronous payments require special handling in dunning. Refer to the [PayPal eChecks section](https://docs.recurly.com/docs/paypal-payments#paypal-echecks) for detailed insights.

## Asynchronous payment methods

Adyen offers various asynchronous payment methods like SEPA and Boleto, which take several days for settlement. Due to this, the payment processing for such methods deviates slightly in Recurly.

## For customer billing information updates

For billing information changes, direct customers to Recurly's hosted pages. Recurly charges the new billing info a minimal amount. Once Adyen validates the new info (i.e., approves the purchase), Recurly automatically issues a refund.

## IP address allowlist

For certain scenarios, Adyen may employ additional IP addresses. These must be whitelisted in Recurly. Before transitioning to Production, contact Recurly Support for assistance.

## API Integration with Recurly

Typically, purchases using Recurly.js involve Recurly handling payments natively. The customer first provides their billing details. Once authorized, you create the subscription and process the charge.

# Setting up payments with Adyen

> 📘 Ensure Adyen Settings are set properly:
>
> Two features are necessary to ask Adyen Support to set properly:
>
> * **API PCI Payments role** for your User. See Step 11.i below for more information.
> * **Skip CVC** for your Merchant Account. See Step 11.ii below for more information.

Ensure a webservice user is set up on Adyen to permit Recurly to dispatch transactions to your gateway.

1. **Access** the Adyen dashboard.

2. **Navigate** to “Developers” → “API Credentials”.

3. **Click** "Create new credential".

4. In the modal that appears,  **select** "Web service user" under "Credential Type".

5. **Enter** your user name and include a description if you wish. For example: Recurly Adyen Credentials

<Image align="center" className="border" border={true} width="75% " src="https://files.readme.io/0958525-Screenshot_2023-10-26_at_1.45.41_PM.png" />

6. Ensure your API credentials have the 'Merchant Recurring Role' checked, or you will not be able to process recurring transactions using stored data within Recurly.

   <Image align="center" src="https://files.readme.io/47ce985afb27f46153651193d5dd02935a1c3a28c3fd4b64c724d175cc8a33a8-Screenshot_2025-02-07_at_9.45.08_AM.png" />
7. Your new credential will be created, and your password will be available under “Server settings” → “Authentication” → “Basic auth” on the subsequent page. You will not be able to access this password after leaving this page, so make note of it immediately. Otherwise, you will need to regenerate the password from this page.
8. **Record** the auto-generated username and password for later use in Recurly.
9. **Click** ‘Save changes’.

<Image align="center" className="border" border={true} width="75% " src="https://files.readme.io/748ce08-Screenshot_2023-10-26_at_1.46.10_PM.png" />

9. In the "Risk" section under "Dynamic 3D Secure", **update** the Dynamic 3DS setting to "prefer no" unless you specifically wish to always require 3DS on your Adyen instance. You should not do this on a gateway instance where recurring billing is running
10. For those adhering to the <a href="https://docs.recurly.com/docs/revised-payment-services-directive-psd2" target="_blank">PSD2 Mandate</a>, **follow** our <a href="https://docs.recurly.com/docs/gateway-specific-updates#section-adyen" target="_blank">Adyen-specific guidelines</a>.
11. **Request**
    1. Adyen support to activate the “**API PCI Payments role**” for your web services user, as it isn't active by default. Without this enabled, payments using a raw card number will fail.
    2. Adyen support to **disable the CVC requirement** on your Merchant Account if you do not collect CVC (CVV codes) from returning or known customers. If you do wish to collect CVC (CVV codes) on all Customer Initiated transactions, ensure your integration supports collecting and passing the code to Recurly via API.
12. Additionally, **ensure** that “Acquirer Result” and “Raw Acquirer Result” are enabled in the API responses.

# Webhooks configuration

Accurate configuration of the callbacks URL is pivotal for Recurly to receive apt status updates for transaction records.

1. **Navigate** to “Developer” >> “Webhooks”.
2. **Click** “+ Webhook” and find "Standard webhook" and click "Add".
3. Under "Server configuration," **locate** and **click** on the pencil icon. In the field provided, enter the URL `https://callbacks.recurly.com/adyen/<MERCHANT_SUBDOMAIN>`, replacing "\<MERCHANT\_SUBDOMAIN>" with your Recurly site's actual subdomain. Once done, **click** on the "Apply" button.

<Image align="center" className="border" border={true} width="75% " src="https://files.readme.io/fc70703-image.png" />

**No other settings changes should be made in this section.**

> **Note:** If your site is hosted in Recurly's European Union (EU) data centers, use callbacks.eu.recurly.com in place of callbacks.recurly.com.

4. **Ensure** the "Enabled" toggle is set as shown:

<Image align="center" className="border" border={true} width="75% " src="https://files.readme.io/1a31b55-image.png" />

5. **Click** “Save changes” at the bottom of the page.

# Activation of "Network Transaction Reference" Value

To successfully process **MIT (Merchant-Initiated Transactions)** across all payment methods, including and not limited to **Google Pay, Apple Pay, and cards**, you must activate **"Network transaction reference"** in your Adyen Merchant Account settings. Navigate to **Developers > Additional Data** in Adyen to enable this feature. Once activated, Adyen will generate a unique transaction ID for direct integrations; however, this ID will **not** be visible in Recurly.

1. **Add the Adyen gateway**: Go to **Configuration → Payment Gateways → Add New Gateway** in your Recurly Admin.
2. **Enter your Adyen credentials**: Provide the **username**, **password**, and **merchant account** details from your Adyen configuration.
3. **Set the custom endpoint** (recommended): Only include the specific portion of the endpoint provided by Adyen, rather than the entire URL. While testing, you can use any placeholder, but update it for production.
4. **Select "Zero Dollar Authorization"** for all card types.
5. **Save** your configurations.

> **Note:** Enabling **Network Transaction Reference** in Adyen is required for successful MIT exemptions and payment processing across all methods—including (but not limited to) Google Pay, Apple Pay, and cards. If this setting isn’t enabled, transactions may fail even if your other Adyen settings are correct.

## Special Currency Considerations

While **ISK** and **CLP** are technically zero decimal currencies (meaning they cannot have partial amounts in cents), Adyen does not have plans to update their logic around these currencies. In order to support these currencies, Recurly will be taking the amount sent in the V3 API and adding the necessary '00' decimal places when sending these transactions to Adyen. It is important to not do this in your own integration to avoid overcharging your customers.

**Examples:**

If the Amount value is sent in as '23', Recurly will send '2300' to Adyen. Ensure your intent is to charge 23 ISK. If a Plan amount is set to 23.00, we will also send the amount to Adyen as 2300 instead of just '23'.

## Adyen ACH

Recurly provides an integrated solution for ACH transactions through Adyen. Delve into the nuances of ACH payments by visiting our dedicated ACH Bank Payments <a href="https://docs.recurly.com/docs/check-gateway-ach" target="_blank">documentation</a>.

### Adyen configuration

To integrate the ACH gateway, initiate the 'Adyen ACH' gateway on the "Add Payment Gateway" page.

Moreover, ensure these specific configurations are correctly set to effectively process ACH transactions:

1. **Set up** the "report credentials". A step-by-step guide is available [here](https://docs.recurly.com/docs/adyen#setting-up-report-credentials-for-ach-and-sepa).
2. Actively **subscribe** to the Payment Accounting Report. A detailed process can be found [here](https://docs.recurly.com/docs/adyen#subscribing-to-the-payment-accounting-report-for-ach).
3. Within Adyen, **adjust** settings to "immediate capture" for transactions.

> **Note**: First/Last name on Checks should not be sent as dashes ( - - ) as this will cause immediate declines.

## Adyen Direct Debit

### BACS

Bankers' Automated Clearing Services (BACS) Direct Debit is a widely used payment method in the United Kingdom. BACS payments support one-time and recurring transactions, however due to chargeback and late failure risks, along with the asynchronous nature of Direct Debit payments, we do not recommend using this payment method for one-time charges where physical product is being shipped.

BACS on Adyen runs specifically on Adyen gateway tokens, so Recurly does not have access to the underlying payment details. That said, this payment method still allows one-time and recurring charges to occur via Recurly.js and APIs.

#### BACS Compliance

When using Recurly.js, you are responsible for obtaining consent and displaying appropriate regulatory information to the consumer on your website. The consumer should be aware of the amount, due date of future charges, frequency, and your Merchant business name when signing up for subscriptions.

Additionally, it would be a good idea to note that Adyen's name will appear on bank statements as "ADYEN RE \[Merchant Name]'.

### SEPA

Single Euro Payments Area (SEPA) Direct Debit stands as a predominant payment mode across the European Union (EU). SEPA is instrumental for merchants aiming to expand their market reach within the EU. This method facilitates one-time or recurring payments in Euros by leveraging the customer's name and bank account number (IBAN format).

As stipulated by the SEPA Direct Debit rulebook, it's imperative for merchants to notify customers each time an account debit is made. To ensure seamless communication, Recurly automatically dispatches an email to the customer. Further details can be accessed [here](https://docs.recurly.com/docs/renewal-reminder#sepa-payment-method).

Recurly supports automated retries for SEPA payments on Adyen. [Learn more about SEPA Retries](https://docs.recurly.com/docs/sepa-retries) by visiting our documentation on the feature.

### **Direct Debit Recurly configuration**

In your Recurly platform:

* Integrate Adyen as your [gateway](https://docs.recurly.com/docs/adyen).
* Select the BACS checkbox under APMs in Adyen.
* Enable the EUR currency for SEPA and the GBP currency for BACS. Find out more about currency addition <a href="https://docs.recurly.com/docs/currencies" target="_blank">here</a>.

### **Adyen SEPA and BACS configuration**

Within your Adyen platform:

* Activate SEPA and/or BACS, depending on your needs.
  * Ensure the EUR currency is available for SEPA transactions.
  * Ensure the GPB currency is available for BACS transactions.
* Enable RECURRING\_CONTRACT webhooks. A guide is available <a href="https://docs.adyen.com/development-resources/webhooks/webhook-types/" target="_blank">here</a>.

## Dual Badge Card Support

On the Adyen platform, Recurly supports the card types of **Cartes Bancaires**, a card brand offered to French customers, **Dankort** which is available only to Danish customers (DKK currency), and **Bancontact**, a brand offered in Belgium. These types of cards are known as "dual-badged" meaning the customer has a preference of which network they process their transactions and subscriptions with. Customers can select the major network (Visa or MasterCard), or the regional network (Cartes Bancaires, Dankort, or Bancontact) when processing a transaction.

Dual Badge Compliance has two factors: *choice* and a *non-distinction policy* between credit and debit. Customers must be given a choice between Visa or the dual-badged option,  *and* be given the option to enter their card into a single field labeled 'Card', whether the card is debit or credit. If you are using Recurly.js elements, this is available and built into elements for you. If you are building your own UI, keep these regulations in mind.

To enable Cartes Bancaires, Dankort, or Bancontact support on your Adyen gateway, ensure you follow the below steps:

1. Within the Adyen gateway settings, ensure **Cartes Bancaires**, **Dankort**, and/or **Bancontact** are checked as a card payment method(s) you wish to accept.
2. Integrate to Recurly.js using either the *cardElement* or *cardNumberElement* parameters. See [Recurly.js documentation](https://recurly.com/developers/reference/recurly-js/#elements) and our [Dual/CoBadged guide](https://recurly.com/developers/guides/co-badge.html) for instructions on enabling card brand network preference within your implementation.
3. In the case of Bancontact, ensure that SEPA is also enabled as Bancontact transactions will be converted to SEPA payments for recurring purposes.
   1. Fun facts:
      1. Bancontact cards do not have or require CVV codes.
      2. Bancontact cards will always require 3D-Secure. Ensure this is enabled in your Adyen account and Recurly integrations as appropriate.
      3. Bancontact does not support separate auth and capture.
4. In the case of Dankort, ensure the DKK currency is enabled on your Adyen and Recurly sites as Dankort is only accepted with this currency.

The *customer* experience will be: A consumer will enter their card into the card field and if their card offers a choice, they should be presented with the options available to them as applicable to their card. They can select their network preference, and continue with their purchase or subscription sign up.

The same choice will be available when updating a billing info or changing billing information to a different dual-badged card. Cards stored in Recurly will retain that choice for subscription processing.

**Notes:**

* Cartes Bancaires cards experience less declines when transactions are submitted with the cardholder's billing address. Ensure you are capturing your customers' billing address if they're using a Cartes Bancaires card within your solution.
* Bancontact acceptance requires SEPA acceptance as well (see below). Please ensure you have SEPA enabled at Adyen and Recurly in order to take full advantage of Bancontact payments. For information on enabling SEPA with Adyen, please see our [SEPA setup instructions](https://docs.recurly.com/docs/adyen#adyen-sepa) below.
* Dankort acceptance requires the **DKK** currency to be enabled at Recurly and Adyen.

## Adyen Cash App Pay

Cash App Pay is a digital wallet in the U.S. that allows users to make purchases using their Cash App balance, or linked credit card, debit card, or bank account. Cash App consumers will be able to choose 'Cash App Pay' during checkout, scan a QR code, and authorize the payment through the Cash App application on their phone.

Cash App through Adyen is only supportive of US / USD transactions.

Cash App requires Adyen's RECURRING\_CONTRACT webhooks. Please refer to [configuration setup steps](https://docs.recurly.com/docs/adyen#additional-configuration) below or [Adyen's documentation](https://docs.adyen.com/development-resources/webhooks/webhook-types/#webhooks-settings-page) for more details on webhook setup.

### **Recurly Configuration**

In your Recurly platform:

* Integrate Adyen as your [gateway](https://docs.recurly.com/docs/adyen) using Recurly.js Alternative Payment Methods. You can find this information in [Recurly Developer Hub](https://recurly.com/developers/reference/recurly-js/#alternative-payment-methods).
* Enable the USD currency. Find out more about currency addition <a href="https://docs.recurly.com/docs/currencies" target="_blank">here</a>.
* Check 'Cash App Pay' in your Adyen Payment Gateway settings within your Recurly site under 'Alternative Payment Methods'.

### **Adyen configuration**

Within your Adyen platform:

* Activate Cash App Pay.
* Ensure the USD currency is available.
* Enable RECURRING\_CONTRACT webhooks. A guide is available <a href="https://docs.adyen.com/development-resources/webhooks/webhook-types/" target="_blank">here</a>.

## Adyen SEPA

See 'Adyen Direct Debit > SEPA'.

## Adyen iDeal

iDEAL is a widely embraced banking payment option in the Netherlands, representing a significant portion of the region's online transactions. During a transaction using iDEAL on Recurly’s checkout, customers will choose their respective banks from an accessible list of iDEAL-affiliated banks. Subsequently, they will be redirected to their bank's platform to complete the payment process.

It's important to note that the inaugural payment for a subscription employs iDEAL, while subsequent payments utilize SEPA Direct Debit (owing to iDEAL's non-support for recurring payments). It's advisable to clearly communicate to customers that post the initial iDEAL transaction, recurring payments will be managed through SEPA Direct Debit.

### **Recurly configuration**

* Integrate Adyen as the gateway.
* Activate SEPA for periodic payments.
* Ensure the EUR currency is in operation.
* Delve into the Recurly.js development guide <a href="https://recurly.com/developers/reference/recurly-js/#alternative-payment-methods" target="_blank">here</a>.

### **Adyen configuration**

* Activate SEPA for subsequent payments.
* Ensure the EUR currency is functional.
* Enable RECURRING\_CONTRACT webhooks. A guide is available <a href="https://docs.adyen.com/development-resources/webhooks/webhook-types/" target="_blank">here</a>.
* Incorporate “Ideal details” webhooks. Steps can be found <a href="https://docs.adyen.com/development-resources/webhooks/webhook-types/#other-webhooks" target="_blank">here</a>.

### **Restrictions and guidelines**

* Due to inherent iDEAL constraints, free trials via iDEAL are non-permissible. For free trials, Recurly suggests opting for SEPA Direct Debit.
* iDEAL cannot be used for subscriptions with a deferred commencement date.
* Chargeback management isn't feasible with iDEAL.
* Recurly's Checkout and Hosted Payment Pages do not support iDEAL.
* For a comprehensive list of limitations, refer [here](https://docs.recurly.com/docs/adyen#limitations).

## Adyen Sofort  (Klarna Debit Risk)

> 📘 Restriction
>
> Only merchants who have an existing Sofort/Klarna Debit Risk account with Adyen may use this payment method. New signups are not available with the gateway.

Sofort  Klarna Debit Risk) stands out as a preferred online banking payment mechanism in countries like Germany, Austria, Switzerland, and Belgium. This payment method is compatible with EUR, CHF, and GBP currencies.

To transact with Sofort (Klarna Debit Risk), customers will choose their country, provide their bank details, and finalize the payment after receiving a confirmation from their bank.

For recurring transactions, Sofort (Klarna Debit Risk) isn't viable, and SEPA is utilized instead.

### **Recurly configuration**

* Initiate the Adyen Gateway.
* Activate SEPA for subsequent payments.
* Ensure the EUR currency is operational.
* The Recurly.js developer guide can be accessed here.

### **Adyen configuration**

* Ensure the relevant currencies are active.
* Integrate the OFFER CLOSED event within the Standard webhook. Guidance is available <a href="https://docs.adyen.com/development-resources/webhooks/webhook-types/#standard-webhook-page" target="_blank">here</a>.

### **Restrictions and guidelines**

* *Sofort is being phased out by Klarna and no new merchant accounts can be acquired at this time. Sofort will be replaced by Klarna Debit Risk behind the scenes at Adyen on September 30th. Merchants will see branding and UI changes after that time period. Adyen has stated no major technical changes are necessary, but that it is important to pass along the Country Code for proper routing. Please update your Recurly.js implementations if you are not passing this field.*
* Inherent limitations in Sofort (Klarna Debit Risk) restrict its use for free trials. For such offers, Recurly suggests SEPA Direct Debit.
* Sofort (Klarna Debit Risk)  isn't compatible with subscriptions that have a deferred start.
* Sofort (Klarna Debit Risk)  transactions cannot be chargeback managed.
* Recurly’s Hosted Payment Pages don't support Sofort (Klarna Debit Risk).
* For a holistic understanding of the limitations, refer [here](https://docs.recurly.com/docs/adyen#limitations).
* SOFORT is also known as Klarna Debit Risk. This payment method is *not* the BNPL/Buy Now Pay Later flavor of Klarna.

## Adyen Boleto

Boleto Bancário, commonly known as Boleto, a popular payment method in Brazil, is usually utilized by individuals without access to bank accounts. This payment method is compatible with BRL

This guide outlines the steps to integrate Boleto with your payment systems through Adyen and Recurly, focusing on initial setup, checkout integration, and handling recurring payments.

### Recurly configuration

* Activate Brazilian Real (BRL) currency.
* Integrate Adyen as a gateway.
* Leverage Recurly JS to integrate the Boleto payment option directly into your checkout page.
* Establish a Boleto-specific email template for recurring payments. This template should be designed to notify shoppers about upcoming payments and provide them with a direct link to download the Boleto invoice.

### Adyen configuration

* Contact your Adyen representative to ensure your account is aligned with an entity recognized in Brazil.
* Enable the Boleto payment method within your Adyen account settings.
* Make sure that Brazilian Real (BRL) is activated in your Adyen account.

### Restrictions and guidelines

Due to Boleto's nature, which does not support direct recurring transactions, a specialized process is implemented to handle subscription renewals:

* For each renewal, Recurly automatically generates a new recurring invoice. This invoice initially appears as "Past Due" to account for the Boleto payment processing time.
* Recurly then communicates with the payment gateway to issue a new Boleto invoice for the renewal amount.
* Utilize the previously configured Boleto email template to inform customers about the new invoice, providing them with a link to download the Boleto.
* Once the customer pays the Boleto invoice, the status of the invoice in Recurly is updated to "Paid," completing the transaction cycle.
* Consider using Boleto as a method to increase customer balance, offering flexibility in payment options and enhancing customer satisfaction.

## Additional configuration

For Adyen to send essential details to Recurly, set up specific features based on your payment method.

### **Setting up "Report Credentials" for ACH and SEPA:**

1. **Log** into Adyen, choose "Developers" > "API credentials".

<Image align="center" className="border" border={true} width="75% " src="https://files.readme.io/0e9f446-Screenshot_2023-10-26_at_2.32.53_PM.png" />

2. If there's no "reporting user", **create** one. **Designate** it as "Report service user".
3. **Save** the password generated under “Server Settings” >> “Authentication” >> “Basic auth” prior to saving changes, or you will need to regenerate the password.
4. Enter the credentials in Recurly under "REPORTS USERNAME" and "REPORTS PASSWORD".

<Image align="center" className="border" border={true} width="75% " src="https://files.readme.io/0ad6c72-image.png" />

### **Subscribing to the payment accounting report for ACH**

1. In Adyen, **go** to Reports. In the "Finance" section, click on “Payment Accounting" and then “Manage report”. You will see “Automatic (generate on a schedule)” set to Off if you have never enabled it.

<Image align="center" className="border" border={true} src="https://files.readme.io/d471c36-image.png" />

<Image align="center" className="border" border={true} src="https://files.readme.io/f40b511-image.png" />

2. **Select** "Automatic" and toggle automatic generation to “On” and set the file type as CSV. Click the ‘X’ to close the dialogue box.

<Image align="center" className="border" border={true} width="75% " src="https://files.readme.io/cbce972-image.png" />

3. If you **click** “Manage report” again, you can **confirm** that the report is now automatically generated.

<Image align="center" className="border" border={true} src="https://files.readme.io/667dc93-image.png" />

### **Configuring Adyen notifications for Recurly**

1. In Adyen, **go** to Developers > Webhooks.

2. **Click** “+ Webhook” using the upper-right blue button.

<Image align="center" className="border" border={true} width="75% " src="https://files.readme.io/99e16dc-image.png" />

3. **Add** these 4 webhook types: Direct-Debit Pending, Generic Pending, Report details, and Standard webhook.
   1. Ensure you have enabled the `RECURRING_CONTRACT` event code. This is required for tokenized payment methods to function properly.
   2. Adyen Documentation lists two places -- please ensure both are handled, or the webhook may not be sent.
      1. [Standard Webhooks Page](https://docs.adyen.com/development-resources/webhooks/webhook-types/#standard-webhook-page)
      2. [Webhooks Settings Page](https://docs.adyen.com/development-resources/webhooks/webhook-types/#webhooks-settings-page)
4. **Ensure** you are entering the correct callback URL in the Server configuration of each webhook. Click “Apply” and then “Save changes” for each webhook you activate.

These payment methods are pivotal for merchants aiming to expand in Europe and other relevant regions. With Recurly’s integration with Adyen, businesses can offer their customers a plethora of payment options, facilitating smoother transactions and increasing conversion rates. For any queries, connect with our <a href="https://www.recurly.com/contact-us/" target="_blank">support</a> or explore our expansive <a href="https://docs.recurly.com/docs/" target="_blank">knowledge base</a>.

# Important notes

* Adhere to regulations around customer notifications, like SEPA's renewal notice requirements.
* Recurly can export billing info from Adyen for SEPA subscription renewals.
* Recurly sends purchase transactions to Adyen with a capture flag, overriding your Adyen settings.
* Currently, Recurly's Adyen integration doesn't support Level 3 card data.

# Troubleshooting

**Q:** An Tokenized Payment Method I am using (all non-Card payments) is not allowing conversions or subscriptions are failing. What can I do?\
**A:** Ensure you have enabled the proper Webhooks -- `RECURRING_CONTRACT` webhooks are critical to ensuring these payment methods function properly. Please see our configuration documentation for these webhooks above.

**Q:** My customer tried to check out but received a decline from Adyen, what happened?\
**A:** It will depend on the decline code you see in your Recurly Admin page for this transaction. If the rejection is due to 3DS requirements, please ensure you have 3DS enabled and configured both in Adyen and in your Recurly.js integration. If you already have 3DS enabled, the customer may not have completed the 3DS challenge successfully and the decline is expected.