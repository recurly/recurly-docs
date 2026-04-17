---
title: Payment descriptors
excerpt: >-
  Ensure seamless payment processing by using default dynamic payment
  descriptors with your gateway. Ensure your plans and invoice descriptions are
  set up properly for bank statements.
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

### Required plan

This feature or setting is available to all customers on any Recurly subscription plan.

### Prerequisites

* We support trial descriptors on all gateways that support cards. Visa Trial descriptors function by adding the word 'Trial' to any Visa transaction that is converting after a trial period ends.
* We support descriptors beyond Visa trial descriptors on the following gateways with the enablement of a feature flag. Reach out to Recurly Support or your account manager to have the related feature flag enabled:
  * [Stripe](https://docs.recurly.com/recurly-subscriptions/docs/stripe#/)
  * [Braintree](https://docs.recurly.com/recurly-subscriptions/docs/braintree-rd#/)
* Dynamic Descriptors (derived) are also supported without flagging on the following gateways:
  * [Commerce Hub](https://docs.recurly.com/recurly-subscriptions/docs/commerce-hub)
  * [Freedom Pay](https://docs.recurly.com/recurly-subscriptions/docs/freedompay)
  * [Checkout.com ](https://docs.recurly.com/recurly-subscriptions/docs/checkoutcom)
  * [Nuvei](https://docs.recurly.com/recurly-subscriptions/docs/nuvei)

### Limitations

* Modifying descriptors is not possible via the API outside of sending in a unique invoice description.

* Modifying your descriptor Prefix is not available on **Stripe**. This must be done at the Gateway.

* **Braintree** prefixes must be 3, 7, or 12 characters, and may be modified from your set DBA.

* **Braintree** support is limited to cards and PayPal.

* If utilizing **Stripe**, your merchant prefix is configured directly within Stripe and cannot be modified via descriptors within Recurly. Only the suffix (Plan Name or Invoice Description) is sent to Stripe.

* While Recurly can send dynamic descriptors to a given gateway, Gateways may not pass descriptors on to the network as well as Issuers have final say on descriptor support. Reach out to your gateway to inquire about their descriptor support for your merchant account specifically.

* Currently, only the Default Business Entity information is used for Prefix information. Dynamic Business Entity usage is planned.

# Definition

A dynamic descriptor, also known as a soft descriptor, is a customizable piece of information that can be included with a credit card transaction and appears on the customer's bank statement, allowing merchants to provide specific details about the transaction beyond just their business name.

Dynamic descriptors assist customers in recognizing their purchases with your business and avoiding "friendly" chargebacks due to an unrecognizable charge.

Descriptors are typically limited to 22 characters, and often look like the below. They may or may not include a domain (acme.com) or a phone number. Visibility is dependent on the consumer's bank support for descriptors and the gateway support for data within a given descriptor.

* **DBA*Description of Charge**

On Recurly, we handle descriptors in the following manner:

* For **Subscriptions**, we utilize your business company name or DBA, if present, and the Plan Name for a given subscription to create the descriptor text. If a Trial is converting, we add the word 'Trial' to the descriptor suffix for Visa transactions. **Example**: `AcmeInc*Trial Gold Plan`
* For **One-Time** transactions, we utilize your business company name or DBA, if present, and the Invoice Description for a given invoice to create the descriptor text. **Examples**: `AcmeInc*Charge` or `AcmeInc*One-Time Payment`

### Supported payment methods & transactions

#### Supported transactions

* One-time transactions.
* Initial subscription transactions (of subsequent recurring transactions).
* Recurring subscription renewal transactions.

#### Supported payment methods

* [Credit Cards](https://docs.recurly.com/docs/credit-cards)

# Key benefits

* **Chargeback reduction:** Let customers know on their bank statements who you are and what you're charging them for. This reduces instances of friendly-fraud and chargebacks due to static or vague descriptors.
* **Transparency:** Customers will appreciate knowing that their bank statement is showing them accurate information for their records.
* **Consistency:** Customers will see the same prefix and memorable plan / charge information from your business on their bank statement. If you change your business name, ensure you notify existing customers that they can expect to see this change on their bank statements.

# Key details

## Additional details

This section outlines how dynamic descriptors are created for your site(s) using already present data for subscriptions and one-time transactions.

### Best practices for descriptors

* Ensure you have your known Business Name either in Site Settings (Company Name) **and** a DBA filled in. We will use this information to create descriptors for your supported gateways. Ensure this company name and/or DBA is kept up to date as your business evolves. DBA will be used over your Company name if you wish to further customize descriptor prefixes.
* When naming plans in Recurly, ensure the plan names are something a customer will recognize when viewing their bank statement, especially within the first 22 characters. In other words, ensure the first few words of your Plan Name is recognizable to a consumer.
* When creating one-time Invoices, ensure you add an Invoice Description that a customer will recognize, whether for the purchase or service you are providing to them. Order numbers are great for transparency. In other words, ensure the first few words of your Invoice Description is recognizable to a consumer within a Bank's typical 22 character limitation.
* If you do not supply an Invoice Description on a one-time charge, we will supply the word 'Charge' to fill out the necessary information for a descriptor where supported.
* Ensure you have dynamic descriptors enabled at your given gateway. Some gateways require a setting or flag to be enabled to pass along the data Recurly provides.
