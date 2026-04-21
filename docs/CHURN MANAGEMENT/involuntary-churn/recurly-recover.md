---
title: Recurly Recover
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

Recurly Recover lets you collect on failed invoices without using Recurly as your primary subscription management or billing platform. It's purpose-built for merchants who need a dedicated, flexible retry engine — independent of the rest of Recurly's subscription infrastructure.

## Definition

Recurly Recover provides the ability to submit past due invoices via an API and automatically retry collection — without shifting your billing or subscription platform onto Recurly. When a past due invoice is submitted, Recurly creates a shell account, a past due invoice with a corresponding transaction, and saves the payment methods.  From there, Recurly calculates a retry schedule, and handles the full collection lifecycle until the invoice is paid or the provided dunning campaign is exhausted.

## Key benefits

* Works independently of your billing stack: You don't need to use Recurly for subscription management to take advantage of its retry engine. Recurly Recover seamlessly integrates with your existing infrastructure and is completely self-serve.
* Flexible dunning campaign control: Assign specific dunning campaigns per API request, giving you the ability to run A/B tests across different retry windows and strategies.
* Vindicia integration support: If you're integrated with Vindicia, Recurly can hand off retry attempts at a configurable point in the dunning campaign, maximizing your chances of recovery.

# Key details

How it works

Once you've gained access to Recurly and generated your API key, you're ready to start submitting failed invoices. Review the API documentation to understand what a successful call requires.
When a call returns a successful response, Recurly creates the following objects on the account:

A charge
A past due invoice
One or more failed transactions
Billing information (payment token) stored on the account

If the Wallet feature flag is enabled, payment methods are marked as primary and backup based on your specifications in the API request. If the BIN backfill feature flag is enabled, Recurly will backfill the token and display the associated credit card details — including card type, last four digits, and expiration date.
Retry and collection flow
Recurly calculates the next collection attempt date based on the data in the API request. From there, the retry process follows this logic:

If collection succeeds at any point, the invoice is marked as Paid and a webhook event fires
If the first attempt fails, Recurly continues retrying for the length of the specified dunning campaign
If no dunning campaign is provided, Recurly uses your default campaign
If the campaign is exhausted without a successful collection, the invoice is marked as Failed and a webhook event fires

While an invoice is in a Past Due state, you can cancel all future collection attempts at any time by marking the invoice as Failed or Paid using the Recurly Invoice API.
Dunning campaigns and emails
Each dunning campaign automatically includes dunning emails. If you're managing dunning-related communications through your own system, you can remove or disable these emails in Email Templates within each dunning campaign.
Vindicia integration
If you're integrated with Vindicia, additional configuration is required. You'll need to:

Enter your Vindicia credentials on the Vindicia Retain page in Recurly
Select your token option on that same page

These steps allow Recurly to call Vindicia for additional collection attempts using payment tokens.
Splitting the dunning window between Recurly and Vindicia
The collection window in days setting in your Vindicia Retry Dunning Settings determines how the dunning campaign is divided between Recurly and Vindicia.
Example: If your dunning campaign is 27 days and the Vindicia retry window is set to 10, Recurly retries for 17 days and then hands off to Vindicia for the remaining 10.
Vindicia window settingBehaviorSet to 0Only Recurly retries; Vindicia is not notifiedSet to a value less than the campaign lengthRecurly retries first, then Vindicia handles the remainderSet equal to the full campaign lengthRecurly does not retry; the past due invoice is sent to Vindicia immediately
In all cases, the account and its associated objects are still created.
Each dunning campaign can have a unique retry window value. Combined with the ability to send dunning campaign IDs in the API, this gives you the flexibility to run A/B testing across different retry strategies.
Webhooks
Recurly fires webhook events at key points in the collection lifecycle — including when an invoice is marked as Paid or Failed. Review the webhooks documentation for a full list of available events.

FAQs
Do I need to use Recurly as my subscription management platform to use Standalone Retry?
No. Standalone Retry is designed to work independently, so you can retry failed invoice collection even if Recurly isn't your primary subscription management or billing platform. We don't recommend combining Standalone Retry with Recurly's full subscription management product at this time.
What happens when a failed invoice is submitted via the API?
Recurly creates an account (without a subscription), along with a charge, a past due invoice, and one or more failed transactions. Billing information is stored on the account, and Recurly automatically calculates the next collection attempt date based on the data in your API request.
How does the retry process work if I'm also integrated with Vindicia?
The dunning campaign length is split between Recurly and Vindicia based on the "collection window in days" setting in your Vindicia Retry Dunning Settings. For example, if your campaign is 27 days and the Vindicia window is set to 10, Recurly retries for 17 days, then hands off to Vindicia for the remaining 10. Setting the window to 0 means only Recurly retries; setting it equal to the full campaign length means Vindicia handles all retries immediately.
Can I stop retry attempts on a past due invoice?
Yes. While an invoice is in a Past Due state, you can cancel all future collection attempts at any time by marking the invoice as Failed or Paid using the Recurly Invoice API.
