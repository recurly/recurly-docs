---
title: Transactions dashboard
excerpt: >-
  Efficiently track and manage your financial transactions with Recurly's
  Transactions Dashboard. Get detailed insights into payments, refunds, and
  billing activities in one convenient place.
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

* Active Recurly account with administrative access.
* Basic understanding of transaction processes and payment gateway functions.

### Limitations

* Inability to reactivate voided transactions.
* Limitations on issuing partial refunds for unsettled transactions.
* Dependence on third-party gateways for transaction settlement times and fraud checks.

# Definition

<Image align="center" border={true} width="70% " src="https://files.readme.io/1e75403-image.png" className="border" />

The Transactions Dashboard in Recurly provides a comprehensive overview of all financial transactions processed through the platform. It includes features for searching transactions, understanding various transaction types, managing refunds and voids, and performing fraud checks, all designed to streamline the financial management of customer accounts.

# Key benefits

* **Comprehensive transaction search**: Easily locate transactions using a wide range of criteria, from customer information to transaction IDs, enhancing tracking efficiency.
* **Streamlined refund and void processes**: Simplify the handling of unsettled and settled transactions, with intuitive options for voids, full, and partial refunds.
* **Enhanced fraud management**: Facilitate safer transactions with built-in features for fraud checks, supplemented by integration with third-party fraud prevention services.

# Key details

The transactions dashboard in Recurly offers a comprehensive view of all your transaction activities. Here, you can effortlessly search for transactions using a variety of criteria, such as the transaction's Universally Unique Identifier (UUID), the customer's first or last name, account code, the last four digits of their card number, card type, payment gateway reference ID, transaction amount, or currency. The available filters help you organize transactions by their type and response, making it simpler to find exactly what you're looking for.

You also have the option to narrow down your search based on the payment gateway and currency used.

## Transaction types

Below is a table describing the various types of transactions you may encounter:

| Transaction   | Description                                                                                                                                     |
| ------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- |
| Verification  | Transactions, usually of $0 or $1, used to verify billing information. These are immediately voided after verification.                         |
| Payment       | Most purchases made through Recurly.                                                                                                            |
| Authorization | An Auth-Only Purchase made through Recurly using the `/purchases/authorize` endpoint.                                                           |
| Capture       | A referenced Transaction to complete an Authorization. Only Authorizations may be captured.                                                     |
| Refund        | Transactions where funds were returned following a successful Recurly transaction. Refunds typically occur post-settlement with your gateway.   |
| Void          | Transactions were funds were returned follow a successful Payment or Authorization prior to settlement (same day). Else, a Refund is submitted. |

## Transaction statuses

This table outlines possible statuses a transaction can have, offering insights into its processing stage or outcome:

| Status     | Description                                                             |
| ---------- | ----------------------------------------------------------------------- |
| Successful | Transactions that have been approved by the payment gateway.            |
| Declined   | Transactions that were not approved by the payment gateway.             |
| Voided     | Transactions that have been cancelled before any exchange of funds.     |
| Fraudulent | Transactions identified as fraudulent.                                  |
| Pending    | Transactions that are awaiting completion or further action.            |
| Scheduled  | Transactions that are set to be processed at a future date.             |
| Processing | Transactions that are currently being processed by the payment gateway. |
| Chargeback | Represents a chargeback on a Card or Bank / Direct Debit payment.       |

## Transaction search

Finding a specific transaction in Recurly is simple and flexible, thanks to a wide range of search fields available.

* **Account Code**: Locate transactions tied to a specific Recurly account code.
* **Company Name**: Search for transactions associated with a company's name.
* **First Name**: Find transactions by the customer's first name.
* **Last Name**: Search transactions using the customer's last name.
* **Email Address**: Locate transactions linked to a specific email address.
* **Username**: Find transactions by the username associated with the customer's account.
* **Amount**: Search for transactions based on the transaction amount.
* **First Six Digits of the Credit Card**: Locate transactions using the first six digits of the customer's credit card. This is helpful for identifying the card issuer and type.
* **Last Four Digits of the Credit Card**: Narrow down transactions with the last four digits of the credit card, offering a quick way to reference a specific payment method.
* **Transaction Reference ID**: Search for transactions using the payment gateway's reference ID.
* **Transaction Unique ID (UUID)**: Locate a transaction with its unique identifier, offering the most direct way to find a specific transaction.

## Creation of a transaction

Transactions in Recurly are automatically generated when an invoice is processed. This can occur as a result of subscription activities (such as creation, renewal, or modification) or from charges created and invoiced on the account. To minimize per-transaction gateway fees and reduce the number of separate bank charges for customers, it is advisable to utilize the [Purchase](https://dev.recurly.com/docs/create-purchase) endpoint for both subscription and one-time charge billings. This endpoint consolidates billing for any combination of subscriptions and one-time charges into a single transaction for your payment gateway.

## Minimum purchase amount

To optimize merchant fees, Recurly does not send transactions below $0.03 to your payment gateway. Instead, such invoices are immediately marked as paid. It's important to note that some payment gateways have their own minimum purchase amounts, typically ranging from $0.30 to $0.50.

## Transaction details

When you click on a transaction, you get the following information:

### Transaction details

This includes the transaction type (such as payment, refund, authorization, etc.), status (successful, declined, voided), the transaction amount, and the customer's billing information. Billing information covers card type and address details (if collected).

#### Status details

This section helps you understand the current status of a transaction. If a transaction is declined, you can investigate further to uncover the reason behind the decline or other error-related statuses.

1. **Select** the transaction in question to view its details.
2. **Look for** the gateway error codes or internal error codes provided. These codes offer insights into what went wrong.

For a detailed explanation of each error code, please visit our developers' documentation at <a href="https://recurly.com/developers/pages/api-transaction-errors.html" target="_blank">Recurly API Transaction Errors</a>. This resource provides a comprehensive list of possible errors, helping you diagnose and address any issues more effectively.

### Fraud details

This section provides information about the address and CVV verification checks, as well as 3DS Authentication status where performed by the payment gateway.  For Fraud Velocity Checks and additional fraud prevention measures, we recommend partnering with our third-party fraud providers. Please contact your Account Executive or Account Manager for more information.

AVS / CVV Codes are normalized in Recurly's systems to display not only the code, but a short sentence to explain the Issuer's response. Example, a gateway may return the letter 'A', which means 'Address matches, but the postal code does not match.'. This means that the consumer provided the proper street address, but their zip code is wrong, based on information their Bank has on file. This is not a code Recurly derives.

3DS Status messages are also normalized in Recurly to display the final authentication result, and applicable meta-data related to the authentication event. We may receive all or partial data from a given gateway provider, but will always show the final results: 

* **Authenticated**: the customer successfully authenticated their identity through 3DS.
* **Attempted**: the customer attempted authentication but the upstream 3DS provider was unavailable, or otherwise is not supported for this card. The authentication attempt did not fail or succeed.
* **Failed**: the customer finished authentication, but their input was rejected. This typically means the person attempting to process is not the cardholder. 
* **Exempted**: the customer was exempted from 3DS authentication, meaning the transaction and consumer qualified for Frictionless flow (no challenge), or a number of other exemption options such as a low value exemption, merchants who have low fraud rates (TRA), or merchants who are listed in the consumer's bank app as 'trusted'.
* **Error**: the 3DS server or provider experienced a hard error, and 3DS could not continue.

## Settling transactions

At the time of purchase, your payment gateway verifies the customer's billing information and confirms fund availability through their credit card processors. Upon a successful response, the funds are reserved, and the transaction amount is deducted from the customer's bank account balance. These transactions are finalized at the end of the day when the payment gateway processes them for settlement, resulting in the release of funds to the merchant. The settlement status of a transaction influences how voids, refunds, and partial refunds are handled.

## Verification

When billing information is added or updated on an account, Recurly issues a $1.00 authorization charge (or a $0.00 verification for gateways supporting Zero Dollar Authorizations) to verify the billing information. Recurly voids this charge once a success or decline response is received from the gateway. Subscription plans with trial periods also process a verification charge at signup to confirm the customer's billing data.

## Refunds and voids

> ❗️ **Refunding Direct Debit transactions**
>
> It is recommended to only refund Direct Debit transactions after at least 1 week from the original authorization date to avoid financial losses. Bank transactions are not immediately authorized and can take several days to return from the consumer's bank as insufficient funds or otherwise not successful.
>
> Direct Debit chargebacks are also typically non-defensible and can occur quite a while after the initial payment takes place. Ensure you are offering refunds to KYC'd customers and ensure consumers are aware of bank refund timeframes so they do not _also_ initiate a chargeback which could result in financial losses.

An unsettled transaction can be voided, which stops the transaction from settling and removes it from the customer's bank statement (timing is up to the consumer's individual bank). Once a transaction has settled, it can only be refunded. Since payment gateways have varying processing times for settling transactions, Recurly automatically attempts a void before processing a refund. Note that partial refunds can only be issued on a settled transaction, so it's advisable to wait 24 hours after an initial transaction before attempting a partial refund.

A voided transaction usually disappears from a customer's credit/debit account statement within 24 hours. In contrast, a refund may take 3 to 5 business days to reflect on the statement.

Refunds are always issued to the original payment method (credit card or bank account for ACH payments).

To refund or void a transaction or invoice:

1. **Open** the customer's account and select the desired transaction in the Transactions section or the invoice in the Invoices section.
2. For transactions, **proceed** to the Transaction Details page and click **Refund Transaction**. For invoices, go to the Invoice Details page and click **Refund Invoice**.
3. **Choose** the specific charge line items for refund, with options to prorate subscription charges or select specific quantities. For custom refund amounts, **click** "Refund a partial item or specific amount?" ensuring the amount does not exceed the original transaction value. Unsettled transactions can only be fully refunded (voided).
4. If the invoice includes credit line items and you're doing a partial refund, **choose** to return credit to the account first and then create a transaction for any remaining amount, or **opt** for "Transaction first" to issue money back to the customer before returning any credit. By default, refunds return credit to the account first. Change this preference using the radio buttons at the top of the page.
5. **Click Preview Refund** to review the refund details, including discounts, taxes, and credit being returned.
6. To complete the refund, **click Refund Charges**. This action will generate a refund invoice and transaction.  
   Learn more about invoices for voided and refunded transactions in our [Invoices](/docs/invoices) section.
