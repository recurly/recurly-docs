---
title: Void
excerpt: Cancel unsettled transactions or credit invoices before settlement in Recurly.
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

Voiding a transaction in Recurly cancels a payment before settlement. A voided transaction is treated as if it never occurred, effectively reversing the pending payment and setting its monetary value to zero. This option is typically available only for **unsettled** transactions.

### Required plan

These features are available to all customers on any Recurly subscription plan.

### Prerequisites & limitations

* **Prerequisites:** Access to **Transactions** or **Invoices** in the Recurly Admin UI.
* **Limitations:**
  * Once a payment has been **voided**, its **value becomes zero**, and it **cannot be refunded** in Recurly.
  * To return funds after a void, issue a **refund externally** (e.g., through your **payment gateway**, **wire transfer**, or **ACH**).
  * You can only void a **credit invoice** if it is not in the states `closed`, `processing`, or `voided`.

# Definition

A void cancels a transaction or credit invoice before settlement. It ensures that no funds move between accounts and that the associated invoice reflects a zero balance.

# Key benefits

* **Immediate cancellation:** Stop unsettled payments before they post.
* **Error correction:** Correct duplicate or mistaken charges on the same day.
* **Accurate reporting:** Track voids easily through Recurly exports.

# Key details

## How to void a transaction

1. **Open** the customer’s account in the Recurly Admin UI.
2. **Go** to the **Transactions** section and **select** the transaction to void.
3. **Review** the transaction details to ensure it is **unsettled**.
4. **Click** **Void transaction** to cancel it.

Once the transaction is voided:

* The transaction's **monetary value is zeroed out** and any pending funds are reversed off the customer's bank statement. This is not always instant -- each bank will have their own timeframe associated with this process.
* The transaction**cannot be refunded** in Recurly or the Gateway.

## Find voided transactions

You can locate voided transactions through the **Transactions export**:

| Column          | Description                                                |
| --------------- | ---------------------------------------------------------- |
| **modified_at** | Displays the date the void took place.                     |
| **invoice_id**  | Identifies the invoice the transaction is associated with. |
| **status**      | Indicates which transactions were voided.                  |

To export:

1. **Go to** **Analytics → Exports** in the Recurly Admin Console.
2. **Download** the **Transactions export** file.
3. **Filter** by `status = Voided` to review all voided transactions.

## Voiding credit invoices via API

To void a credit invoice using the API:

* The invoice must be a **credit invoice** (`type=credit`).
* It cannot be **closed**, **processing**, or **already voided**.

<br />
