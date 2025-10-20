---
title: Void
deprecated: false
hidden: true
metadata:
  robots: index
---
<br />

To void a transaction in Recurly, it's important to note the following:

Once a payment has been voided, the monetary value associated with that transaction is zeroed out. Consequently, you cannot refund a voided payment directly through Recurly.
In such cases, it's recommended to refund the transaction directly through your payment gateway or externally via methods like wire transfer or ACH.
To find voided transactions, you can use the Transactions export. This export contains the following columns:

modified_at: This column displays the date the void took place.
invoice_id: This column identifies the invoice the transaction is associated with.
status: This column indicates which transactions were voided.
You can download the Transactions export from Analytics > Exports in the Recurly Admin Console.

Please note that to void a credit invoice via the API, the invoice must be a credit invoice (type=credit) and cannot be closed (state=closed), processing (state=processing), or already voided.

<br />

<br />
