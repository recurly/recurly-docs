---
title: 'Stop the Leak: How to optimize Dunning for growth'
excerpt: On-Demand Recurly Navigate Webinar.
deprecated: false
hidden: true
metadata:
  robots: index
next:
  description: >-
    Download the Dunning Optimization Checklist: A quick reference of best
    practices and configurations to keep your Dunning setup and strategy
    polished. 
  pages:
    - slug: dunning-optimization-checklist
      title: Dunning Optimization Checklist
      type: basic
---
Discover proven strategies to reduce involuntary churn and recover lost revenue in this lunch and learn led by Hannah Wheeldon, Strategic CSM at Recurly. Gain actionable insights tailored for DTC businesses, with valuable takeaways for B2B, and learn how to optimize your dunning process for long-term growth.

<Image align="center" alt="Stop the Leak: How to optimize Dunning for growth" border={false} src="https://files.readme.io/bcf004b875a18b027f27ab41a8fc1f14360b33f42a3f1e479929d0cc43a32000-Screenshot_2025-11-17_at_6.28.54_PM.png" />

> **Note**: Watch it <Anchor label="on-demand here" target="_blank" href="https://recurly.ondemand.goldcast.io/on-demand/a65f472f-9876-4736-9209-5b7b669de773">on-demand here</Anchor>.

### Download

<Embed typeOfEmbed="pdf" url="https://go.recurly.com/Recurly-Navigate-Presentation-Deck-How-to-Optimize-Dunning-for-Growth.html" href="https://go.recurly.com/Recurly-Navigate-Presentation-Deck-How-to-Optimize-Dunning-for-Growth.html" providerUrl="https://go.recurly.com" providerName="Recurly" />

<HTMLBlock>{`
<style>
  .hidden-content {
    display: none;
  }
</style>

<div class="hidden-content">
Stop the Leak: How to Optimize Dunning for Growth

Dunning Overview


Dunning is the process of collecting on past-due invoices. This is primarily managed through Recurly's retry model and email communications. Subscribers enter the dunning process when a renewal payment fails.
Soft Declines: If a soft decline is received (e.g., insufficient funds), Recurly will send email communications and retry the transaction.
Hard Declines: If a hard decline is received (e.g., invalid account number), email communications will still be sent, but the transaction will generally not be retried.
How Dunning Works in Recurly


Recurly utilizes two main tools for dunning:
Retries: When an invoice fails, it moves into a dunning campaign with a set window length. Recurly's algorithm determines the optimal times to retry the transaction within this window to successfully collect payment.
Email Communications: Businesses have control over when dunning emails are sent to customers. These emails can be customized to align with specific communication strategies.
Configuring Dunning in Recurly


To review and adjust dunning settings within the Recurly app:
Email Templates: Access the Dunning Management templates to view, edit, and customize email content.
Dunning Management Area: This section allows you to control campaign actions, including:
Setting the timing for email sends.
Defining the overall dunning window length.
Choosing whether to expire the subscription or keep the invoice open for manual collection.
Setting up separate dunning campaigns for trials or manual payments if applicable.
Selecting specific email templates to be sent at different points in the dunning window.
Analyzing Dunning Performance


The Dunning campaign section within Recurly's analytics provides insights into:
Overall recovery rate for dunning.
Performance at the invoice and revenue levels.
Comparison of different dunning campaign versions.
Performance of monthly versus annual campaigns.
10 Top Tips for Optimizing Dunning1. Match Emails to Your Branding


It is crucial to build trust with customers when sending payment-related emails. Ensure that emails sent from Recurly match your website branding and other communications. You can set a header and footer style in the email template area of the Recurly app, which will apply to all emails, including dunning, renewal reminders, and subscription change emails.2. Clear Call-to-Action


Emails should have a clear call-to-action, such as "Update your billing information." The action button should be consistent with your website's styling. Including personalized information like the customer's name and the amount due can further enhance trust and clarity.3. Effective Communication Timing


While Recurly's retry model handles transaction retries, you control when emails are sent. Sending regular emails throughout the dunning window is important, as there is a direct correlation between email sends and customers updating their payment information. For monthly subscriptions, a 27-day dunning window is recommended, allowing Recurly's retry model maximum time to work. For yearly, six-monthly, or quarterly plans, a 60-day dunning window is recommended. Avoid a 60-day window for monthly subscriptions to prevent multiple past-due invoices.4. Vary Email Content and Tone


Avoid sending the same email multiple times. Each email should contain different information and leverage Recurly's email parameters to personalize content (e.g., customer name, last four digits of the card, amount due). The tone of emails can also change throughout the dunning window, starting friendly and becoming more urgent towards the end of the campaign.5. Include a Countdown


Clearly show customers how much time they have left before their account closes or subscription expires. This creates urgency and prompts action. Consider including this countdown in email subject lines.6. Remind Customers of Value


In later stages of dunning, remind customers of the value your business provides to prevent voluntary churn. Highlight what they stand to lose, such as:
Unlimited access or downgrades.
Loss of ranking among other members.
Loss of access for group plan members.
Loss of rewards or points.
Loss of access to old pricing models if applicable.
7. Offer Alternative Calls to Action


Beyond updating billing information, consider offering alternative assistance:
Links to support (phone number, live chat).
Coupons for discounts.
Options to pause the service.
8. Optimize Subject Lines


Since customers may only see the subject line, ensure it conveys critical information:
Card declined status.
What they are losing access to.
Call to action (e.g., "Update your payment information").
Countdown to account closure.
9. Multiple Dunning Campaigns


Create different dunning campaigns to target various user groups. For example, separate campaigns for monthly and annual plans, or for different customer segments (e.g., students vs. enterprise clients) to tailor messaging and window lengths.10. Utilize the Right Communication Service


Recurly offers several options for sending dunning emails:
Recurly (Out of the box): Emails are sent on your behalf.
DMARC Setup: Removes "via Recurly" language for improved email validity.
SendGrid Integration: Send emails via your SendGrid account by dropping in your API key.
Mailchimp Integration: Send emails via your Mailchimp account using an API key.
Braze Integration: Create emails in Braze, and Recurly will send the correct events to Braze to trigger email sends, allowing for sophisticated experimentation and tracking.
Sneaky Tip: Payment Overdue Banner in Product


Displaying a payment overdue banner within your product or app can significantly increase engagement. Customers logged into your product have higher trust in the information, and linking directly to the payment method update page can lead to high click-through rates.Sneaky Tip: Recurly Wallet


If your business utilizes Recurly Wallet for backup payment methods, include a mention of this feature in your dunning sequence. Encourage customers to add a backup payment method, potentially with an incentive like a discount on their next bill.Value to Your Business


Implementing these dunning optimization tips can lead to significant improvements in revenue recovery. Many businesses observe a 3% to 5% uplift in recovered revenue by making these changes. Even simple adjustments, such as extending the dunning window, can have a powerful impact. While some businesses worry about providing "free access" during an extended dunning period, webhooks can be used to stop product access while dunning continues.
</div>
`}</HTMLBlock>

<br />

<HTMLBlock>{`
<style>
  .hidden-content {
    display: none;
  }
</style>

<div class="hidden-content">

Recurly NavigateRecurly Product Series
Stop the Leak: How to Optimize Dunning for Growth

Agenda
What is Dunning?
How to understand your current Dunning setup
10 tips for optimizing Dunning
Key takeaways
Dunning OverviewWhat is Dunning?

The dunning cycle is the time period during which Recurly retries soft-declined transactions, and email communications are sent to customers to update their billing information.

Day 0: Subscription Renewal
Payment attempt fails
First email sent
Day 3: 3 Days Later
Second Email Sent
Day 7: 4 Days Later
Third Email Sent
Day 11: 4 Days Later
Fourth email sent
Customer updates credit card
Successful renewal
Who enters the dunning process?
Any subscriber where the initial renewal payment fails with a soft decline will receive dunning communication emails and Recurly's intelligent retry model.
Essentially all invoices that become past-due will enter a dunning campaign.
Hard declines will only receive dunning communication emails; in most cases, the card is not retried.
How Recurly dunning works

While the length of your Dunning window controls how long you have to send emails and how long Recurly can run its Intelligent Retries, these two tools are not tied together. This means a retry will not be triggered by an email being sent. You can control the exact day to send the email, but the retries work independently from an algorithm.
Day 0: Customer Updates = Email #1 to customer
Last Day: Final Email to customer

10 Tips for Optimizing Dunning

1. Make sure your branding matches

It is vital your branding matches other communications.
Recurly Inc: Please update your billing information to ensure your subscription is not interrupted. If you have any questions, please contact us at billings@recurly.com. Thank you, Recurly Inc.
Invoice #44581: Customer Name, Total Due: £161.12
View Online: 123 Street St City, CA 12345 United States
Your Plan: Silver, Next Invoice: Jan 30, 2024
Description: Subtotal
Executive Add On: £14.49, Oct 3-Dec 3, 2023
Setup fee: Silver Plan x3 Nov 3, 2023-Jan 3, 2024: £88.68
Trial period for Silver Sep 3-Dec 3, 2023: £3.48
Header & Footer Design
Email Header: An optional common header that can be applied to all email templates. Update your logo and branding to the header; this will be included in all email templates beyond the Dunning emails.
Email Footer: An optional common footer that can be applied to all email templates. Consider a branded footer design on emails with important/relevant information, such as T&Cs, and contact us links. Using brand font, color, and social media adds credibility.
2. Clear Call to Action (CTA)
Recurly Inc: Please update your billing information to ensure your subscription is not interrupted. If you have any questions, please contact us at billings@recurly.com. Thank you, Recurly Inc.
Invoice #44581: Customer Name, Total Due: £161.12
View Online: 123 Street St City, CA 12345 United States
Your Plan: Silver, Next Invoice: Jan 30, 2024
Description: Subtotal
Executive Add On: £14.49, Oct 3-Dec 3, 2023
Setup fee: Silver Plan x3 Nov 3, 2023-Jan 3, 2024: £88.68
Trial period for Silver Sep 3-Dec 3, 2023: £3.48
It's not too late! Your most recent payment of €168.14 was declined. To continue using the service and access all tools, please update your billing information now.
Update Your Billing Info
Stay Awesome! [Company Name] finance team
3. Get Your Communication RightLeave 4-5 days between each message

Recurly customer examples show that every time a dunning email is sent, there is a direct impact on customer updates. We recommend this type of cadence for Monthly plans.
Recovery Type by Days in Dunning:
Days to Collection (0-20)
account_updater
customer_updates
exp_date
prior_recovery
retry
Giving 27/60 days for the full cycle

One Recurly customer example showed that extending from an 18-day dunning to 28 days allowed for more retries and successful customer updates. For monthly plans, we recommend a 27-day window. For plans longer than 2 months, we recommend a 60-day window.
Recovery Type by Days in Dunning:
Days to Collection (0-28)
account_updater
customer_updates
exp_date
prior_recovery
retry
4. Leverage alternative email messages, changing tone & message in each one

By default, Recurly will send the “Payment Declined” email template for each dunning notification event that is defined in Dunning Management. However, we recommend making each email unique with its own template/language. Below are some common things included:
Consider using the email parameter {{account_hosted_maintenance_url}} to provide the customer with an easy way to update their billing information using the Recurly Hosted Account page.
Confirm the price of the subscription to help validate the legitimacy of the email, e.g., “We're getting in touch to let you know that your most recent payment of £7.99 was declined."
Including the customer's billing information will help assure them this is a real email, “We're having trouble processing your recent payment of £7.99 using Visa ending in ...3385.”
5. During the cycle, inform the customer the exact number of days until their account will be closed.
"5 days left until your subscription expires. We were still unable to process your payment. This could be due to the following reasons: Insufficient funds, Issues with your bank, Expired card."
"2 days left until your subscription expires. Since we are not able to process your payment, we have sent you a couple of emails. Update your payment information within two days to keep access to your subscription and to use our music and sound effects in new content."
6. Remind your customer of the value you provide

At the point where a subscriber is reading your emails but not taking any action, they are sort of choosing to churn. You need to resell them on the value of their subscription and create FOMO!
To keep your annual subscription and not lose your unlimited access
Keep your ranking against other members
To keep your Guided Courses
You and your 5 other users will shortly lose access
Your reward points will be lost!
You are currently on a legacy pricing plan; don't lose access to this exclusive pricing. If you resubscribe in the future, it will be on our new pricing.
7. Alternative CTAs – links to FAQ, social, community, support, customer service

Additionally, if your subscriber is reading your emails but not taking any action, they may need assistance other than just ‘updating their billing information.'

Can you give them a link to your live chat to talk with a support agent? You'd rather have the opportunity to speak with them than just churn. Consider including a coupon code to discount future charges (this will not discount existing past-due invoices) or offering a subscription pause.
Need help? For questions regarding your account or subscription, visit our Help Center.
Visit Help Center
Here to help: If you have any questions or issues, we'd be happy to help. Drop us a line at support@findmypast.com. Support hours: 9 am - 5:30 pm Mon - Fri.
View our FAQs | Contact our support team | Read our privacy_policy. If you've forgotten your password, reset it here.
This email has been sent by a company, registered in England, company no. 4369607. Registered office: [Company Name], Clerk's Court, First Floor, 18-20 Farringdon Lane, London, EC1R 3AU.
8. Email subject line & message should express an increasing sense of urgency with each message

Some customers will send an email immediately when the transaction first failed. An alternative is to wait until the 3rd day to send an email, as the intelligent retries capture the majority of failures in the first 3 days, so some of your customers never even need to know there was a problem.
Frequency
Template Name
Email Subject Line
Day 3
MONTHLY Payment Declined 1st
OOPS! Your credit card has been declined
Day 8
MONTHLY Payment Declined 2nd
Don't lose access to your [Company] Top Tips!
Day 13
MONTHLY Payment Declined 3rd
Action Required: Update your [Company] payment details
Day 18
MONTHLY Payment Declined 4th
URGENT - You will lose access in 10 days
Day 22
MONTHLY Payment Declined 5th
URGENT - You will lose access in 5 days
Day 27
Expired for Non-Payment
Your [Company] Subscription Canceled for Non-payment

1-month subscription example in the UI
Dunning Cycle Summary


Immediately - Hard Decline Email: An extra email sent only to customers whose initial payment attempt fails with a hard decline.
Payment Declined
Day 3 - First Email Sent to the customer 3 days after the initial payment attempt fails.
Monthly Payment Declined 1st
Day 8 - Second Email Sent to the customer 5 days after the first email is sent.
Monthly Payment Declined 2nd
Day 13 - Third Email Sent to the customer 5 days after the second email is sent.
Monthly Payment Declined 3rd
Day 18 - Fourth Email Sent to the customer 5 days after the third email is sent.
Monthly Payment Declined 4th
Day 22 - Fifth Email Sent to the customer 4 days after the fourth email is sent.
Monthly Payment Declined 5th
Day 27 - Sixth Email Sent to the customer 5 days after the fifth email is sent.
Expired for Non-Payment

27 days after the first payment attempt fails, the subscription will expire, and the invoice will fail.1-year subscription example in the UI
Dunning Cycle Summary


Day 3 - First Email Sent to the customer 3 days after the initial payment attempt fails.
Annual Payment Decline 1st
Day 8 - Second Email Sent to the customer 5 days after the first email is sent.
Annual Payment Decline 2nd
Day 13 - Third Email Sent to the customer 5 days after the second email is sent.
Annual Payment Decline 3rd
Day 20 - Fourth Email Sent to the customer 7 days after the third email is sent.
Annual Payment Decline 4th
Day 30 - Fifth Email Sent to the customer 10 days after the fourth email is sent.
Annual Payment Decline 5th
Day 50 - Sixth Email Sent to the customer 20 days after the fifth email is sent.
Annual Payment Decline 6th
Day 60 - Seventh Email Sent to the customer 10 days after the sixth email is sent.
Expired for Non-Payment

60 days after the first payment attempt fails, the subscription will expire, and the invoice will fail.9. Get Your Setup RightConsider adding multiple campaigns, targeting different plans/user groups

Assign different plans to different campaigns. Different campaigns allow you to have more tailored communications with cohorted users. Example campaign splits:
Campaign for monthly plans at 27 days
Campaign for annual plans at 60 days
Friendly language campaign for student-type audience
Formal language campaign for enterprise-type plans
10. Use the right communication service

As standard, Recurly will send emails on your behalf from our email provider. This means the emails your customers receive will have ‘via recurly.com' in the data. We have several options to have more control over your email sending and data insight.
Recurly DMARC: set up your own email domain within the Recurly account.
[Test] Thank You for Subscribing External
Inbox x jason@jason.com via recurly.com to me 2:56 AM (0 minutes a
from: jason@jason.com via recurly.com
to: jbattle@recurly.com
date: Nov 23, 2022, 2:56 AM
subject: Thank You for Subscribing
mailed-by: email.recurly.com
signed-by: recurly.com
security: Standard encryption (TLS) Learn more
Important mainly because you often read messages with this label.
V. @mailinator.co
Sendgrid API key: use your own SendGrid account to process emails.
Mailchimp API key: use your own Mailchimp account to process emails.
Braze: use the Recurly <> Braze integration to create and send emails from Braze, giving you lots of visibility and insight into your performance.
11. Show a 'Payment overdue' banner within your product/app

To increase visibility, it is important to engage with your customers where they are. If they are logging in and using your product, make it easy for them to update payment methods by including a banner with a link. A webhook guide on what to listen for can be shared.
Find my past: Payment not received. We haven't received a payment for this billing period. You will lose access shortly if you don't renew.
Update payment method
Welcome back, Gunnar
Brenda B She/Her
Member since 2020
65-100 years
Last active two weeks ago
M
Sneaky tip number 12! Recurly Back Up Payment (Wallet)

If you have the Recurly backup payment enabled, you should dedicate one of your dunning emails to encourage customers to add a secondary payment method to avoid them falling into Dunning again in the future.
Don't want this to happen again? Make sure you're never locked out of your account again by adding a backup payment method to your account. We'll even give you 10% off your next month's invoice as a thank you!
Add Backup Payment Method
Stay Awesome! [Company Name] finance team
What value can this bring your business?

We typically see a 3–5% uplift in dunning recovery rate once these 10 top tips have been followed.
One merchant got a 12% uplift by enhancing its branding on email design and messaging through the different sets of emails, updating its dunning window, and optimizing the frequency of communications.
Another merchant got an 11% uplift by extending its dunning window by 13 days and adding additional email communications to remind consumers of the value it provides.
A different merchant got an 8% uplift by modifying and extending its dunning window length to adjust its communication frequency and leave more days between each message.
Recap: 10 Tips for Optimizing Dunning
Make sure branding matches other communications.
Leave 4-5 days between each message, giving a 27/60 days for the full cycle.
Leverage alternative email messages, changing tone & message in each one.
During the cycle, inform the customer the exact number of days until their account will be closed.
Remind your customer of the value you provide.
Alternative CTAs – links to FAQ, social, community, support, customer service.
Email subject line & message should express an increasing sense of urgency with each message.
Consider adding multiple campaigns, targeting different plans/user groups.
Use the right communication service.
Show a ‘Payment overdue' banner within your product/app.
Key Takeaways
If nothing else, updating your branding in these email communications is key to building trust with your customer.
The longer the dunning window, the better success Recurly will have in collecting that revenue for you (and you don't have to give away “free” access).
Look at your MRR and calculate what a 3-5% uplift would add to your top-line revenue. Hopefully, that helps get the resourcing you need.
Reference InfoHard vs soft declines
Soft declines mean the bank approved the funds for the payment. However, the payment method failed from a missed step along the process. A server may have taken too long to respond, or a momentary outage at a payment gateway stops the information transfer. The point is, the card number is probably valid. You may try it again. The most common soft decline on renewals is insufficient_funds.
Hard declines are a more significant error. The process did finish completely. However, the credit card was declined by the card issuer or payment processor. Retrying the card number will never work. Instead, another form of payment is in order, or your customer needs to talk to their credit card company. The most common hard decline on renewals is invalid_account_number.
Day 0: Subscription Renewal
Payment attempt fails
First email sent
Day 3: 3 Days Later
Second Email Sent
Day 7: 4 Days Later
Third Email Sent
Day 11: 4 Days Later
Fourth email sent
Customer updates credit card
Successful renewal
</div>
`}</HTMLBlock>

<br />