---
title: Account Management
excerpt: >-
  Recurly offers a built-in customer portal (accessed by your customers at
  subdomain.recurly.com) with limited account management features. From here
  your customers can log in to view their invoices, update their billing
  information, or cancel their subscription at next renewal. For more
  information on Recurly's Hosted Account Management Solution, see <a
  href='/hosted-account-management.html'>Hosted Pages documentation</a>.


  Some merchants wish to have more features and flexibility; below find our best
  practices for integrating with Recurly's API and building your own account
  management portal.
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
##Subscription Modifications

Subscription modifications, also known as upgrades or downgrades, can be surfaced within a customer's account page. Based on options you present within your company's account management portal, use the <a href='https://dev.recurly.com/docs/update-subscription'> Update Subscription API call</a> to tell Recurly how to modify the user's current subscription plan. Subscription modifications can be made either immediately or at renewal. See <a href='/upgrades-downgrades.html'>Subscription Modification Documentation</a>.

##Subscription Cancellations or Terminations

You may wish to expose a subscription cancellation or termination button within your company account management portal. A cancellation leaves your customer's subscription active until the end of their current bill cycle, while a termination ends their subscription immediately. See <a href='https://dev.recurly.com/docs/terminate-subscription'> Subscription Cancellation or Termination Documentation</a>.

Some customers may have an outstanding balance at the time of cancelation/termination. If you wish to stop collection attempts when a customer ends their service with you, you may mark an invoice as failed via the API. See <a href='https://dev.recurly.com/docs/mark-an-invoice-as-failed-collection'> Invoice Documentation</a> for instructions on marking invoices and failed and stopping the collection attempts on that invoice.

Some merchants may have enforced contract lengths with their service. In these cases, we recommend replacing the cancellation/termination button with a link to contact support. Creating an avenue for discussion about early opt-out will prevent your business from receiving chargebacks.

##Subscription Postponing

Your customers may wish to delay services for a period of time and request that payment be paused, while still keeping their subscription active. Merchants can expose a "Pause my Subscription" function using <a href='https://dev.recurly.com/docs/postpone-subscription'>Recurly's Postpone API call</a>. This functionality delays the date of the customer's next invoice.

##Billing Information Updates

Giving your customers an easy and secure way to update their billing information is the best way to keep their subscriptions active and service uninterrupted. Due to the sensitive nature of credit card information, we recommend using Recurly.js to expose a billing information update form. Please see our <a href='/recurlyjs.html'>Recurly.js Documentation </a> for implementing this form within your company's account management portal.

##Invoices and Transaction History

Display your customer invoices online so they can easily query history and obtain receipts. See the <a href='https://dev.recurly.com/docs/list-transactions'>Recurly Transactions API</a> and <a href='https://dev.recurly.com/docs/list-invoices'>Invoice API</a> for instructions on pulling this data from Recurly.

##Access

Place a link to your customer account management portal inside all your Recurly email templates as well as your own app. We recommend creating multiple avenues for your customers to access, review, and revise their subscription billing terms and activity.