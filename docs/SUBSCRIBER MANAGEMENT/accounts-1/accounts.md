---
title: Accounts settings
excerpt: >-
  Accounts are core to managing your customers inside of Recurly. The account
  object stores the entire Recurly history of your customer and acts as the
  entry point for working with a customer's billing information, subscription
  data, transactions, invoices and more.
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

Use the [accounts dashboard](https://app.recurly.com/go/accounts) to view and manage customer accounts. You can search by first name, last name, email address, account code, and more. Filters let you drill in by category. Categories can overlap — for example, the **Open** filter can include both **Non-subscribers** and **Subscribers**.

## Filters

* **Open** — Accounts that aren’t closed.
* **Non-subscribers** — Open accounts with no active, canceled, or future subscriptions.
* **Subscribers** — Open accounts with at least one active or canceled subscription.
* **In trial** — Subscribers with at least one active or canceled subscription in trial.
* **Past due** — Subscribers with an invoice in a past-due state.
* **Non-renewing** — Subscribers that won’t renew after the current term.
* **Future** — Subscribers with a subscription that hasn’t started yet.
* **Closed** — Accounts that aren’t open.

## Account search

You can search by:

* Account code
* Company name
* Email
* First name
* Last name
* Username
* Coupon code

## Create an account

From the accounts overview page, select **New account** to [create a customer account](https://app.recurly.com/go/accounts/new). Provide:

### Account code

Uniquely identifies a customer in Recurly. No two customers can share the same account code. Many merchants align this value with their own user identifier; using the customer’s email address is also common. Once set, the account code can’t be modified.
**Invalid account codes:** values that start with a period (`.`) or contain slashes (`/`) or semicolons (`;`).

### Username

A secondary identifier you can search for in the dashboard.

### Email

The customer’s email address. Recurly communications are sent here, and customers use this email to sign in to hosted account management pages. This value doesn’t need to be unique.

### CC emails

Additional addresses that should receive account emails. Separate with commas (for example, `name@domain.com,name2@domain.com`). CC recipients receive the same messages sent to **Email**.

### First name / Last name / Company / VAT number / Phone number

Basic profile and tax details.

### Address

Used on manual invoices. Include at least postal code and country so taxes can be calculated for the account’s purchases.

## Billing info

The **Billing info** section shows stored payment details. Customers usually add or update this during purchase or when they manage their payment method. You can choose how much of the billing address is required in **Admin → Site settings**. Billing info can differ from the account email and address.

## Account notes

Leave internal notes to add context — for example, refund reasons or customer requests. Notes are not visible to customers.

## Update accounts

After creation, you can update all fields except the account code.

## Close accounts

Closing an account:

* Permanently deletes stored billing information.
* Cancels any active subscriptions (they remain active until the current billing period ends).
* Fails any open invoices.

Close accounts only when all business with the customer is complete. You’ll see **Close account** in the admin when viewing an account.

## Reopen closed accounts

Reopen an account from **Account options → Reopen account**, or create a new account using the same account code. History is restored, but customers must provide billing info again to resume billing.

## Delete accounts

Accounts can only be deleted in **sandbox** (see **Clear test data** in site settings). In production, data is retained for historical accounting and can’t be removed.

***

## Per-account rate limiting

Recurly enforces built-in, per-account rate limits to protect end-customer accounts from excessive activity. These limits are part of the core Recurly platform and are **not** tied to deprecated Kount/Fraud Management features.

### What’s limited

Counters increment based on the **`account_code`** used in an API request for:

* New subscriptions
* Transactions
* Billing info updates

### Where to see limits (sandbox)

In sandbox, open any **test customer account**. On the right side of the page, under **Billing info** and **Hosted page links**, you’ll see the current per-account limits and their counters for **New subscriptions**, **Transactions**, and **Billing info updates**.

### Management

These limits can’t be changed. You can manually **reset** the counters from the Recurly UI if needed.

> **Note:** This capability is proprietary to Recurly and commonly misattributed to legacy Kount/Fraud Management. The limits apply regardless of any external fraud or payment integrations.
