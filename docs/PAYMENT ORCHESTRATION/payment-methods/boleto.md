---
title: Boleto
excerpt: >-
  Easily integrate Boleto, a leading Brazilian payment method, with Recurly for
  seamless transactions and increased market outreach.
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

### Prerequisites and supported gateways

Recurly currently supports Boleto  transactions through [Adyen](https://docs.recurly.com/docs/adyen#adyen-boleto).

### Limitations

* Every Boleto generation via Recurly results in the creation of a new invoice.
* Boleto is not a recurring payment method. Customers must return to session for every payment.
* Boleto lacks refund capabilities; external refunds are suggested.

# Description

Boleto Bancário, commonly known as Boleto, a popular payment method in Brazil, is usually utilized by individuals without access to bank accounts. Customers are furnished with a Boleto invoice which they can conveniently pay via ATMs, branch facilities, online banking, or retail stores.

# Use cases

1. Ideal for targeting a broader Brazilian customer base, especially those without bank accounts.
2. Suitable for businesses aiming for a flexible payment option in the Brazilian market.
3. Optimal for transactions where immediate payment confirmation isn't vital.

# Checkout flow

When shoppers select Boleto as their desired payment method during checkout:

1. A Boleto invoice, complete with a barcode, is generated for the shopper.
2. The shopper can either view the barcode directly on the checkout page or opt to download the Boleto invoice.
3. Payment for the Boleto invoice can be carried out online or in-store.
4. Upon successful payment of the Boleto invoice, Recurly is alerted through an event, leading to the marking of the invoice as "Paid".
