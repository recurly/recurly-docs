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
## Dashboard

<a href="https://app.recurly.com/go/accounts" target="_blank">Your accounts dashboard</a> provides an overview of all customer accounts managed by Recurly. From this view, you can search by first name, last name, email address, account code, and more. The filters on this view allow you to drill into accounts by different categories. Categories overlap and are not necessarily distinct, _e.g._ the **Open** filter will return both **Non-subscribers** and **Subscribers**.

#### Open

Accounts that aren't Closed.

#### Non-subscribers

Open accounts with no active, canceled, or future subscriptions.

#### Subscribers

Open accounts with at least one active or canceled subscription.

#### In trial

Subscribers with at least one active or canceled subscription in trial mode.

#### Past due

Subscribers with an invoice in the past-due state.

#### Non-renewing

Subscribers that won't renew after the current term

#### Future

Subscribers with a subscription that hasn't yet started.

#### Closed

Accounts that aren't Open.

## Account search

You may search for an account on any of the following fields:

* Account code
* Company name
* Email
* First name
* Last name
* Username
* Coupon code

## Account creation

From the accounts overview page, click New Account to <a href="https://app.recurly.com/go/accounts/new" target="_blank">create a new customer account</a>. You will be asked to provide the following details:

#### Account code

Uniquely identifies your customers in Recurly. No two customers can share the same account code. Merchants typically align account codes with the same identifiers they use to track users in their own system. Using the customer's email address as their account code is another popular convention among Recurly merchants. Once set, the account code cannot be modified. Account codes will be considered invalid if they start with a periods ( . ) or  contain slashes ( / ), or semicolons ( ; ).

#### Username

A secondary identifier that can be searched against on the dashboard.

#### Email

Your customer's email address. When provided, all Recurly communication is sent to this address. The customer will also use this email address to log into your hosted account management pages. This value does not need to be unique.

#### CC Emails

Additional email address that should receive account correspondence. These should be separated only by commas and should be formed as [name@domain.com](mailto:name@domain.com) only. These CC emails will receive all emails that the "Email" field also receives.

#### First name

Customer's first name

#### Last name

Your customer's last name

#### Company

Your customer's company name (if applicable)

#### VAT number (if applicable)

VAT information

#### Phone number

Your customer's Phone number

#### Address

The account address is used in manual invoices and must contain at least a postal code and country for taxes to be calculated on any of the account's purchases.

## Billing info

On an account, there is a **Billing Info** section that shows stored payment information. Billing Info is usually filled out by the customer upon purchase or when they update their information. The merchant determines how much of the billing address is required in the Admin under Site Settings. Billing Info can be different from the account email and address.

## Account notes

Your team can leave notes on an account to add context, _e.g._ the reason for a refund, customer requests, and/or complaints. These notes are internal and not exposed to your customers.

## Updating accounts

Once an account is created, all values (with the exception of the account code) may be updated.

## Closing accounts

Closing an account permanently deletes its billing information, cancels any active subscriptions (canceled subscriptions will remain active until the end of the current billing period before expiring), and fails any open invoices. We recommend closing accounts only when all business is concluded  
with a customer.

You will see the option to close an account when viewing an account in the admin console.

## Reopening closed accounts

A closed account can be reopened by accessing the Account Options menu in the admin console and choosing 'Reopen Account', or by creating a new account with the same account code. Reopening an account will restore its history but billing information will need to be provided by the customer to continue billing.

## Deleting accounts

Accounts can only be deleted from your site while in sandbox mode (look for the Clear Test Data button in your site settings). Once your account is in production mode all data is kept for historical accounting and cannot be removed from your site.
