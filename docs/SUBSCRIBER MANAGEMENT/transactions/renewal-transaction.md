---
title: Renewal
deprecated: false
hidden: true
metadata:
  robots: index
---
<br />

Subscription renewals in Recurly involve automatically generating a new recurring invoice. For each renewal, Recurly communicates with the payment gateway to initiate a new transaction.

For Boleto, a payment method that doesn't support direct recurring transactions, Recurly automatically generates a new recurring invoice for each renewal, which initially appears as "Past Due" to account for processing time. Recurly then issues a new Boleto invoice for the renewal amount and uses the configured Boleto email template to notify customers with a link to download the invoice. Once the customer pays the Boleto invoice, the invoice status in Recurly updates to "Paid."

External Subscription Notifications alert your system to lifecycle changes (creation, renewal, cancellation, upgrades, downgrades, expirations, etc.) for subscriptions managed outside of Recurly, delivering full context in JSON or XML.

Check all the prerenewal notifications: https://docs.recurly.com/recurly-subscriptions/docs/prerenewal-notifications#/
