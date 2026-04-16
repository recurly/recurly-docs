---
title: Verify billing info
excerpt: >-
  Effortlessly validate and ensure the accuracy of stored customer billing
  information with Recurly's Verify Billing Info feature.
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

### Prerequisites

* Integration with API V3 or V2.
* Use of credit card gateways (non-credit card payment methods are unsupported).

### Limitations

* Only accessible via the API; no Admin functionality currently available.
* Verification is based on your gateway configuration, either as a $1 authorization or ZDA.
* CVV will not be included in the verification due to PCI compliance regulations. To run a verification including CVV, use the billing info verification endpoint that supports CVVs and your customer must be in session to provide the value.
* Verifications are counted as transactions, potentially incurring transaction fees from both Recurly and gateways.

# Definition

Recurly's "Verify Billing Info" feature offers merchants the capability to validate the billing information stored in Recurly's secure credit card vault. This ensures that the customer's payment details remain accurate and up-to-date, facilitating smoother transactions and enhanced customer relations.

# Key benefits

* **Proactive verification**: Actively confirm the validity of stored billing information, reducing payment failures.
* **Enhanced customer targeting**: Identify subsets of customers for targeted marketing campaigns or communications to update billing details.
* **Boosted merchant confidence**: Ensure stored billing information remains accurate, irrespective of its duration in the system.

# Supported functionality

Recurly's Verify Billing Info feature is robust and versatile:

* Initiate a billing info verification for the default stored billing info via API using the account code. This counts as a customer-initiated transaction and could trigger 3DS requests. It's best to have your customer in session in case consumer authentication is required.
* Choose a gateway code to direct verifications through a specific gateway.
* Opt for a $1 or zero-dollar authorization based on gateway configuration settings.
* Obtain billing info verification responses via API, including both successful and declined verifications.

# Supported gateways

Recurly's Verify Billing Info feature is compatible with all Recurly credit card gateway integrations. However, non-credit card gateways such as PayPal Business, Adyen HPP, Adyen ACH, GoCardless, etc., are not supported.

# Implementation guide

### 1. Initiate billing info verification

* **Step 1**: Access your Recurly dashboard.
* **Step 2**: Using API V3 or V2, send a POST request to `/accounts/:account/billing_info/verify`.
* **Step 3**: Ensure the `account_code` is included in your API call.

### 2. Specify gateway (optional)

* **Step 1**: In your API call, optionally include a `gateway_code` to direct the verification through a specific gateway.
* **Step 2**: If the gateway code doesn't support the card type, an error will be returned.

### 3. Receive verification response

* **Step 1**: After submitting the verification request, wait for a response from Recurly.
* **Step 2**: Review  the response to determine if the verification was successful or declined.

# Implementation details

Harness the power of Recurly's Verify Billing Info feature by:

1. Using API V3 or V2, initiate a POST to `/accounts/:account/billing_info/verify`, where `:account` represents the user's account code.
2. Ensure the `account_code` is incorporated in the API call.
3. By default, Recurly will route the stored billing information associated with the provided account code to the default gateway that supports the card type.
4. If a gateway code is specified for the subscription or billing info, the verification will be directed to that particular gateway.
5. Optionally, include a `gateway_code` to channel transactions through a preferred gateway.
6. In case the specified gateway code doesn't support the card type, an error will be generated.
7. Recurly will transmit all stored fields related to the default billing information, potentially including PAN, expiration date, cardholder name, and cardholder billing address.

**Note**: Due to PCI compliance regulations, CVV will not be transmitted.
