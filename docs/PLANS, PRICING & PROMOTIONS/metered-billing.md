---
title: Metered Billing
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
[block:callout]
{
  "type": "success",
  "title": "Try our new Usage-Based Billing!",
  "body": "This Metered Billing page has been deprecated.\n\nThere is a new, better way to handle usage-based billing. Read about it <a href=\"https://docs.recurly.com/docs/usage-based-billing\">here.</a>"
}
[/block]
Most metered billing plans charge upfront for the monthly costs, then  look back historically for any overage fees. This means that if you sign up for new service on the first day of June, you will immediately pay the monthly base fee for June. On the first day of July, you will receive a bill for July's monthly base fee plus any usage fees from June. In other words, you are prepaying the base fee and you pay the usage fees in arrears.

Traditionally, it has taken a tremendous effort to build billing systems for usage based models. Quite often, a company will bill its customers so that all the billing periods start and stop on the same day. This leads to an uneven flow of revenue and less flexibility with respect to pricing.

Recurly can simplify your metered billing implementation and simultaneously smooth out your revenue collection so it occurs continuously during the month. Here's how it works:

You define a monthly subscription plan and a price per month. When a customer signs up for the plan, Recurly sends your service a webhook saying "start the service". At this point, your system starts tracking the customer's usage. On a nightly basis, sum up the user's usage over the past 24 hours. If the user is over the quota, calculate the fee as a dollar amount (or using whatever currency you like) for the additional usage and submit this fee to Recurly as a one-time charge.

At the end of the month, Recurly will sum up all the additional one-time charges and automatically create an invoice charging for the accrued usage plus the next month's base price. Recurly will also send another notification to your service that the billing period renewed. At this time, your system can reset the user's usage meter to zero and start again.

## Bandwidth Overage Example

Suppose Acme bills $10/month for 50MB of bandwidth and $2 for every 10 MB of bandwidth past the initial 50MB. Verena signs up for the $10/mo plan. When she goes past 50MB of usage, Acme submits a $2 charge using the Recurly API:

```
account = Recurly::Account.find('verena')
account.adjustments.create(
  :description          => '10MB additional bandwidth',
  :unit_amount_in_cents => 2_00,
  :currency             => 'USD'
)
```

After submitting the charge, Acme allows Verena to use another 10MB of bandwidth. If she goes past that again, a new $2 charge is created. Acme does not have to track total bandwidth---just the bandwidth used since the last $2 charge. When her subscription renews, Acme resets her bandwidth counter at zero.

All the $2 overage fees will get invoiced when Verena's subscription renews. The invoice will bill for next month's $10 fee and the two overage fees from the previous month. Then, Recurly will run Verena's credit card for $14.

## Time-Based Metered Billing Example

Suppose Awesome Inc. was selling a service that cost users $20/month for the base service and $.02 for each minute the service is used. Let's say Jacob signs up for the $20/month plan and uses 125 minutes during the month.

In order to bill this, Awesome Inc. would track the amount of minutes Jacob uses the system (in this example 125) and would calculate the dollar cost of those minutes. In this example it would be $2.50. When his subscription renews, Awesome Inc. renews Jacob’s minute counter.

When Jacon's subscription renews, the $2.50 usage fee will be added to the invoice for next month's usage.  The invoice will show a $20 charge for next month plus $2.50 usage fee for the previous month.  Then, Recurly will collect $22.50 from Jacob's credit card.

## Questions?

We are in the process of collecting more feedback about how our customers handle their recurring billing today. Please let us know how your billing works. There's a good chance your system will work with Recurly today. And soon, metered and usage based billing will be even better with your support.