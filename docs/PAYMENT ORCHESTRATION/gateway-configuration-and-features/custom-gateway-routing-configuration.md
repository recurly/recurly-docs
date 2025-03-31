---
title: Custom gateway routing (merchant-initiated)
excerpt: >-
  Navigate the seamless route towards efficient transaction handling with
  Recurly's Custom Gateway Routing. Tailor your financial avenues by directing
  transactions through specified payment gateways, ensuring optimal fund
  management, enhanced acceptance rates, and a bolstered financial reporting
  structure.
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

This feature is only available on advanced plans. If you’re currently on Pro or Starter, you may need to upgrade your plan to access it. Please contact [Recurly Sales](https://recurly.com/demo/contact-sales/) for more information.\
Prerequisites

### Limitations

Merchants should have multiple gateways configured for a particular payment type (e.g., credit cards) within Recurly.\
Limitations

* To follow Card on File Mandates: Depending on the gateways, the information will be packaged in different formats. In most cases, the raw network transaction ID is accepted and recurring transactions will process as usual. In rare cases, the information is not compatible and failover will not occur. 

* When passing the gateway\_code for multiple subscriptions within a single request, routing to different gateways will not be honored.

* If utilizing Stripe, card brands for your gateways are configured directly within the Stripe dashboard. Recurly lacks awareness of the card brands supported by your Stripe account. In cases where certain card brands aren't supported by Stripe but are by other gateways, specifying a gateway\_code is essential to route that particular transaction to another gateway. It's advisable to review your Stripe configuration within the merchant portal to ensure smooth transaction routing.

### Supported payment methods & transactions

#### Supported transactions

* One-time transactions.
* Initial subscription transactions (of subsequent recurring transactions).
* Recurring subscription renewal transactions.

#### Supported payment methods

* [Credit Cards](https://docs.recurly.com/docs/credit-cards)
* [PayPal](https://docs.recurly.com/docs/paypal-payments) (excluding PayPal Complete or PayPal through Braintree Gateway)
* Amazon Pay

# Definition

Custom Gateway Routing is a functionality provided by Recurly that empowers merchants to direct transactions to a specific payment gateway. By designating the gateway, merchants can segregate funds, optimize acceptance rates, and achieve a granular control over transaction routing based on unique business requirements.

# Key benefits

* **Financial reporting efficiency:** Segregate funds by leveraging specific gateway accounts, thus streamlining financial reporting processes.
* **Business-centric routing:** Tailor transaction routes based on various business use cases ensuring a direct control over where transactions are routed.
* **Enhanced acceptance rates:** Optimize acceptance rates by routing transactions through local processors, reducing the chances of cross-border transaction failures.
* **Recurring transaction management:** Easily manage and alter gateway routes for recurring transactions, aligning with subscription renewals and business requirements.

# Key details

## Additional details

This section outlines how the gateway\_code parameter influences the routing of transactions, and how merchants can manage this feature for individual or recurring transactions. Detailed insights into updating, retrieving, and understanding the routing logic based on gateway\_code are provided, ensuring a comprehensive grasp of this feature for effective utilization.

* Passing the gateway\_code in a request to the various API endpoints channels the transaction to the associated gateway. Absence or mismatch of gateway\_code reverts the transaction to the default gateway, with certain exceptions causing transaction failure.
* The gateway\_code persists for recurring transactions, routing subsequent subscription renewals to the specified gateway unless updated.
* Update the gateway\_code through a PUT request using the v2/subscriptions/:uuid/notes or v3 /subscriptions/\{subscription\_id} endpoint, or clear it with an empty tag to revert to standard routing logic.
* Utilize GET requests to /subscriptions to fetch the gateway\_code associated with an account's subscription.
* Use the v2/invoices/\<uuid> or v3 /invoices/\<invoice\_id> endpoint to alter the gateway\_code at the Invoice level, modifying the specified gateway accordingly.
* Unique Recurly gateway instances are essential for routing to different gateways, either through a unique Merchant Account ID / MID or using a different gateway altogether.
* Payment method-specific routing is available. If a gateway\_code sent is incompatible with the payment method, the transaction defaults to the original gateway for that method.
* Applying gateway codes to all subscriptions within a single API request is supported.
* For Aggregate Invoices, consistent gateway\_code across subscriptions on an invoice utilizes that gateway; discrepancies or non-specified codes revert to the default gateway.
* The gateway\_code is exhibited on the transaction detail page, included in the Transaction Export, and is part of webhooks, promoting transparency and traceability.
* Custom Gateway Routing covers a range of Recurly payment methods including Credit Cards, PayPal, Amazon Pay, expanding its utility across diverse payment platforms.

## Standard gateway routing

If no gateway\_code is passed, Recurly will route transactions based on whether there is a ‘Default Gateway’ if that gateway supports the combination of payment method, card type, and currency for the transaction. If the ‘Default Gateway’ does not support the transaction, Recurly will look for other gateways that have been set up by the merchant that match the transaction’s payment method, card type, and currency.

# Setup for custom gateway routing

### Step 1: Obtain the gateway code

* Begin by accessing the gateway configuration page within your Recurly account.
* Here, you'll find a unique `gateway_code` generated by Recurly for each payment gateway you have configured. Make a note of the `gateway_code` for the gateway you wish to route transactions to.

### Step 2: API endpoints configuration

* The Custom Gateway Routing feature can be accessed via two API endpoints: `v2/purchases` and `v3/purchases`.
* If you are using the v3 version, replace the v2 endpoint with the appropriate v3 endpoint based on the setup instructions provided.

### Step 3: Passing the gateway code in API requests

* Incorporate the `gateway_code` parameter in your API requests to the `v2/purchases` endpoint. This parameter should be passed at the root level of your request.

### Step 4: Utilizing supported client libraries

* The Custom Gateway Routing feature is supported across all Recurly-provided client libraries. Ensure you are utilizing a supported library to take advantage of this feature.

### Step 5: Reviewing the setup

* Once you've configured the Custom Gateway Routing feature, you can visit the gateway configuration page in Recurly to view a list of all the gateways along with their unique `gateway_code`. 

### Step 6: Testing

* To ensure that the setup works as expected, conduct a few test transactions.
* Monitor the routing of these transactions to verify that they are being directed to the specified gateway as per the `gateway_code` passed in the API requests.

By following these steps, you will have successfully set up and tested the Custom Gateway Routing feature in your Recurly account, directing transactions to the desired payment gateway.