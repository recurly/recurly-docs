---
title: Dunning campaigns
excerpt: >-
  Maximize revenue recovery with Recurly's Dunning Campaigns. Tailor your
  collection strategies, optimize email notifications, and manage failed
  transactions seamlessly.
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

* An active Recurly account.
* Configuration user access.
* For multiple dunning campaigns: This feature **may not be included** in the Starter or Pro plans. If you are interested, please contact [Recurly Sales](https://recurly.com/demo/contact-sales/) to discuss upgrade options.

### Limitations

* Dunning settings are versioned; changes to a campaign won't affect invoices already in dunning.
* Maximum of 50 dunning campaigns for eligible merchants.

# Definition

Dunning Management refers to the strategies and communications used to prompt subscribers for payment after an initial failure, and the duration allowed for recovery attempts.

# Key benefits

* **Customized collection strategies**: Tailor your dunning campaigns to specific customer cohorts for optimized results. Additionally, track which customers are assigned which dunning campaign, and received which dunning email, in the Account Activities export.
* **Enhanced subscriber communication**: Send targeted emails to subscribers, informing them of payment failures and prompting action.
* **Flexible dunning cycles**: Choose from automatic, manual, and post-trial dunning cycles, each with its own set of emails and schedules.
* **Improved revenue recovery**: Longer dunning windows have shown to result in higher recovery rates.
* **Analytical insights**: Track dunning versions and measure their effectiveness over time.

# Dunning campaigns

Originating from a term in the 17th century, "dun" means "to demand payment for a debt." Dunning is pivotal in your revenue collection process, focusing on:

* Notifying subscribers via email after a payment failure.
* The duration allowed for Intelligent Retries to recover a failed transaction.

Dunning activates when an automatic invoice (such as credit card, ACH, direct debit) fails its initial payment attempt, when manual invoices (like check, wire) surpass their net terms, and when a subscription trial attempts to convert to a paid subscription but the payment fails.

Recurly's Dunning Management lets you devise multiple collection strategies tailored for different customer groups. If invoices become past due, Recurly employs the relevant dunning campaign to recover the payment. While every account has a default dunning campaign, those with permissions can create targeted campaigns for specific plans or accounts.

These multiple dunning campaigns can be assigned to specific plans and/or accounts, enabling a more tailored approach for communications with different audiences (this feature **may not be included** in the Starter or Pro plans. If you are interested, please contact [Recurly Sales](https://recurly.com/demo/contact-sales/) to discuss upgrade options). This customization aims to enhance failed payment recovery and boost subscriber retention. Additionally, merchants can evaluate the effectiveness of various campaigns through testing and utilize the <a href="https://docs.recurly.com/docs/dunning-effectiveness" target="_blank">Dunning Campaign analytics</a> to determine the optimal dunning configuration for their customer base. For further information, refer to the section on multiple dunning campaigns below.

### Accessing dunning management

1. **Login** to your Recurly account.
2. Navigate to the **Configuration** menu.
3. Select **Dunning Management** from the dropdown.

## Default dunning campaigns

Every site will possess one default dunning campaign, which is used for all invoices that don't have a separate designated campaign on the account or plan. The default campaign should represent your standard collection process for when a customer doesn't settle an invoice.

For sites with multiple dunning campaigns, the default campaign can be determined using the **Campaign Actions** button on the campaign details page. Note that all plans and accounts set to use the default dunning campaign will now employ the newly designated default campaign.

# Dunning configuration

Access Dunning Management via your account's Configuration menu. Here, users with access can modify failed payment email intervals, the number of email attempts, the specific email to send, and the desired outcome for a subscription and invoice if payment remains uncollected.

<Image align="center" width="50% " src="https://files.readme.io/e1ccbbc-5f1bc75-Dunning_Management__Recurly_2021-06-17_at_10.43.25_AM.jpg" />

## Modifying the default dunning campaign

Recurly already has a default dunning campaign set up for you, and you are free to modify it to suit your needs.

1. From the Dunning Management page, **select** the dunning campaign you wish to edit.
2. **Click** the **Campaign Actions** dropdown.
3. **Select** **Edit Campaign**.
4. **Make** the necessary changes.
5. **Click Save**.

### Campaign details

This section is for internal reference, allowing you to name and identify the campaign. The Campaign Name will be visible when choosing dunning campaigns on the Plan and Account pages in the Admin Console. Remember, the Campaign Code can only comprise numbers, lowercase letters, dashes, pluses, and underscores.

### Dunning cycles

Dunning cycles are categorized based on the invoice's collection method:

* **Payment Declined** emails for automatic invoices.
* **Invoice Past Due** emails for manual invoices.
* **Post-Trial Payment Declined** emails for both automatic and manual invoices that fail after a free trial.

Each dunning campaign can encompass an automatic invoice dunning cycle, a manual invoice dunning cycle, and a post-trial dunning cycle, each with distinct collection emails and schedules. Each of these different dunning cycles allow you to create different messages, and CTAs to effectively communicate with your customer to take the desired action.

#### Automatic invoice dunning cycle

For automatic invoice payment failures, Recurly will send a **Payment Declined** email, notifying the customer of the failure and urging them to refresh their billing details. Consecutive emails are sent based on the schedule you set in the relevant dunning campaign.

<Image align="center" width="50% " src="https://files.readme.io/9eb5bda-033141c-Edit_Campaign__Recurly_2021-06-17_at_10.43.46_AM.jpg" />

Here, you can add, delete, or modify steps in the dunning cycle. Each dunning step can be linked to a specific email template. You can conveniently preview or modify an email using the links beneath the Email Template dropdown. Emails can also be configured in the **Email Templates** section of the Configuration panel. All dunning-associated emails are located at the bottom of the Email Templates page.

#### Manual Invoice Dunning Cycle

Manual invoice dunning cycles are set up similarly to the automatic invoice dunning cycle, but they utilize the **Invoice Past Due** email templates.

<Image align="center" width="50% " src="https://files.readme.io/bd259e6-01e0031-Edit_Campaign__Recurly_2021-06-15_at_11.54.55_AM.jpg" />

It's essential to note that users with the authority to modify the Customer section in Recurly can opt to reopen failed manual invoices. If a failed manual invoice is reopened, dunning **will not** resume (meaning no dunning emails will be sent), and the linked subscription remains unaffected. When a manual invoice is reopened, it stays in an Open state indefinitely until it's closed and marked as paid/failed.

#### Trial dunning cycle

For invoices that remain unpaid after transitioning from a free trial to a paid subscription, Recurly can send a **Post-Trial Payment Declined** email to attempt customer recovery. If incorporated into your dunning campaign, this cycle can be limited to automatic invoices only or extended to both automatic and manual invoices. Otherwise, the setup of trial dunning cycles mirrors the steps of the automatic invoice dunning cycle.

<Image align="center" width="50% " src="https://files.readme.io/c3ad07a-7b325c4-Post-Trial_Dunning_Cycle.png" />

It's crucial to understand that the trial dunning cycle only activates for unpaid subscriptions that had a free trial period integrated into the subscription plan or applied via a coupon. "Free trial" alternatives that don't use Recurly's trial feature, like creating a $0 subscription and then raising the price post the initial billing cycle, won't activate the trial dunning cycle when unpaid.

#### End of dunning cycle

For every dunning cycle, you can set the behavior of the invoice and the subscription if the customer does **not** pay by the cycle's end. The final email sent to the customer if the subscription expires can also be customized.

<Image align="center" width="50% " src="https://files.readme.io/b082fe6-da6c473-Edit_Campaign__Recurly.png" />

By default, dunning settings will automatically mark an invoice as failed at the cycle's end if it remains unpaid. A failed invoice in Recurly signifies it's written off as bad debt, removing the owed balance from the customer's account. You can adjust your dunning settings to never auto-fail the invoice, leaving it overdue.

If your invoices remain overdue post the dunning cycle, there are two methods to retry collection on the invoice. Both actions will send all overdue invoices on an account into collections:

* Have the customer update their billing details.
* Add a new subscription to the account (resubscribe the customer).

(Note: If you have [Account Updater](https://docs.recurly.com/docs/account-updater) activated, Recurly will persistently run Account Updater on the account linked to the overdue invoice and attempt to collect payment on that invoice indefinitely).

# Email template configuration

You can effortlessly preview or modify an email from links below the Email Template dropdown. Emails can also be configured in the **Email Templates** section of the Configuration panel. All Dunning Management Templates are located at the bottom of the Email Templates page. Access to this page requires the Configuration user role.

For more details on editing email templates, [check the dedicated documentation](https://docs.recurly.com/docs/email-templates).

## Creating a new dunning email template

To create a new email template, head to the Dunning Management section of Email Templates. Here you will find email template configuration for the following emails: Payment Declined Templates (for automatic invoices), Invoice Past Due Templates (for manual invoices), or Subscription Expired for Non-Payment Templates (for subscriptions that remain unpaid at the end of any dunning cycle) and click *New Email Template. The Dunning Management email configuration section also includes the email for Payment Declined Due to 3D Secure 2.*

<Image align="center" width="50% " src="https://files.readme.io/f5f646b-903fe6e-Email_Templates__Recurly.png" />

You'll have the option to select a base template, so you don't have to craft the email from scratch. The template requires a name, which will be referenced when linking the email with dunning steps on a dunning campaign.

<Image align="center" width="50% " src="https://files.readme.io/276a9f6-98375c0-Screen_Shot_2018-02-06_at_3.01.10_PM.png" />

Each dunning email will maintain the same aesthetics as our other email templates. However, you can customize the emails in the dunning process and have distinct email content at each step. Modifying the messaging in each email can effectively instill a sense of urgency in your subscribers.

After creating new emails, you can link them with steps in your dunning process by navigating to the Dunning Management page. Once an email is associated with a dunning campaign, this association will be noted on the Email Templates page under each dunning email.

## Deleting a dunning email template

If you wish to delete a dunning email template, first ensure it isn't linked to any dunning step. Achieve this by navigating to the Dunning Management page, adjusting your dunning settings, and removing the template from any dunning campaign and step it's linked to.

Then, head to the Email Templates page and locate the email. If there's a note stating it's "Not being sent by any current Dunning Campaigns", you can delete the email. Note that you can't delete the base Post-Trial Payment Declined, Payment Declined, Invoice Past Due, or Subscription Expired for Non-Payment email templates.

## Updating billing info

[3]: https\://dev.recurly.com/docs/list-accounts

When your customers receive a failed payment email, they should know how to refresh their billing details. The default payment declined email template provides your customers a direct link to their hosted account management page, where they can submit updated billing details.

You can incorporate a direct link to a customer's account management page from your website using the `hosted_login_token` parameter available on the \[Accounts API]\[3]. API users can also modify the email template to direct to a billing update form on their own site.

When billing details are successfully updated, Recurly will retry collection on all overdue invoices on the account (note: automated updates executed by Recurly's <a href="https://docs.recurly.com/docs/account-updater">Account Updater</a> also initiate a collection attempt).

## Stop dunning

For subscribers in dunning who simply require a few more days to pay, you can halt dunning for an invoice without transitioning the invoice to a Closed state. To do this, open an overdue invoice and click **Stop Dunning** in the Invoice Actions. When dunning is halted, the invoice will remain active in the **Past Due** state. However, Intelligent Retry attempts will be halted (note: though Intelligent Retry attempts will be halted, if you have <a href="https://docs.recurly.com/docs/account-updater">Account Updater</a> activated, Recurly will persistently run Account Updater on the account linked to the overdue invoice and attempt to collect payment on that invoice indefinitely), dunning emails will no longer be sent, and the End of Dunning Cycle action won't be executed.

## Stop collection & mark paid

The entire collection process can be halted for a past due invoice by opening the invoice and clicking either **Stop Collection** in the Invoice Actions, which will mark the invoice as failed, or **Mark Paid**, which will indicate that the invoice was successfully paid. (The latter option is typically employed when funds are received outside of Recurly.) Either option will transition the invoice to a **Closed** state, halt Intelligent Retry attempts on the invoice, stop dunning emails, and bypass the End of Dunning Cycle actions set for the given dunning campaign.

Note that halting collection on an invoice *will not* automatically cancel the related subscription. The subscription must be canceled separately to prevent the subscription from renewing again. A subscription will only be automatically canceled if an invoice fails dunning (assuming your dunning settings are set to expire a subscription at the end of the dunning process).

# Multiple dunning campaigns

For merchants on Recurly's Starter plan, all invoices that become overdue will follow the default Automatic Invoice Dunning Cycle, the default Manual Invoice Dunning Cycle, or the default Post-Trial Dunning Cycle, based on the invoice's collection method and the subscription type.

You can create and customize dunning campaigns for up to 50 different scenarios. Your existing Dunning Configuration will be retained as your Default campaign. This feature **may not be included** in the Starter or Pro plans. If you are interested, please contact [Recurly Sales](https://recurly.com/demo/contact-sales/) to discuss upgrade options.

### Creating a new dunning campaign

1. From the Dunning Management page, click the **Create Campaign** button.
2. Fill in the **Campaign Details** section with the desired name and reference code.
3. Configure the **Plan Selection** if you wish to assign this campaign to specific subscription plans.
4. Set up the **Dunning Cycles** based on your desired collection methods and schedules.
5. Click **Save**.

### Assigning a dunning campaign to a plan or account

You can specify the dunning campaign of your choice for each plan and/or account (this feature **may not be included** in the Starter or Pro plans. If you are interested, please contact [Recurly Sales](https://recurly.com/demo/contact-sales/) to discuss upgrade options). After crafting your dunning campaign(s) in the Configuration section of the Recurly Admin console, access any new or existing **Plan** or **Account** and select your preferred dunning campaign for that entity from the dropdown. You can also choose your desired dunning campaign for any plan or account via our [API](https://developers.recurly.com/api/). To allocate a dunning campaign to a large number of plans simultaneously, you can utilize our bulk update API endpoint.

1. Navigate to the desired **Plan** or **Account** page.
2. Locate the **Dunning Campaign** dropdown.
3. Select the desired campaign from the list.
4. Save the changes.

## Editing dunning campaigns

When you adjust a dunning campaign or allocate a different campaign to a plan or account, all invoices currently in dunning (in an overdue state) will persist with the dunning settings that were active when the invoice became overdue. All new invoices that enter dunning from this point will utilize the new settings. This is because dunning settings are versioned, ensuring an invoice currently in dunning doesn't alter its email send schedule or retry failed transactions.

## Disabling dunning campaigns

For merchants with permissions to establish multiple dunning campaigns, redundant campaigns can be deactivated, and they won't count towards your 50 dunning campaign limit. However, your default campaign can't be deactivated; you must first set another campaign as the new default if you wish to deactivate the existing default.

When a campaign is deactivated:

* The campaign won't appear in the dropdown on the Plans or Accounts pages in the Recurly Admin console.
* Any plans or accounts using that campaign will employ the default campaign in the future.

<Image align="center" width="50% " src="https://files.readme.io/71c62c3-aca5887-Dunning_Management__Recurly.png" />

## Dunning campaign priority

* If no additional campaigns are crafted, the default campaign will be used for all invoices.
* If a dunning campaign is linked to a plan, that campaign will be employed for subscribers whose invoices become overdue.
* If a dunning campaign is linked to an account, that campaign will be used for any past due invoices for that account.
* If multiple dunning campaigns could potentially apply to a subscription, the priority is: Account > Plan > Default.
* For merchants bundling multiple subscriptions onto a single invoice, if a single dunning campaign is **not** linked to an account and multiple subscriptions on the invoice are set to use different dunning campaigns, the dunning campaign of the oldest subscription on the invoice will be used. This logic remains true if any of the subscriptions on the invoice failed post a free trial period.
* For merchants using the Account Hierarchy feature, if the account being billed for the invoice (parent or child) has a specific dunning campaign linked, then that dunning campaign will be used for the invoice. Otherwise, the invoice will follow the dunning priority mentioned above. Any dunning settings on the other, unbilled account (parent or child) will **not** be considered in the dunning campaign priority logic.

# Understanding effective dunning

[Enhance your dunning emails with these tips.](https://recurly.com/blog/improve-your-dunning-emails-for-subscription-billing/)

## Dunning best practices

We trust our merchants to understand their customers and their collection process best. We offer the flexibility to modify dunning settings, granting you ultimate control over your collection strategy.

Here are some best practices to consider:

* Extended dunning windows lead to better recovery rates.
* For monthly subscriptions, we recommend a dunning length of no longer than 27 days. If your dunning exceeds 27 days in February, subscribers who don't pay might receive a second invoice and then have their subscription expire soon after. In addition, a 27-day duration will allow Recurly to maximize the number of intelligent retries (link to: [https://docs.recurly.com/docs/retry-logic](https://docs.recurly.com/docs/retry-logic)) on a failed invoice, giving you the highest chance of recovering a failed invoice.
* Direct debit payments can take 3 days or more for a response, which can influence the end of the dunning cycle.
* Unless otherwise configured, the default dunning campaign will be employed and will expire the subscription and fail the invoice.
* For high-value subscribers, most merchants prefer to keep the subscription active and the invoice open.
* Enabling different dunning campaign messages and durations for your different plans is a great method to achieve the highest success rate of recovered invoices, resulting in subscriber retention. For example, having a 27 day window for monthly plans, yet up to a 60 day window for quarterly, bi-annual and annual plans is a great approach.

## Examining previous configurations of a dunning campaigns

Every invoice adheres to the dunning configuration that was in place when the invoice entered the dunning process. To review previous dunning configurations, simply click on the **Settings History** button within each dunning campaign.

<Image align="center" width="50% " src="https://files.readme.io/c7f6f37-0b5407f-Settings_History__Recurly_1.png" />

This feature provides a comprehensive view of your dunning settings' evolution, ensuring you always have a point of reference. It's an invaluable tool for experimenting with various dunning schedules and evaluating their effectiveness over time.

For a concise overview of the analytics associated with each dunning version, select the **View Analytics** button located on the right of each entry in the Settings History page. Please note, to access these pages, you must have the Analytics role. Currently, analytics are exclusively available for automatic payment invoices.

For a deeper dive into gauging dunning effectiveness with Recurly's reports, consult our analytics documentation [here](https://docs.recurly.com/docs/dunning-effectiveness-report). For insights and best practices, explore [our blog](https://blog.recurly.com/how-effective-is-your-dunning-strategy-recurly-analytics-has-the-answer).

## How to test dunning behavior

For merchants keen on accelerating the dunning process to evaluate webhooks, email delivery, and other parameters, follow these steps to initiate dunning in **sandbox** mode:

1. Register an account using the "Success" test card number: 4111-1111-1111-1111.
2. Modify the account's billing details to the "Fail, but save" test card number: 4000-0000-0000-0341. (Note: While it might seem like an error has occurred, this is anticipated. The card number will still be stored on the account.)
3. Expedite the renewal procedure by selecting "Change" adjacent to the Current Period on the subscription.
4. Adjust the subscription's next renewal date to be 1 hour ahead, and then confirm the changes.
5. Within the hour, the subscription will renew, initiating your dunning procedure.

# Dunning notifications via webhooks

Webhooks can be employed to synchronize your service with collection activities within Recurly.

## Dunning event

Sent when invoices enter and remain in dunning and will use the same dunning schedule as configured under Dunning Management in Recurly. These push notifications are sent irrespective of whether merchants use Recurly to send customer communication. Recurly merchants employ this push notification to customize customer emails for each dunning step or to reach customers through different communication channels (an external email system, SMS, in-app notifications, etc.)

## Failed payment

Sent after each failed payment. Recurly merchants use this push notification to flag a user as overdue within their application and encourage them to refresh payment details.

## Successful payment

Sent after a successful payment. Recurly merchants use this push notification to recognize when a previously overdue user is now in good standing.

## Subscription expired

Sent if Recurly terminates a subscription due to non-payment or if the subscription is canceled and no longer valid. When this notification is received, the subscription should be immediately terminated in your system. This is the primary notification you should catch if you are receiving push notifications.

[Discover more about webhooks and how to use them.](https://docs.recurly.com/docs/webhooks)

# Transitioning from sandbox to production

While Recurly sites in sandbox or development mode allow testing of multiple dunning campaigns' creation and assignment, this feature is only accessible in production for those on Recurly's Professional or Elite plans.

Upon transitioning a sandbox or development site to a production site under our Starter plan, all dunning campaigns, barring the default campaign, will be deactivated. These inactive campaigns will be locked from editing and cannot be reactivated or set as the default. If you continue with Recurly's Starter plan, any plans that were assigned a non-default campaign during testing will be reconfigured to use the default dunning campaign.

### Plan selection

If you have several dunning campaigns set up, you can link a specific dunning campaign to certain subscription plans either now or later, in the plan details section. If a plan is linked to a non-default dunning campaign, all past due subscriptions for that plan will follow the rules of the chosen dunning campaign. However, if an account with a past due invoice has been assigned a different dunning campaign, it will follow that one instead.

### Transactions that won't retry

If your initial dunning email for failed automatic invoices is scheduled to be sent **after** the first payment attempt, there's added functionality for handling transactions that won't undergo the retry process. This includes:

* Transactions facing a hard decline.
* Transactions failing due to incorrect billing details.

Since these transactions won't succeed without updating the payment method or billing details, Recurly won't retry these transactions.