---
title: Check Commerce
excerpt: Simplify and secure your ACH payments with Check Commerce through Recurly.
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

This feature **may not be included** in the Starter or Pro plans. If you are interested, please contact [Recurly Sales](https://recurly.com/demo/contact-sales/) to discuss upgrade options.

# Definition

Check Commerce is a payment gateway specifically designed to accept ACH (Automated Clearing House) payments. To process ACH payments, merchants must establish a Check Commerce account via Recurly.

> **Note**: Visit our [guide on testing your gateway configurations ](https://docs.recurly.com/docs/how-to-test-your-gateway)in Recurly to ensure your payment processes are set up correctly.

# Key details

| Feature                         | Description                     |
| ------------------------------- | ------------------------------- |
| Services that work with Recurly | ACH Payments                    |
| Supported Operations            | Transaction Processing, Refunds |
| Supported Payment Types         | ACH (Automated Clearing House)  |
| Supported Card Brands           | N/A                             |
| Gateway Specific 3DS2 Supported | N/A                             |
| Card on File Supported          | N/A                             |
| Regions                         | United States                   |
| Currencies                      | USD                             |

# Eligibility criteria

* Merchants must be located in the United States to apply.
* Merchants must have a late failure rate of 0.5% or lower.
* Standard Check Commerce accounts are limited to $5,000/transaction, but merchants may be approved for higher limits on a case by case basis.
* If approved for a higher limit, you will receive two Check Commerce accounts: one for transactions of $5,000 or less and one for transactions exceeding $5,000.

# Required application documents

To apply for a Check Commerce account, you will need:

* A voided check
* A Valid US Driver's license
* Articles of incorporation
* Screenshots of your checkout flow with the required disclaimers
* Additional requirements apply if the merchant has one or more Principal Business Owners based in Canada (e.g. copy of Principal's passport)

## Apply for an Account

1. **Start the Application Process**\
   Log into Recurly and visit the **Payment Gateways** page.
2. **Select Check Commerce**\
   Click on the "Add a New Gateway" button at the top right of the **Payment Gateways** page, then select the **Check Commerce** option at the bottom.
3. **Confirm Eligibility**\
   If your Site Settings country is not in the United States, you will not see the Check Commerce option and will not be able to use this payment gateway.
4. **Request an Account**\
   If you do not already have a Check Commerce account, once you have selected Check Commerce, click the "Request an Account" button at the right of the page. You will be redirected to Check Commerce's online application for a new account.\
   Do not change the Referral Partner ID on this page to avoid delays in account setup.

## Connect your Account to Recurly

1. **Confirm Your Recurly Plan and Status**\
   Ensure that you have subscribed to Recurly's Elite plan and have moved into production mode.
2. **Enter Credentials**\
   Visit the **Payment Gateways** page in your Recurly Admin and click "Enter Credentials" next to your Check Commerce application status.
3. **Provide Check Commerce Credentials**\
   Enter your Check Commerce Merchant ID/Account Number (a numeric string) and Password.
4. **Gateway Failover**\
   Select whether or not you wish to include this instance of [Check Commerce in gateway failover logic](https://docs.recurly.com/docs/gateway-failover).
5. **Consumer or Business Customers**\
   Choose which type of customers you service with this Check Commerce account.\
   Choose Individual accounts if you primarily work with end-consumers with personal checking accounts.\
   Choose Business accounts if your primary customer is a B2B/Business entity.
6. **Enable Check Commerce**\
   Ensure Check Commerce is set to 'Enabled’ for new transactions when you are ready.
7. **Add Payment Gateway**\
   Click "Add Payment Gateway".
8. **Confirm Activation**\
   After completing these steps, you will see that Check Commerce has been added to our list of Production Gateways with a status of enabled.
