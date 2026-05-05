---
title: Dynamic Transaction Statement Descriptor guide
excerpt: >-
  Customize your transaction descriptors on one-time and subscription
  transactions using the Recurly V3 API.
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

This guide shows you how to use the Purchase, Subscription, Subscription Update, and certain Invoice endpoints to customize customer-facing statement descriptors using the Recurly V3 API.

### Prerequisites

* Familiarity with Recurly’s V3 API and basic REST concepts
* You are using a Supported Gateway: Adyen, Braintree, Stripe, Commerce Hub, Cybersource, FreedomPay, Checkout.com, and Nuvei
* You have discussed your descriptor suffix and DBA with your Acquirer and agreed upon prior to implementation. Some acquirers require notification prior to descriptor changes.

### Key Benefits

Statement descriptors are an incredible important piece of payment processing, as it is what customers see on their bank statements when transactions are created. Visa and other networks have programs that rely on descriptors to ensure merchants comply with chargeback and risk assessment, for example the VAMP program.

* **Chargeback reduction:** Having a descriptive, coherent statement descriptor can dramatically reduce chargeback behavior by ensuring customers see a recognizable business name or product on their bank statements.
* **Card Brand Compliance**: Ensure, for subscriptions, that the statement descriptor is consistent throughout the lifetime of a consumer's subscription.
* **Multi-gateway Support:** Recurly supports dynamic descriptors on our major gateway partners, ensuring consistency across the entire platform.

***

# Definition

**Creating Purchases** refers to the process of generating new customer accounts alongside subscriptions or one-time payment in a single, consolidated call to the Recurly Purchase endpoint. This streamlines checkout experiences by bundling all required resources into one request.

**Soft Descriptor** refers to the malleable descriptor Recurly will send to the gateway, and the gateway will pass onto your processing partner for display on a customer's bank statement. Depending on the bank / issuer, this descriptor may only be visible while the transaction is in a pending state.

**Hard Descriptor** refers to the final state of a descriptor on a customer's bank statement once the transaction is fully settled. Recurly and our partner gateways have no control over what displays at this stage of the payment lifecycle.

**Static Descriptor** refers to the gateway or acquirer level default that will be used in the event descriptors are not used or sent by Recurly for a given gateway or transaction. This will usually only reference your business name and not include specific product or subscription information.

**Business Entity** refers to your Business Entity or Entities that you set up within your Recurly site environment.

**Descriptor Suffix** refers to the dynamic text you may send in as a merchant that will be visible to consumers. Treat this value with care and consideration.

**Trial Suffix** refers to the Visa Trial Descriptor mandate where Recurly, during a trial conversion, will prefix your suffix with the word TRIAL. You do not need to provide this in your suffix.

**DBA** refers to your consumer-friendly, "recognizable" business name (Doing Business As). You may have a parent company name or a legal business name, but are known to the public by something slightly different, or completely different, depending on your business structure. Ensure you are setting your DBA properly in your business entity or entities if using multiple business entities.

***

## Descriptor Best Practices

Recurly, by default, uses your Subscription Plan names or Invoice descriptions as the descriptor suffix when using our default behavior. You can read more on our dedicated[ Payment Descriptors ](https://docs.recurly.com/recurly-subscriptions/docs/payment-descriptors) info page.

When customizing your suffix, keep these practices in mind:

* The entire string must not breach ~ 22 characters including separators and spaces.
* Do not include the separator in your suffix - Recurly dynamically adds the asterisk separator depending on your gateway's individual requirements.
* Do not include your DBA in your suffix -- set your DBA at the Business Entity level.
* Be "recognizable" -- use DBAs and product descriptions that your customers will know and understand.
* Be simple -- do not write full sentences, or lengthy product names. Remember, you only have 22 characters for your DBA, the required separator, and the suffix combined. **Example**: Acme*Product Name
* Be aware that some gateways require truncation of the DBA to 3, 5, or 7 characters. You may wish to adopt a 3-5 character version of your business name / DBA for this purpose. Check which gateway(s) you are using for specific requirements.
* Make sure you fully fill out your Business Entity information -- some gateways require extra information such as customer service phone numbers, emails, domain names, and MCC codes.

## Integration Examples

When you are creating a subscription and want to customize the suffix, ensure you are submitting your subscriptions with a business entity associated with the transaction so that the information from that business entity (DBA, customer service phone numbers, etc) can be referenced for the subscription specifically. You should also ensure that you are supplying a reasonable and well-thought out descriptor suffix if you plan on customizing the soft descriptor that consumers see on their bank statements.

### Setting Descriptors on Subscriptions

Endpoint: `POST /subscriptions`

```Text JSON
```

### Updating Descriptors on a given Subscription

Endpoint: `PUT /subscriptions/{subscription_id}`

Please note, these fields are not supported in the POST subscriptions change endpoint.

```
```

### Setting Descriptors on One-time Payments

Endpoint: `POST /purchases`and `POST /purchases/authorize`

```Text JSON
```

### Setting Descriptors on a Pending Invoice

Endpoint: `POST /accounts/{account_id}/invoices`and `PUT /invoices/{invoice_id}`

```Text JSON
```

<br />

<br />
