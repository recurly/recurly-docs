---
title: SEPA
excerpt: >-
  Discover how to expand your business reach in the European Union (EU) by
  leveraging SEPA Direct Debit through Recurly, a secure and trusted way to
  process one-off or recurring Euro-denominated payments.
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

Recurly currently supports SEPA transactions through [Adyen ](https://docs.recurly.com/docs/adyen)and [GoCardless ](https://docs.recurly.com/docs/gocardless)gateways.

### Limitations

- **Currency:** SEPA exclusively processes transactions denominated in EUR.
- **Customer notification: **Every time a debit occurs, merchants are required to notify their customers — a function automatically handled by Recurly through email notifications.

# Description

SEPA, or Single Euro Payments Area, Direct Debit stands as a vital payment method for merchants aiming to establish or expand their business operations in the European Union. This payment method allows for the processing of both one-time and recurring payments denominated exclusively in Euros (EUR). SEPA requires customers' names and bank account details to be in IBAN (International Bank Account Number) format.

Consistent with the SEPA Direct Debit rulebook, merchants are mandated to notify customers for every account debit, a procedure automatically undertaken by Recurly through email notifications. Find further details on this [here](https://docs.recurly.com/docs/renewal-reminder#sepa-payment-method).

### Use cases

- Recurring Subscriptions: Easily handle subscriptions with recurring payments in EUR.
- One-off Payments: Securely process single payments leveraging the SEPA Direct Debit scheme.

# Checkout flow

#### Customer information collection

Collect essential customer details, including their name and bank account number in IBAN format, during the checkout process to facilitate SEPA Direct Debit transactions.

Recurring SEPA payments can be leveraged even when the first transaction is handled through a different payment method that _does not_ support recurring billing, such as iDeal and Sofort.