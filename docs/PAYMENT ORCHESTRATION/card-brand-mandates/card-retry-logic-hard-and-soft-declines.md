---
title: Card Retry Logic - Hard and Soft Declines
excerpt: >-
  Card Brand requirements and restrictions for retrying card payments when they
  decline.
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# What is a Decline and why is it hard or soft?

Credit Card payment declines can occur for a variety of reasons, and include anything from insufficient funds to stolen card fraud. The card networks, like Visa and MasterCard, have rules and reasons behind each type of decline, and some of these reasons are listed as 'soft' and 'hard'.

# What is a "soft" decline

A "soft" decline means that the decline reason is "fixable", and that the payment can be reattempted at a later time. For example, Insufficient Funds is a fixable problem when it comes to a credit or debit card payment. The consumer would need to make funds available in order to complete the payment.

Once funds are available, the payment can be reattempted without causing compliance issues with the credit card networks. However, there are limits to retrying a payment in the recurring space. See below for more information on retry limitations.

# What is a "hard" decline

A "hard" decline means that the decline reason is not generally "fixable", and that the payment should not be retried. These reasons can include fraud, account closures, or even the consumer blocking a merchant from re-authorizing their card.

Visa has a list of decline reasons and categorizes them in levels. For example, a Category 1 Visa Decline Code is always going to be a hard decline and should not be retried.

MasterCard uses a different method: Merchant Advice Codes. Merchant Advice Codes, or MAC for short, are also a list of MasterCard specific codes that should not be retried for recurring or one-time transactions. Certain codes can infer retry-friendly transactions if new card data is provided via Account Updater or the customer updating their billing information.

Recurly works hard to maintain compliance for our customers to avoid fines associated with retry abuse and card network retry limitations.

# What kind of declines can be retried and how often?

Only "soft" declines (Insufficient Funds, as an example) can be retried (without Network fee risk). Visa and Mastercard have different guidelines on the frequency of retries, please see below.

## Visa Retry Limitations

Visa allows re-attempts against _soft_ declined transactions up to **15 times within a 30 day period**. In other words, after an initial decline, Recurly can and will retry the transaction up to 15 times before ceasing attempts.

## MasterCard Retry Limitations

MasterCard is a bit more complicated. MasterCard instructs merchants not to retry a transaction for 24 hours when the payment has resulted in 10 declines. After that 24 hour period, retries can resume _but_ must abide by these restrictions:

* No more than 35 failed attempts on the same card / same merchant in a 30 day period
* No more than 7 retries in a single day

## General Retry Limitations

The system will cease attempts in other scenarios as well:

* A retry results in an approval. No further retries will be attempted after an approval.
* A hard decline is returned by the gateway. If the response from the gateway _changes_ from a soft to a hard decline (for example, if the customer closed their account within the retry period), then Recurly will no longer attempt a payment against this card.
* The Invoice is manually closed or the subscription expired. In this case, Recurly will no longer attempt to recover payments.
* The billing information is updated. If the card being retried is updated, we will no longer attempt to recover funds from the previous payment method.

## Network Advice Codes

### MasterCard Merchant Advice Codes

Mastercard Merchant Advice Codes (MACs) are alphanumeric codes used by Mastercard to provide merchants with more specific details about why a transaction was declined. They go beyond basic decline codes, offering guidance on whether to retry the transaction, when to retry, or why the card was declined in the first place.

See below for Recurly's behavior when each individual code is received on supported gateways. Please note, not all gateways return this detail, and some gateways require the MAC code detail response to be enabled at the gateway, such as WorldPay.

| Advice Code | Description                                                   | Behavior                                                                                                         |
| :---------- | :------------------------------------------------------------ | :--------------------------------------------------------------------------------------------------------------- |
| 01          | New Account Information Available                             | Invoice will not retry unless Billing Info is updated manually or via Account Updater                            |
| 02          | Try Again Later                                               | Invoice queued for retry                                                                                         |
| 03          | Do Not Try Again                                              | Invoice will not retry unless Billing Info is updated manually or via Account Updater                            |
| 04          | Technical issue with the payment                              | Invoice will not retry unless Billing Info is updated manually or via Account Updater                            |
| 21          | Do Not Honor, Consumer cancelled recurring agreement          | Invoice will not retry unless Billing Info is updated manually or via Account Updater                            |
| 22          | Transaction Not Allowed for Merchant                          | Invoice will not retry unless Billing Info is updated manually or via Account Updater                            |
| 24          | Insufficient Funds, Retry after 1 Hour                        | Invoice queued for retry, delayed by 1 hour                                                                      |
| 25          | Insufficient Funds,Retry after 1 day                          | Invoice queued for retry, delayed by 1 day                                                                       |
| 26          | Insufficient Funds,Retry after 2 Days                         | Invoice queued for retry, delayed by 2 days                                                                      |
| 27          | Insufficient Funds,Retry after 4 days                         | Invoice queued for retry, delayed by 4 days                                                                      |
| 28          | Insufficient Funds,Retry after 6 days                         | Invoice queued for retry, delayed by 6 days                                                                      |
| 29          | Insufficient Funds,Retry after 8 days                         | Invoice queued for retry, delayed by 8 days                                                                      |
| 30          | Insufficient Funds,Retry after 10 days                        | Invoice queued for retry, delayed by 10 days                                                                     |
| 40          | Non-reloadable Prepaid Card                                   | Can occur on approvals or declines. Invoice will not retry unless Billing Info is updated manually.              |
| 41          | Non-reloadable Prepaid Card                                   | Can occur on approvals or declines. Invoice will not retry unless Billing Info is updated manually.              |
| 42          | Mastercard refused this transaction due to a sanctions match. | Invoice will not retry unless Billing Info is updated manually or via Account Updater                            |
| 43          | Consumer used a multi-use virtual card.                       | Can occur on approvals or declines. If declined, Invoice will not retry unless Billing Info is updated manually. |
