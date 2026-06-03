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

When a customer subscribes to your service, the credit card number or other payment instrument is sent from Recurly through a **payment gateway** to your **merchant account** and on to the **card issuer**, or other institution authorizing the transaction. Once the transaction has been approved, the transaction settles, and the merchant bank (Acquirer) ultimately funds you, the merchant, by transferring funds, minus fees, to your business bank account. If a transaction is declined, an error message is sent back through the system to Recurly with information on why and/or how to proceed. **Please note**, the granularity of the decline message is directly tied to a gateway's decline message availability. Some declines can be generic, and no further information is available to Recurly or the Gateway.


<Image src="https://files.readme.io/393d40568ec94fb48407646431910507180c44cd589216c8591736a64e1ca7f3-transactionflow.png" align="center" />


## Payment Gateways

Credit card and other payments must be submitted through a payment gateway. Payment gateways traditionally serve specific geographies and merchant types, or have specialization in specific payment methods. While most merchants require only one payment gateway, companies operating in multiple geographies may require multiple gateways. It is also important to maintain redundancy by having multiple relationships.

## Merchant Banks

The purpose of your merchant bank is to serve as a ‘buffer’ in the event that transactions are contested via chargebacks. The merchant bank underwrites this risk by assessing fees to each merchant based on the characteristics and risk level of their business.

## How can Recurly help?

Recurly supports [many payment gateways](http://docs.recurly.com/payment-gateways/additional) worldwide as well as a variety of alternate payment methods. We believe that choice and flexibility help our customers make decisions that are optimal for their unique business requirements.
