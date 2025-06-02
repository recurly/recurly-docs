---
title: Cybersource
excerpt: >-
  Seamless and secure payment processing with CyberSource integration for
  Recurly.
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

# Definition

CyberSource is a full-service payment management platform. When configured with Recurly, it allows you to securely manage your transactions. You will need a CyberSource Merchant ID and a Transaction Security Key for the SOAP Toolkit API to enable this integration.

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
        Payment Processing
      </td>
    </tr>

    <tr>
      <td>
        Supported Operations
      </td>

      <td>
        Transaction Processing: Purchase, Auth and Capture, Void, Refunds, AVS Checks
      </td>
    </tr>

    <tr>
      <td>
        Supported Payment Types
      </td>

      <td>
        Credit/Debit Card, Apple Pay

        * Apple Pay is not supported with TSYS/Vital acquirer
      </td>
    </tr>

    <tr>
      <td>
        Supported Card Brands
      </td>

      <td>
        Visa, MasterCard, American Express, Discover, Diners Club, JCB, Union Pay
      </td>
    </tr>

    <tr>
      <td>
        Gateway Specific 3DS2 Supported
      </td>

      <td>
        Yes
      </td>
    </tr>

    <tr>
      <td>
        Card On File Supported
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
        Global
      </td>
    </tr>

    <tr>
      <td>
        Currencies
      </td>

      <td>
        See <a href="https://docs.recurly.com/docs/currency-support-by-gateway" target="_blank">all available.</a>
      </td>
    </tr>
  </tbody>
</Table>

# Address Verification System (AVS) settings

Merchants using CyberSource have the option to tailor their Address Verification System (AVS) checks. You can:

* Enable AVS checks for all transactions,
* Enable AVS checks for only US/Canada transactions, or
* Disable AVS checks altogether.

Recurly recommends enabling AVS for the US and Canada only. This setting can be found when configuring/editing a CyberSource gateway in Recurly.

> **Note:** AVS checks typically work best for the US and Canada, and may be inconsistent or unsupported in other countries. CyberSource allows you to decline transactions based on the AVS result, and the above options give you the flexibility to decide whether or not to bypass AVS checks for certain countries.

#### CyberSource processor configuration

CyberSource may require different integrations based on the processor used for a given CyberSource account. To ensure Recurly sets the correct parameters for your integration, you must:

* Set the main processor for your account in the "CREDIT CARD PROCESSOR" selector when configuring the CyberSource gateway in Recurly.

This is essential as it determines how transactions are handled between Recurly, CyberSource, and your processor.

# Configuring CyberSource gateway in Recurly

### Step 1: Obtain your CyberSource credentials

* Log into your CyberSource Business Gateway. If you do not have an account, you will need to sign up for one through CyberSource.

### Step 2: Generate a SOAP toolkit key

* Log into your business center account, and navigate to **Payment Configuration → Key Management** and select **Generate Key** and choose “SOAP Toolkit API” within your CyberSource dashboard.
* Click on **Download Key** to create a new Key. If you are asked for a password, this will be your Merchant ID.
* Copy the new key generated *before* leaving the page. You will need this key to connect CyberSource with Recurly.

### Step 3: Generate your P12 Certificate File and Password

* Log into your business center account, and navigate to **Payment Configuration → Key Management** and select **Generate Key** and choose “REST Certificate” within your CyberSource dashboard.
* Click on **Download Key** to create a new Key. **Ensure you know where this file is downloaded** as you will need it in Step 4.
* Create a password for the certificate by entering the password into the New Password and Confirm Password fields, and then click Generate key. **Keep this password** as you will need it in Step 4.

### Step 4: Enter CyberSource credentials in Recurly

* Log into your Recurly account and navigate to the Payment Gateways page.
* Click on the "Add a New Gateway" button at the top right of the Payment Gateways page.
* Select “CyberSource” from the list of available gateways.
* Enter your **CyberSource Merchant ID** into the “Login” field.
* Paste the **SOAP Toolkit key** that you copied earlier into the “Key” field.
* Upload the **P12 File Certificate** that you generated in Step 3 to the file upload button.
* Enter the **P12 Password** that you generated in Step 3 to the P12 File Password field.

### Step 5: Configure your 3DS2 support (optional)

* If you wish to support 3DS2 verification flows on Cybersource, check the box **Enable 3DS2 support**. Only enable this if you have 3DS enabled at Cybersource.
* Reach out to Recurly Support to enable the `challengeCode` parameter for your implementation if you want to enforce 3DS challenges for subscription signups and one-time charges. **Note**: not all Cybersource processors support this feature. Talk to your Cybersource representative before enabling this on Recurly, or payments can fail.

### Step 6: Set your credit card processor and card types

* Under the ‘ACCEPTED CARD TYPES’ header, you will see multiple card brand names. Only enable (select) those card types that you have enabled on your Cybersource account.
* In the “CREDIT CARD PROCESSOR” selector, choose the main processor for your CyberSource account. This is necessary for Recurly to set the correct parameters for transactions. If you are not sure which option to select, consult with your Cybersource account representative. **Do not leave this selection unset -- various compliance mandates rely on this information to properly pass data to the gateway.**

### Step 7: Enable currencies

* USD will be enabled by default. If you want to add additional currencies, or remove USD, use the selection tool on the left to add the currencies your Cybersource gateway accepts.

### Step 8: Enable zero dollar authorizations

* It is extremely important to ensure you have enabled this on your card types available. Zero dollar authorizations will be an important part of validating card data prior to subscriptions starting or when offering free trials.

### Step 9: Configure AVS settings

* Decide whether you want to enable Address Verification System (AVS) checks and for which transactions:
  * All Transactions
  * US/Canada Transactions Only (recommended)
  * Disable AVS Checks
* Select your desired option from the AVS settings while configuring/editing the CyberSource gateway in Recurly.

### Step 10: Save and enable the gateway

* After entering all the required information, click on the "Add Payment Gateway" button at the bottom of the page.
* You will see that CyberSource has been added to your list of Production Gateways in Recurly with a status of "Enabled".

### Step 11: Test the configuration (recommended)

* Make a test transaction to ensure that the integration is working correctly. This can be done in development mode for your sandbox site in Recurly before moving to a live environment.

### Step 12: Go live

* After testing, if everything is working as expected, you are ready to accept live payments through the CyberSource gateway via Recurly.\
  **Pro Tip:** Keep your CyberSource credentials secure and ensure only authorized personnel have access to this information. Regularly review and regenerate your SOAP Toolkit Keys for added security.
  *Please note:* Always consult with your CyberSource account representative or support resources to ensure that your account is in good standing and that you are compliant with all relevant regulations and requirements.