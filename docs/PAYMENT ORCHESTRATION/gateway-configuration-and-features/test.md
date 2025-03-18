---
title: Test gateway
excerpt: >-
  Effortlessly test your transaction configurations with Recurly's Test Gateway,
  ensuring seamless live operations.
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

### Prerequisites

* A Recurly account with administrator access.
* Familiarity with the Recurly dashboard and gateway configurations.

### Limitations

* The only supported currencies for this test gateway are USD, AUD, BRL, CAD, CHF, CZK, DKK, EUR, GBP, HUF, ILS, INR, JPY, MXN, NOK, NZD, PLN, SEK, SGD, ZAR.
* Test Gateway transactions are solely for testing and do not represent real monetary transactions.
* Not all real-world error scenarios can be simulated.
* Transaction results in the Test Gateway may not always reflect outcomes in a live gateway setting.

# Definition

The Test Gateway in Recurly offers a simulated environment, letting you test transactions using predefined credit card and bank account numbers. This functionality aids in anticipating and addressing potential issues without affecting real-world operations.

# Key benefits

* **Risk-free testing:** Trial run configurations without the concern of real-world consequences.
* **Diverse scenarios:** Simulate various transaction outcomes, from success to multiple decline reasons.
* **3DS2 ready:** Test the 3DS2 challenge flows without actual cardholder authentication.
* **Comprehensive feedback:** Understand potential issues and troubleshoot with immediate feedback.

# Test credit card numbers

With the Test Gateway activated, various credit card numbers are at your disposal for transaction simulations. Depending on the card number provided, the system will return predefined results.

## Successful transactions

| Card Number         | Outcome                                                                                                                  |
| ------------------- | ------------------------------------------------------------------------------------------------------------------------ |
| 4111-1111-1111-1111 | Success.                                                                                                                 |
| 4222-2222-2222-2220 | Success, but flagged for Fraud Review by the gateway (*Note: Relevant only to PayPal gateways when in production mode.*) |
| 4000000000002024    | Successful purchase with a declined refund.                                                                              |

## Other successful numbers

For further testing, a range of other successful card numbers are available. These span various card types, including American Express, Diners Club, Discover, JCB, MasterCard, and Visa. Note that all these numbers, except the one marked "Invalid credit card number," adhere to the Luhn validation algorithm.

| Card Number      | Card Type                  |
| ---------------- | -------------------------- |
| 378282246310005  | American Express           |
| 371449635398431  | American Express           |
| 378734493671000  | American Express Corporate |
| 30569309025904   | Diners Club                |
| 38520000023237   | Diners Club                |
| 6011000990139424 | Discover                   |
| 3530111333300000 | JCB                        |
| 3566002020360505 | JCB                        |
| 5555555555554444 | MasterCard                 |
| 5105105105105100 | MasterCard                 |
| 2223000048400011 | 2 Series MasterCard        |
| 4012888888881881 | Visa                       |
| 4222222222222    | Visa                       |

## Declined transactions

A series of credit card numbers result in declined transactions. Reasons for decline can vary, and the following are predefined outcomes for specific card numbers:

| Card Number         | Decline Reason                                                                                   |
| ------------------- | ------------------------------------------------------------------------------------------------ |
| 4000-0000-0000-0002 | Declined by the gateway.                                                                         |
| 4000-0000-0000-0010 | AVS failed on street address and postal code.                                                    |
| 4000-0000-0000-0028 | AVS failed on street address.                                                                    |
| 4000-0000-0000-0036 | AVS failed on postal code.                                                                       |
| 4000-0000-0000-0044 | Advanced Verification failed (Secure 3D, etc).                                                   |
| 4000-0000-0000-0051 | Card number declined.                                                                            |
| 4000-0000-0000-0069 | Expired card or expiration date does not match.                                                  |
| 4000-0000-0000-0077 | Insufficient funds.                                                                              |
| 4000-0000-0000-0085 | Did not pass your fraud filters.                                                                 |
| 4000-0000-0000-0093 | Originating from fraudulent IP address.                                                          |
| 4000-0000-0000-1190 | Declined due to a fraud risk score.                                                              |
| 4000-0000-0000-0101 | CVV / Security code did not match.                                                               |
| 4000-0000-0000-0119 | Declined by issuing bank, customer needs to contact their bank.                                  |
| 4000-0000-0000-0200 | Invalid data or parameter.                                                                       |
| 4222-2222-2222-2222 | Invalid card number (Fails the Luhn algorithm check).                                            |
| 4000-0000-0000-0226 | Invalid expiration date.                                                                         |
| 4000-0000-0000-0309 | Gateway Timeout.                                                                                 |
| 4000-0000-0000-0317 | Duplicate transaction.                                                                           |
| 4000-0000-0000-0325 | Card type not accepted.                                                                          |
| 4000-0000-0000-0341 | 'Declined by Gateway' error will be thrown, but Recurly will allow you to store card regardless. |

## 3DS2 Test cards

The test cards listed below should only be used to test the 3DS2 challenge flows. 3DS2 integration steps, and more information on how to use these cards, can be found in our guide [here](https://recurly.com/developers/guides/3ds2.html#3d-secure-20-integration-guide).

| Card Number      | Description                                                                                |
| ---------------- | ------------------------------------------------------------------------------------------ |
| 4000000000003220 | This card will trigger the 3DS2 challenge flow.                                            |
| 4000000000003063 | This card will trigger the device fingerprint flow.                                        |
| 4222222222222220 | This card will trigger an approved transaction requiring fraud review (frictionless flow). |
| 4000008400001629 | This card can be used to test the 3DS2 dunning flow.                                       |

## Test bank account numbers (ACH)

To test ACH, you can add bank account details through the API, the Hosted Account Management pages or using the "Make a Payment" button on the hosted invoice page. You will not be able to add bank account details through the Admin due to NACHA regulations on merchant access to customer account information.

Testing ACH does not test your gateway connection, but uses an internal Recurly test gateway to simulate the transaction responses and invoice states you will get with ACH payments and refunds.

### Routing number

| Routing Number | Description                                                                                                            |
| -------------- | ---------------------------------------------------------------------------------------------------------------------- |
| 123456780      | This is the only routing number that will work in sandbox mode. This routing number will return the "BANK OF RECURLY". |

### Success Bank Account Number

| Account Number | Description |
| -------------- | ----------- |
| 111111111      | Settled     |

### Declined bank account number

| Account Number | Description                                                |
| -------------- | ---------------------------------------------------------- |
| 111111112      | Transaction was canceled by the bank.                      |
| 111111113      | Transaction was canceled by the bank.                      |
| 111111114      | Will first be successful and then will issue a chargeback. |
| 111111115      | If refunded, will be a successful refund.                  |
| 111111116      | If refunded, will be a declined refund.                    |

## Step-by-step-processes

### Accessing the Test Gateway

* Navigate to the "Payment Gateways" section after logging into your Recurly account.
* The Test Gateway is active by default on your Recurly Sandbox.

### Testing with Credit Card Numbers

* Start a transaction using one of the provided test credit card numbers.
* Observe the system's response and act accordingly.

### Testing with Bank Account Numbers (ACH)

* Through the API, Hosted Account Management pages, or the "Make a Payment" option on the hosted invoice page, input a bank account detail.
  > **Note:** Direct input through Admin is restricted due to NACHA regulations.
* Initiate a transaction using one of the provided test bank account numbers.
* Monitor the simulated response.

In conclusion, Recurly’s Test Gateway provides a simulated and safe environment for businesses to ensure their configurations are correctly set up, reducing the likelihood of issues when running live transactions.