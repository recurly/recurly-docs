---
title: Payment gateway & merchant account overview
excerpt: >-
  Recurly enables you to easily process recurring payments. Setting up a Recurly
  account is just the first step – you’ll also need to connect a payment gateway
  and merchant account to be able to accept credit cards.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
## Transaction Flow

When a customer subscribes to your service, the credit card number is sent from Recurly through a **payment gateway** to your **merchant bank account**. Once the transaction has been approved, the merchant bank account ultimately settles the transaction and transfers funds to your business bank account. If declined, a detailed error message is sent back through the system to Recurly.

![601](https://files.readme.io/3XhVM9NSCyhUigQ54EtO_transactionflow.png "transactionflow.png")

## Payment Gateways

Credit card payments must be submitted through a payment gateway. Payment gateways typically serve specific geographies and currency types. While most merchants require only one payment gateway, companies operating in multiple geographies may require multiple gateways.

## Merchant Banks

The purpose of your merchant bank account is to serve as a ‘buffer’ in the event that transactions are contested via chargebacks. The merchant bank underwrites this risk by assessing fees to each merchant based on the characteristics of their business.

## How can Recurly help?

Recurly supports [many payment gateways](http://docs.recurly.com/payment-gateways/additional) worldwide as well as a variety of alternate payment methods. We believe that choice and flexibility help our customers make decisions that are optimal for their unique business requirements.
