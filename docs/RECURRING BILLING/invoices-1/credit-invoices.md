---
title: Credit invoices
excerpt: >-
  Elevate your billing experience with Recurly's Credit Invoice feature.
  Streamline your credit adjustments, ensure clarity in financial records, and
  enhance customer satisfaction.
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

Recurly's Credit Invoice is a specialized feature designed to separate credit adjustments from charge adjustments. This ensures that any credit issued to a customer is provided its own distinct invoice, offering clear financial records for both businesses and their customers.

# Key benefits

* **Clear financial records:** Maintain distinct and separate records for credits, ensuring accuracy in financial reporting.
* **Enhanced customer understanding:** Provide customers with straightforward invoices, reducing confusion and potential disputes.
* **Tax compliance support:** By separating issued credits from charges, businesses can better support tax compliance requirements.
* **Streamlined operations:** Automate the process of issuing credit invoices, saving time and reducing manual errors.

# Key details

## Understanding credit invoices

Recurly's credit invoice is akin to a credit memo or note. With Credit Invoices, any credit given to a customer gets its own invoice. This separation offers clarity for financial reporting, aids in tax compliance, and makes invoices more transparent for customers. 

Credit invoices can be categorized into three types: credit, refund and write-off.

### 1. **Credit**

This type doesn't link to any specific charges or invoices and is often a custom or promotional credit. Such credits don't reverse discounts or taxes since they aren't tied to any charges. When issued, a New Credit Invoice email is sent to the customer.

<Image align="center" width="80% " src="https://files.readme.io/7a0ef3b-closed-credit-invoice.png" />

### 2. **Refund**

This type reverses previously issued charges. It's generated when a subscription changes immediately with prorated credits or when an invoice is refunded. Emails sent depend on the event causing the refund.

Refund Invoices will use the billing and shipping information from the original invoice even if the current address has been updated.

> **Avoid Over Crediting with Recurly**
>
> Recurly ensures credits issued against a charge don't exceed the original charge amount. This prevents scenarios where, for instance, a subscription downgrade follows a refund, resulting in double crediting.

<Image align="center" width="80% " src="https://files.readme.io/263e692-refund-with-discounts-and-tax.png" />

### 3. **Write-off**

This type offsets charges on a corresponding failed invoice. Activating the Credit Invoices feature means a failed invoice will always be paired with a write-off credit invoice to balance it out.

<Image align="center" width="80% " src="https://files.readme.io/c959776-write-off-invoice.png" />

<Image align="center" width="80% " src="https://files.readme.io/d34d120-failed-invoice.png" />

## Navigating credit payments

When a credit invoice's balance pays off a charge invoice, a credit payment records the amount that reduced both balances. These payments can be seen on the invoice and exported for a detailed audit trail.

<Image align="center" width="80% " src="https://files.readme.io/2dfa6c3-charge-invoice-with-credit-payment.png" />

### Credit payment actions

Credit payment actions in Recurly track the application or removal of credit balances. This includes using an open credit balance for a charge invoice payment, recording balance write-offs, removing credit balances, and refunding a credit payment as a cash transaction. These actions can be viewed in the Credit Payments export or via the API.

## Enhanced invoice origins

The **origin** attribute at the invoice level  indicates the event that led to the invoice's creation, aiding in understanding its context and offering valuable insights for reporting. The origin of each invoice can be viewed on the Invoice Details page, used as a filter on the Invoices Index page, and is available in exports, the API, and webhooks.

> **Note:** In some exports, this attribute is referred to as **invoice\_type**.
>
> Below are the possible origins for invoices, along with their respective codes and descriptions:

| Origin Display           | Origin Code                | Description                                                                                                                                                              |
| ------------------------ | -------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Purchase                 | purchase                   | A charge invoice from a subscription purchase or one-time purchase, including gift card purchases. Legacy invoices not related to refunds also fall under this origin.   |
| Renewal                  | renewal                    | A charge invoice from a subscription renewal, applicable at each billing cycle.                                                                                          |
| Immediate Change         | immediate\_change          | A charge or credit invoice issued for an immediate subscription change.                                                                                                  |
| Termination              | termination                | A credit invoice for a refund during subscription termination, or a charge invoice for final usage-based billing in termination.                                         |
| Refund                   | refund                     | A credit invoice created from directly refunding a charge invoice.                                                                                                       |
| Posted Credit            | credit                     | A custom credit invoice not linked to a specific charge invoice.                                                                                                         |
| Gift Card Redemption     | gift\_card                 | A credit invoice for redeeming a Recurly or external gift card. Note: Gift card purchases are categorized as "purchase."                                                 |
| Write-Off                | write\_off                 | A credit invoice for writing off a failed charge invoice as bad debt.                                                                                                    |
| Prepayment               | prepayment                 | A charge invoice for a specific dollar amount and a corresponding credit invoice for an equivalent credit amount.                                                        |
| External Refund          | external\_refund           | A credit invoice due to a chargeback from the Check Commerce ACH gateway.                                                                                                |
| Carryforward Credit      | carryforward\_credit       | A credit invoice for transferring carryforward credits to the new format upon enabling Credit Invoices. Represents previously issued credits.                            |
| Carryforward Gift Credit | carryforward\_gift\_credit | Similar to carryforward credit, but specific to transferring gift card credits to the new format.                                                                        |
| Usage Correction         | usage\_correction          | A credit invoice for correcting net-negative usage in usage-based add-ons.                                                                                               |
| Line Item Refund         | line\_item\_refund         | A credit invoice for refunding specific line items on a legacy invoice. Supported types of refunds for individual line items are quantity, specific amount, and quantity |
| Open Amount Refund       | open\_amount\_refund       | A credit invoice for refunding a specific dollar amount on a legacy invoice.                                                                                             |

## Streamlined subscription changes

Immediate subscription changes, whether downgrades or upgrades, separate credits from charges. This means a single subscription change can result in a charge invoice, a credit invoice, or both. For instance, if a subscription changes from a Silver to Gold plan, a credit invoice will be issued for the Silver credit, and a separate charge invoice will be issued for the Gold charge. Despite the issuance of two invoices, only one Subscription Change email will be sent to the customer. If PDFs are attached to your Recurly emails, the customer will receive two invoice PDFs - one for the credit and another for the charge.

## Standalone credit invoices

Credits can be issued on their standalone credit invoice.\
To issue a one-off credit invoice via the Recurly Admin Console:

1. Navigate to the customer's account.
2. Click on **Add Credit**.
3. You'll notice new options:
   * **Note to Customer**: Add a message for your customer to the credit invoice.
   * **Reason Code**: Categorize the credit as general, service, or promotional to track its purpose.
   * **Add Another Credit Adjustment**: Define multiple credit adjustments at once.
   * **Account Note**: Add an internal note to the account before finalizing the invoice.
   * Preview the credit invoice or post it directly to the account.\
     Uninvoiced credit adjustments can be created on the account via our API. Custom credits made through the Adjustments endpoint won't be invoiced immediately. They must be invoiced via the API or will be invoiced automatically during the next billing event. Uninvoiced credits won't be applied to charge invoices until they've been invoiced.

## Refund capabilities

Refunding an invoice creates a refund credit invoice with credit adjustments. If the original invoice was paid with credit, the refunded credit will transfer as part of the credit balance on the issued refund credit invoice.\
For example, if an original invoice was $100, paid with $20 of credit payment and an $80 credit card transaction, refunding the entire invoice to credit will result in a refund credit invoice with:

* Total of ($100)
* No refund transactions
* Credit Balance of ($100)

### Advanced refund options

Refunding an invoice now offers more flexibility:

#### **1. Prorated refund**:

If you issue a prorated refund, you can later refund the remaining amount of the original invoice. This option is available for refund credit invoices issued after the Credit Invoices feature was enabled. Legacy refund invoices won't have this option.

#### **2. Refund to credit balance**:

Instead of refunding to the original payment method, you can now opt to refund to the customer's credit balance. This is useful if the customer will have future purchases, as the balance will automatically be used as payment.

<Image align="center" width="50% " src="https://files.readme.io/d5ccf16-refund-to-credit.png" />

#### **3. Refund credit payment to original payment method**

If an invoice was paid with a credit payment, and that credit payment came from a refundable transaction, the credit payment can be refunded as a transaction. This ensures a clean audit trail of transactions.

<Image align="center" className="border" width="50% " border={true} src="https://files.readme.io/d414de3-refund-back-to-cash.png" />

#### **4. Handling Failed Refunds**:

If a refund transaction declines, Recurly will, by default, create a refund credit invoice and retain the transaction amount as part of the credit balance on the invoice. However, you can also choose to block all declined refunds, retry the refund transaction, record an external refund transaction, or void the credit invoice, depending on the specific scenario and your business needs.

These enhanced refund capabilities ensure that businesses have the flexibility and control they need when managing customer refunds, making the process more streamlined and customer-friendly.

## Write-offs explained

When a charge invoice either fails directly or at the culmination of the dunning cycle, a corresponding write-off credit invoice is generated. This invoice zeroes out the balance of the failed invoice by creating credit adjustments that mirror the charges on the failed invoice, including descriptions, taxes, and discounts. These adjustments are tagged with a credit reason code of **write\_off**. The credit invoice itself will also have an origin of **write\_off** for easy identification.

Upon creation, the write-off invoice's balance is immediately applied to the final invoice through a credit payment labeled **write\_off**. This ensures the write-off credit invoice is closed instantly upon collection.

Legacy invoices (those created before the Credit Invoices feature was enabled) won't generate a write-off credit invoice when failed.

After enabling the Credit Invoices feature, manually collected failed invoices can't be reopened. However, manually collected paid invoices can still be reopened.

> **Note:** Failing an invoice with a credit payment will void the credit payment and reopen the originating credit invoice. This action triggers an account activity notification and a webhook alert.

## Voiding credit invoices or balances

Mistakes happen. Sometimes a credit is issued erroneously. While credits can't be deleted anymore, their balance can be voided, ensuring an audit trail remains.

* **Full credit invoice voiding**: If a credit invoice retains its full balance (meaning no credit payments or refund transactions have reduced it), the entire credit invoice can be voided. This action shifts the invoice to a **voided** state. The credit balance is removed by generating a credit payment labeled **reduction**.

<Image align="center" width="80% " src="https://files.readme.io/68e7e9f-voided-credit.png" />

* **Partial Credit Balance Voiding**: If only a portion of the credit invoice's balance remains, the entire invoice can't be voided. However, the remaining credit balance can be. This action creates a credit payment labeled **reduction** for the remaining balance, closing the credit invoice.

To track removed credit balances, use the Credit Payments export and filter by the **reduction** action.

## Credit limitations

To maintain clean accounting and ensure accurate reversal of discounts and taxes on credits, Recurly associates each credit with its originating charge. This ensures the total of all credits never surpasses the charge they're against. 

## Tax implications on credit invoices

Refund and write-off credit invoices will reverse taxes if the original charge invoice collected them. However, one-off credit invoices won't reverse taxes since they aren't linked to specific charges.

For those using the Avalara AvaTax integration, Recurly will commit every credit invoice upon issuance. If a credit balance is voided, Recurly will void the committed document in AvaTax. However, if the credit invoice's balance is removed but the invoice remains closed (not voided), Recurly won't void the committed document in AvaTax.

For EU-based transactions, credit invoices won't display VAT Reverse Charge Notes if the original invoice was a reverse charge. The credit invoice will reference the original invoice, which contains the VAT Reverse Charge Notes.

## Email template updates

The Credit Invoices feature introduces changes to email templates:

### Payment confirmation

This email will now be dispatched when a charge invoice is fully settled with a credit payment.

### Payment refunded

This email will be sent when a refund is entirely credited to a credit balance.

### Subscription change

This email will be dispatched immediately upon request. If an immediate subscription change results in both charges and credits and your site supports PDF attachments, the email will include two PDF attachments: one for the credit invoice and another for the charge invoice.

### Credit Invoice email template

Credit Invoice emails are dispatched whenever a one-off credit invoice is issued. This doesn't apply to write-off credits, refunds, or subscription change credits. Consider customizing this template to fit your needs.

> **Note:** Recurly sites established after May 8, 2018 UTC (May 7, 2018 5pm PT) will have the Credit Invoices feature enabled by default. If you have a site established before May 8, 2018 and never activated credit invoices, read through these directions.
