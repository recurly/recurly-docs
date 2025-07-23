---
title: CardConnect
excerpt: >-
  Seamlessly integrate and manage your CardConnect Payment Gateway through
  Recurly for efficient and secure credit card transactions.
deprecated: false
hidden: true
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

* Check CardConnect / [CardPointe's list of prohibited businesses](https://support.cardpointe.com/assets/support/assets/Wells-Fargo-US-RISO-Agent-ISV-Unqualified-List-062422.01962.pdf) if you do not yet have an account.

# Definition

CardConnect is a payment gateway that enables merchants in the US and Canada to process credit card transactions. You can sign up for a merchant account through Recurly who can offer an exclusive rate on processing services. 

> **Note**: Visit our [guide on testing your gateway configurations ](https://docs.recurly.com/docs/how-to-test-your-gateway)in Recurly to ensure your payment processes are set up correctly.

# Key details

| Field                           | Description                                                                                                |
| ------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| Services that work with Recurly | Purchase, Recurring Transactions                                                                           |
| Supported Operations            | Authorize & Capture, Purchase, Recurring Payments, Refund, Verify, Void                                    |
| Supported Payment Types         | Credit Card Transactions                                                                                   |
| Supported Card Brands           | Visa, Mastercard, American Express, Discover, JCB, Diners Club                                             |
| Gateway Specific 3DS2 Supported | N/A                                                                                                        |
| Card on File Supported          | Yes                                                                                                        |
| Regions                         | US, Canada                                                                                                 |
| Currencies                      | See <a href="https://docs.recurly.com/docs/currency-support-by-gateway" target="_blank">all available.</a> |

## Integration notes

* Initially, closing your day's transaction batch is set to automatic, but you can adjust this according to your business needs.
* Chargebacks can be managed and viewed within the CardPointe application, with customizable notifications and support from Fiserv's chargeback support.
* The integration with CardConnect supports the [Auth and Capture](https://docs.recurly.com/docs/auth-and-capture) transaction flow, allowing for robust and secure credit card transactions.

## Merchant account application

CardConnect processes your merchant application rapidly—with a minimum of a 4-hour turnaround and a 75% rate of automatic approval. If additional review is necessary, you will be contacted within 24 hours. Keep an eye on your inbox for updates from CardConnect regarding your application status.

## Merchant account support

If you have questions or need support related to your CardConnect merchant account:

* For existing CardConnect accounts: If you want to use this account with Recurly, reach out to your CardConnect representative to update your account information.
* To delete a CardConnect account: First, remove the payment gateway from within Recurly, and then contact CardConnect to deactivate or delete your merchant account.
* For general support: Contact CardPointe Support at [cardpointeSupport@cardconnect.com](mailto:cardpointeSupport@cardconnect.com), or call 877-828-0720 (Opt 1, Opt 1), or get assistance through CoPilot merchant ticketing.

# Integration guide

Ensure that you have an active CardConnect account. If you don't have one, follow the steps listed below. If you already have an active CardConnect account, skip to Step 2.

## Step 1: Applying for a CardConnect Merchant Account via Recurly

1. **Access the CardConnect Application Link**
   * From the 'Add CardConnect Gateway' page in Recurly, follow the link to CardConnect’s Hosted Application Page.
2. **Complete the Merchant Application**
   * Fill out the application form with your business details.
3. **Submit Your Application**
   * Review your information and submit the application.
4. **Monitor Your Email**
   * Check your email for updates on the application status from CardConnect.

## Step 2: Configuring CardConnect in Recurly

1. **Login to Your Recurly Account**
   * Log in to your Recurly dashboard.
2. **Navigate to Payment Gateway Settings**
   * Go to **Configuration→Payment Gateways**.
3. **Select CardConnect Gateway**
   * Choose ‘CardConnect’ from the list of available payment gateways.
4. **Enter CardConnect Credentials**
   * Input the following information as provided by CardConnect:
     * Username
     * Password
5. **Enable Supported Card Brands**
   * Specify which card brands you want to support.
6. **Enable Accepted Currencies**

* In the Acceptance Currencies section, use the dropdown menu in the left section under Available Currencies and add all currencies associated with your CardConnect account(s).
* In the same Accepted Currencies section, to the right, enter your CardConnect Merchant ID associated with each selected currency under Merchant IDs for Selected Currencies’.

7. If your CardConnect Account is set up to accept Zero Dollar Authorizations, select which card types are authorized under ‘Zero Dollar Authorizations (Advanced)’.
8. **Enable the Gateway for New Transactions**
   * Select the radio button labeled 'Enabled’ when you are ready to go live.
9. **Save Your Settings**
   * Click on ‘Add Payment Gateway’ to finalize the setup.

## Step 3: Merchant Account Support and Maintenance

1. **Modify Existing CardConnect Account (if needed)**
   * If you have an existing merchant account with CardConnect and would like to use this account with Recurly, please contact your CardConnect representative to modify your account information.
2. **Deleting Your CardConnect Account (if needed)**
   * To delete a CardConnect account, first remove the payment gateway from within Recurly, and then contact CardConnect to inactivate or delete your merchant account.
3. **CardConnect Support**
   * For additional support, contact CardPointe Support at [cardpointeSupport@cardconnect.com](mailto:cardpointeSupport@cardconnect.com), or call 877-828-0720 (Opt 1, Opt 1).
