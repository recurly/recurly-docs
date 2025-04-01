---
title: Credit payments - export
excerpt: >-
  Dive into the world of credit payments with the Credit Payments Export,
  tracking every credit payment action and its details.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Definition

The Credit Payments Export section provides insights into credit payments, encompassing the use of outstanding credit balances to pay invoices. This export not only covers standard credit payments but also records write-offs, credit balance removals, and credit payments subsequently refunded as cash transactions. It becomes visible and populated if you have enabled the [Credit Invoices](https://docs.recurly.com/docs/credit-invoices-release) feature on your Recurly site.

# Filters

### **Action Filter**

The Credit Payments export can be pre-filtered in the Admin Console based on the **Action** taken. The available credit payment actions include:

| **Action**       | **Description**                                                                                                                                                                                                                                                                                                                                      |
| :--------------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| All of the below | All descriptions below.                                                                                                                                                                                                                                                                                                                              |
| Gift Card        | Similar to a normal credit payment, but the credit invoice's amount originates from a "gift\_card." Useful for tracking invoices paid with gift card credit.                                                                                                                                                                                         |
| Payment          | A normal credit payment that utilizes all or a portion of a credit invoice balance to pay a charge invoice.                                                                                                                                                                                                                                          |
| Reduction        | Removes a credit balance from a credit invoice. Use this action to identify all credits "deleted" from an account and check the corresponding original invoice status to see if it resulted in a [voided credit invoice or a closed credit invoice](https://docs.recurly.com/docs/credit-invoices-release#section-void-a-credit-invoice-or-balance). |
| Refund           | Applied when a [credit payment is refunded as a refund transaction](https://docs.recurly.com/docs/credit-invoices-release#section-refund-credit-payment-to-original-payment-method). This event generates a new credit payment that records the original credit payment's ID and the new refund transaction's ID.                                    |
| Write-Off        | Used to transfer the balance of a write-off invoice to a failed invoice, reducing the latter's balance to zero.                                                                                                                                                                                                                                      |

### Date Range Filters

#### **Created**

Lists all credit payments created within the selected timeframe.

#### **Modified**

Lists all credit payments modified during the selected timeframe. A credit payment's modified\_at value is set upon creation and only updates when the credit payment is voided (voided\_at value set) due to the invoice it was applied to being failed.

# Exports table

<HTMLBlock>{`
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Download Button</title>
    <style>
        .download-button {
            display: inline-block;
            padding: 5px 10px;
            text-align: center;
            text-decoration: none;
            color: #1C2833FF; 
            background-color: #F8F8F8FF; 
            border-radius: 5px;
            font-weight: normal;
            transition: background-color 0.5s ease, transform 0.3s ease;
          	transition: 0.4s !important;
            font-family: 'Proxima-nova', Arial, sans-serif;
            max-width: 100%; 
        }

        .download-button:hover {
            background-color: #FFFFFFFF; 
            transform: scale(1.02); 
        }
      	a:hover {
          	color: #1C2833FF;
          	text-decoration: underline !important;
        }
      </style>
</head>
<body>
    <a href="https://docs.google.com/spreadsheets/d/1U0_Wl_NMScJqKBZoBKMmQnybmLEr0gFi6r7dfNiP9Qc/export?format=xlsx" class="download-button">Download our complete export schema</a>
</body>
</html>
`}</HTMLBlock>

To help you identify and organize information effectively, the export provides a structured table that contains the following columns:

| Column Name                                                                    | Example                                            | Description                                                                                                                                                                | Data type (size) |
| :----------------------------------------------------------------------------- | :------------------------------------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :--------------- |
| <span id="id">id</span>                                                        | 41872c1bf4bcfcd5658d86401194f63b                   | The unique id of the credit payment.                                                                                                                                       | varchar(32)      |
| <span id="created_at">created\_at</span>                                       | 2017-12-02 17:58:09 UTC                            | The date and time the credit payment was created.                                                                                                                          | timestamp        |
| <span id="modified_at">modified\_at</span>                                     | 2017-12-02 17:58:09 UTC                            | The date and time the credit payment was modified, which would be when it was created or voided.                                                                           | timestamp        |
| <span id="voided_at">voided\_at</span>                                         | 2017-12-02 17:58:09 UTC                            | The date and time the credit payment was voided due to the applied invoice being failed.                                                                                   | timestamp        |
| <span id="action">action</span>                                                | payment, gift\_card, write\_off, reduction, refund | The action that resulted in the credit payment being created. See action filter table above for details.                                                                   | string           |
| <span id="currency">currency</span>                                            | USD                                                | The currency of the credit payment amount.                                                                                                                                 | varchar(3)       |
| <span id="amount">amount</span>                                                | 54.38                                              | The amount of the credit payment, which will always be positive.                                                                                                           | numeric          |
| <span id="original_invoice_billed_date">original\_invoice\_billed\_date</span> | 2017-12-02 17:58:09 UTC                            | The date the credit invoice the credit payment came from was issued.                                                                                                       | timestamp        |
| <span id="original_invoice_status">original\_invoice\_status</span>            | open, processing, closed, voided                   | The current status of the credit invoice the credit payment came from. This is helpful to identify voided vs. closed credit invoices for reduction action credit payments. | varchar(20)      |
| <span id="original_invoice_number">original\_invoice\_number</span>            | 1008                                               |                                                                                                                                                                            | string           |
| <span id="applied_to_invoice_number">applied\_to\_invoice\_number</span>       | 1005                                               |                                                                                                                                                                            | string           |
| <span id="original_credit_payment_it">original\_credit\_payment\_id</span>     | 775a2e6d1f90f8a8e79c584106b7418d                   |                                                                                                                                                                            | varchar(32)      |
| refund\_transaction\_id                                                        | refund\_transaction\_id                            |                                                                                                                                                                            | varchar(32)      |
| credit\_payment\_api\_id                                                       | e28zov4fw0v2                                       | Credit Payment API ID                                                                                                                                                      | string           |

# Version Changelog

### Version 2 - 2/5/2025

* Addition of `credit_payment_api_id`.