---
title: Accounts dashboard
excerpt: >-
  Manage your customer accounts effortlessly, ensuring seamless billing,
  subscriptions, and account tracking all from a centralized dashboard.
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

* Admin access to Recurly's dashboard.
* Familiarity with your customer data and billing processes.

### Limitations

* Account codes, once set, cannot be modified.
* Accounts can only be deleted while in sandbox mode.

# Definition

<Image align="center" className="border" border={true} src="https://files.readme.io/d74cea9-image.png" />

The Accounts Management section in Recurly provides an organized interface to handle all customer account related activities. This encompasses monitoring and managing subscriptions, billing information, account statuses, and provides the ability to search, create, update, close, or delete accounts as required.

# Key benefits

* **Centralized management**: View all customer accounts and subscriptions from a unified platform for streamlined operations.
* **Easy tracking and updating**: Effortlessly track and update billing information, ensuring accurate and up-to-date financial records.
* **Efficient account search**: Utilize effective search and filter capabilities for quick access to account details, enhancing operational speed and accuracy.

# Key details

## Dashboard

Your accounts dashboard is the gateway to all customer accounts managed by Recurly. This view allows for searching using various identifiers such as first name, last name, email address, account code and more. Utilize the filters to narrow down accounts based on different categories which may overlap; for instance, the **Open** filter encompasses both **Non-subscribers** and **Subscribers**.

### Account Status

| Status | Description                                    |
| ------ | ---------------------------------------------- |
| Open   | Accounts that are active and not closed.       |
| Closed | Accounts that have been deactivated or closed. |

### Subscription Status

| Status            | Description                                                                                    |
| ----------------- | ---------------------------------------------------------------------------------------------- |
| Active            | Subscribers with an ongoing subscription without interruptions.                                |
| Renewing          | Subscribers whose subscriptions are set to renew automatically at the end of the current term. |
| Non-renewing      | Subscribers whose subscriptions will not renew automatically after the current term concludes. |
| Future Start Date | Subscribers whose subscriptions are set to begin at a future date.                             |
| In Trial          | Subscribers who are currently in a trial period.                                               |
| Paused            | Subscribers whose subscriptions are temporarily on hold but not canceled.                      |
| Past Due          | Subscribers with at least one invoice that has not been paid by the due date.                  |
| No subscription   | Accounts without any current or past subscriptions.                                            |

## Account search

Locate accounts easily with the search functionality, using any of the following fields:

* Account code
* Company name
* Email
* First name
* Last name
* Username

## Account creation

Initiate the creation of a new account from the accounts overview page by clicking **New Account** to [create a new customer account](https://app.recurly.com/go/accounts/new). The details required are as follows:

| Field        | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| ------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Account Code | The account code serves as a unique identifier for your customers within Recurly, ensuring that no two customers share the same code. Typically, merchants synchronize account codes with identifiers used in their own tracking systems. It's also a common practice among Recurly merchants to use the customer's email address as their account code. Once established, the account code can't be modified. For validity, account codes should not start with a period (.), nor contain slashes (/) or semicolons (;). |
| Username     | A secondary identifier searchable on the dashboard.                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| Email        | The email field captures your customer's email address, which becomes the main channel for all communications from Recurly. Additionally, customers will utilize this email address to access your hosted account management pages. Unlike the account code, the email address does not have to be unique.                                                                                                                                                                                                                |
| CC Emails    | Specify additional email addresses in the CC Emails field if there are other recipients for account correspondence. Each email address should be separated by commas and formatted as [name@domain.com.](mailto:name@domain.com.) Recipients listed in the CC Emails field will receive all communications sent to the email address specified in the "Email" field.                                                                                                                                                      |
| First Name   | Customer's first name.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| Last Name    | Customer's last name.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| Company      | Customer's company name (if applicable).                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| VAT Number   | VAT information (if applicable).                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| Phone Number | Customer's phone number.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Address      | The provision of an account address is essential for manual invoicing. hen provided, it should at least include a postal code and country to facilitate precise tax calculations on the account's transactions.                                                                                                                                                                                                                                                                                                           |

## Billing info

The **Billing Info** section displays stored payment information, usually provided by the customer during a purchase or update. Determine the required billing address fields in the Admin under Site Settings. Note that Billing Info can differ from the account address. Learn more about Wallet <Insert link here>.

## Account notes

Keep internal notes on an account for context, like refund reasons, customer requests, or complaints. These notes are not visible to customers.

## Updating accounts

Post creation, all account values except the account code can be updated.

## Closing accounts

Closing an account results in permanent deletion of its billing info, cancellation of active subscriptions (which remain active till the current billing period ends), and failure of open invoices. Ensure all business is concluded with a customer before closing their account. The close account option is available when viewing an account in the admin console.

## Reopening closed accounts

Reopen a closed account via the Account Options menu in the admin console by selecting "Reopen Account", or create a new account with the same account code. Reopening restores account history, though billing information must be re-provided by the customer for continued billing.

## Deleting accounts

Accounts deletion is only possible in sandbox mode using the Clear Test Data button in site settings. Post-production mode transition, data retention is mandatory for historical accounting and cannot be removed from your site.
