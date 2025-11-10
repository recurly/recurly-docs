---
title: First Data
excerpt: >-
  Streamline your payment process, secure customer transactions, and optimize
  your business operations with the First Data GGe4 Gateway integration in
  Recurly
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
> ❗️ For internal use only. Do not share with merchants.

# Overview

### Required plan

This feature or setting is available to all customers on any Recurly subscription plan.

# Definition

First Data is a comprehensive payment gateway solution. Recurly supports integration with First Data's GGe4 Gateway for US merchants, facilitating seamless and secure payment transactions.

# Key details

| Features                        | Description / Availability                                                                                                      |
| ------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- |
| Services that work with Recurly | Payment processing, Subscriptions, [MOTO](https://docs.recurly.com/recurly-subscriptions/docs/moto-transactions#/)   Processing |
| Supported operations            | Payment, Auth and Capture, Void, Refund                                                                                         |
| Supported payment types         | Credit Card, Debit Card                                                                                                         |
| Supported card brands           | Visa, MasterCard, Amex, Discover, JCB, Diners Club                                                                              |
| Gateway Specific 3DS2 Supported | No                                                                                                                              |
| Regions                         | United States                                                                                                                   |
| Currencies                      | Multiple, including AUD, CAD, EUR, GBP, NZD, PLN, and USD                                                                       |

## Setting Up First Data GGe4 Gateway with Recurly

To connect your Recurly site to your First Data GGe4 gateway account, you will need the following credentials:

* Gateway ID
* Password
* HMAC Key ID
* HMAC

## Creating a User for the Results API

For the best performance and reliability, Recurly strongly recommends creating a separate, read-only user account in First Data. This account allows Recurly to automatically query the transaction status, which is especially valuable if the GGe4 gateway becomes unresponsive or if a network issue arises after a transaction is submitted. Enter the credentials for this read-only user in the Recurly gateway configuration page.

For detailed steps, refer to the First Data [docs on Results API](https://support.payeezy.com/hc/en-us/articles/203731249-Real-time-Payment-Manager-RPM-User-Guide#3).

### Important Notes:

* **'Results API' credentials expire every 60 days.** It is critical to update these credentials before they expire to maintain uninterrupted service.
* **Failure to update the 'Results API' credentials will result in requests returning an 'invalid_credentials' error.** If 12 of these erroneous requests are made in 15 minutes, the entire integration may be suspended due to an "IP-Lockout" scenario.  
  For further details, refer to First Data’s [documentation on creating an account](https://support.payeezy.com/hc/en-us/articles/203731249-Real-time-Payment-Manager-RPM-User-Guide#3).

## AVS Settings

When adding a new credit card in Recurly, a transaction is created, and the given billing address is submitted to the payment gateway along with other transaction information. An AVS (Address Verification System) response is then returned to Recurly. This is vital for fraud prevention, and First Data’s GGe4 gateway allows you to tailor this to your needs. You can choose to require a partial match on AVS responses for transactions (recommended) or to bypass the AVS response, allowing transactions irrespective of AVS issues.

> 📘 **Credentials Reminder**
>
> To activate your First Data gateway, enter your Gateway ID, Password, HMAC Key ID, and HMAC on the credentials page within Recurly.
>
> > **Please Note:** AVS responses are only validated on initial transactions (i.e., when a credit card is first added in Recurly). AVS responses for recurring transactions are disregarded.
> >
> > Below is the "Step-by-Step Process" section for the Recurly user guide, which is designed to guide the users through the process of integrating First Data’s GGe4 gateway with Recurly. In addition, there is a specific guide on how to set up a read-only user for the Results API on the First Data GGe4 Gateway portal.

# Step-by-Step Process to Integrate First Data's GGe4 Gateway with Recurly

### Step 1: Gather Your First Data Credentials

* Log in to your First Data GGe4 Gateway portal and collect the following credentials:
  * Gateway ID
  * Password
  * HMAC Key ID
  * HMAC

### Step 2: Enter Credentials in Recurly

* Log into your Recurly account.
* Navigate to **Configuration** > **Payment Gateways** in your Recurly Admin Console.
* Click on **Add Gateway Account** and select **First Data GGe4** from the dropdown menu.
* Enter your First Data **Gateway ID**, **Password**, **HMAC Key ID**, and **HMAC** into the corresponding fields.

### Step 3: Configure AVS Settings (Optional but Recommended)

* Under the AVS settings section, select your desired AVS matching level:
  * **Full Match Required**
  * **Partial Match Allowed**
  * **No AVS Match Required**
* Save your changes.

### Step 4: Set Up a Read-Only User for Results API

* Follow the guide below on how to set up a read-only user in the First Data GGe4 Gateway portal (explained in detail below).

### Step 5: Test and Verify

* Perform a test transaction to ensure the integration is functioning as expected.
* Monitor and review the transaction status and logs in Recurly.  
  **Please Note:** Be vigilant about updating the 'Results API' credentials, which expire every 60 days. Set a recurring calendar reminder to ensure continuity.

# How to Set Up a Read-Only User for the Results API in First Data GGe4 Gateway

### Step 1: Log Into the First Data Portal

* Access the First Data GGe4 Gateway portal at [First Data Login Portal](https://globalgatewaye4.firstdata.com/?lang=en).

### Step 2: Navigate to User Administration

* Click on the **Administration** tab on the far right of the portal.

### Step 3: Create a New User

* Click the **Create New User** link under the Administration section.

### Step 4: Specify User Details

* Create a username and assign the **Read Only** role under the **Login** tab.

### Step 5: Configure Merchant/Terminal Restrictions

* After creating the user, click on the username.
* Navigate to the **Merchant / Terminal Restrictions** tab.
* Ensure this user has access to the terminals that Recurly uses to initiate transactions on your behalf.

### Step 6: Enter Read-Only User Credentials in Recurly

* Return to your Recurly **Payment Gateway configuration** page and input the **read-only user credentials**.

### Step 7: Regularly Update the Results API Credentials

* Keep in mind that these credentials expire every 60 days, so it is crucial to update them regularly to avoid service interruption.
