---
title: DIY trainings
excerpt: >-
  The fastest way to get familiar with Recurly's capabilities and UI is to
  undergo a series of exercises based on actual use cases for the application.
  Most of the manual exercises below are actions that can also be completed via
  use of the Recurly API, in addition to the admin console.
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
### Task 1 - Create a Site
Open a free sandbox account at https://app.recurly.com/signup.
[block:callout]
{
  "type": "warning",
  "body": "You must select a [data hosting region](https://docs.recurly.com/docs/data-hosting) for your new site when you open the sandbox account."
}
[/block]
Your free sandbox will not expire unless you: close the site, move it into production mode, or fail to log in to the site for 60 days. The system will send you a reminder email near the end of this timeframe, to remind you to log back in to retain access to your site.

### Task 2 - Create Subscription Plans
You can click "Create plan" to use the walk-through tutorial, or you can "go straight to your account" and explore on your own.

*HINT: Go to Configuration --> Plans*
  * Create a plan that costs $10 and recurs every 15 days
  * Create a plan that has a $15 setup fee and costs $50 a month
  * Create a plan that costs $60 a month that runs for a year then ends
  * Create a plan with a 15 day free trial that costs $45 a month and has 2 add-ons 

### Task 3 - Sign Up Users
Sign up 4 individuals, one person per plan, through the hosted payment pages.
*HINT: Your hosted payment page URLs can be found within each Subscription Plan.*

Create an account for a new customer and manually add a subscription on their account page

### Task 4 - Generate Coupons
  * Create a coupon that is for 50% off for 3 months
  * Create a coupon that is 10% off forever that can be redeemed 5 times
  * Create a coupon that can only be used on your $50/month plan
  * Create a coupon that will give you 40% off the first invoice it is applied to
  * Create a set of 50 bulk unique code coupons for $5 off of any subscription, to be applied indefinitely

### Task 5 - Configure Hosted Payment Pages
  * Add a company logo to your hosted payment page
  * Add a privacy policy URL that redirects to: http://knowyourmeme.com/memes/doge
  * Add a terms of Service URL that is: http://didthelakersgetswept.com/
  * Change your signup button text to give your HPP (hosted payment page) flair

### Task 6 - Recurly Site Configuration
  * Invite your email address to your Recurly site with all permissions except configuration
  * Change your Dunning settings to have 5 attempts that leave the subscription active after 20 days
  * Add a technical contact to your Site Settings
  * Change your listed phone number to your company's main number
  * Turn off the Subscription Expired template

### Task 7 - Modify Subscriber Accounts
  * Redeem a coupon on a customer's account
  * Change a subscription plan's renewal date in the customer account
  * Cancel a customers subscription and give a prorated refund
  * Cancel a customers subscription and have it take place at the next renewal
  * Add a pending charge to a customers account
  * Add a credit to a customers account then post a one time transaction
  * Edit a customer's subscription so the pricing is different than the plan's default price and have the changes take place immediately
  * Migrate a customer from one plan to another and have it take place on next renewal
  * Partially Refund an invoice
  * Void a transaction

### Task 8 - Sales Tax
  * Enable sales tax
  * Collect tax in all regions except New Mexico, Puerto Rico, and Washington D.C.