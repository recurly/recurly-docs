---
name: DunningOptimizationWebinar
---
<HTMLBlock>{`
<iframe
  src="https://navigate.recurly.com/on-demand/Dunning-Optimization/"
  width="100%"
  height="600"
  frameborder="0"
  allowfullscreen
  style="border:0;">
</iframe>
`}</HTMLBlock>

<br />

<HTMLBlock>{`
<p style="display: none;">
Stop the Leak: How to Optimize Dunning for Growth

Dunning Overview

Dunning is the process of collecting on past-due invoices. This is primarily managed through Recurly's retry model and email communications. Subscribers enter the dunning process when a renewal payment fails.

Soft Declines: If a soft decline is received (e.g., insufficient funds), Recurly will send email communications and retry the transaction.

Hard Declines: If a hard decline is received (e.g., invalid account number), email communications will still be sent, but the transaction will generally not be retried.

How Dunning Works in Recurly

Recurly utilizes two main tools for dunning:
• Retries: When an invoice fails, it moves into a dunning campaign with a set window length. Recurly's algorithm determines the optimal times to retry the transaction within this window to successfully collect payment.
• Email Communications: Businesses have control over when dunning emails are sent to customers. These emails can be customized to align with specific communication strategies.

Configuring Dunning in Recurly

To review and adjust dunning settings within the Recurly app:
• Email Templates: Access the Dunning Management templates to view, edit, and customize email content.
• Dunning Management Area: This section allows you to control campaign actions, including:
– Setting the timing for email sends.
– Defining the overall dunning window length.
– Choosing whether to expire the subscription or keep the invoice open for manual collection.
– Setting up separate dunning campaigns for trials or manual payments if applicable.
– Selecting specific email templates to be sent at different points in the dunning window.

Analyzing Dunning Performance

The dunning campaign section within Recurly's analytics provides insights into:
• Overall recovery rate for dunning.
• Performance at the invoice and revenue levels.
• Comparison of different dunning campaign versions.
• Performance of monthly versus annual campaigns.

10 Top Tips for Optimizing Dunning

1. Match Emails to Your Branding
   It is crucial to build trust with customers when sending payment-related emails. Ensure that emails sent from Recurly match your website branding and other communications. You can set a header and footer style in the email template area of the Recurly app, which will apply to all emails, including dunning, renewal reminders, and subscription change emails.

2. Clear Call-to-Action
   Emails should have a clear call-to-action, such as "Update your billing information." The action button should be consistent with your website's styling. Including personalized information like the customer's name and the amount due can further enhance trust and clarity.

3. Effective Communication Timing
   While Recurly's retry model handles transaction retries, you control when emails are sent. Sending regular emails throughout the dunning window is important, as there is a direct correlation between email sends and customers updating their payment information. For monthly subscriptions, a 27-day dunning window is recommended, allowing Recurly's retry model maximum time to work. For yearly, six-monthly, or quarterly plans, a 60-day dunning window is recommended. Avoid a 60-day window for monthly subscriptions to prevent multiple past-due invoices.

4. Vary Email Content and Tone
   Avoid sending the same email multiple times. Each email should contain different information and leverage Recurly's email parameters to personalize content (e.g., customer name, last four digits of the card, amount due). The tone of emails can also change throughout the dunning window, starting friendly and becoming more urgent towards the end of the campaign.

5. Include a Countdown
   Clearly show customers how much time they have left before their account closes or subscription expires. This creates urgency and prompts action. Consider including this countdown in email subject lines.

6. Remind Customers of Value
   In later stages of dunning, remind customers of the value your business provides to prevent voluntary churn. Highlight what they stand to lose, such as:
   • Unlimited access or downgrades.
   • Loss of ranking among other members.
   • Loss of access for group plan members.
   • Loss of rewards or points.
   • Loss of access to old pricing models if applicable.

7. Offer Alternative Calls to Action
   Beyond updating billing information, consider offering alternative assistance:
   • Links to support (phone number, live chat).
   • Coupons for discounts.
   • Options to pause the service.

8. Optimize Subject Lines
   Since customers may only see the subject line, ensure it conveys critical information:
   • Card declined status.
   • What they are losing access to.
   • Call to action (e.g., "Update your payment information").
   • Countdown to account closure.

9. Multiple Dunning Campaigns
   Create different dunning campaigns to target various user groups. For example, separate campaigns for monthly and annual plans, or for different customer segments (e.g., students vs. enterprise clients) to tailor messaging and window lengths.

10. Utilize the Right Communication Service
    Recurly offers several options for sending dunning emails:
    • Recurly (out of the box): Emails are sent on your behalf.
    • DMARC Setup: Removes "via Recurly" language for improved email validity.
    • SendGrid Integration: Send emails via your SendGrid account by dropping in your API key.
    • Mailchimp Integration: Send emails via your Mailchimp account using an API key.
    • Braze Integration: Create emails in Braze, and Recurly will send the correct events to Braze to trigger email sends, allowing for sophisticated experimentation and tracking.

Sneaky Tip: Payment Overdue Banner in Product
Displaying a payment overdue banner within your product or app can significantly increase engagement. Customers logged into your product have higher trust in the information, and linking directly to the payment method update page can lead to high click-through rates.

Sneaky Tip: Recurly Wallet
If your business utilizes Recurly Wallet for backup payment methods, include a mention of this feature in your dunning sequence. Encourage customers to add a backup payment method, potentially with an incentive like a discount on their next bill.

Value to Your Business
  Implementing these dunning optimization tips can lead to significant improvements in revenue recovery. Many businesses observe a 3% to 5% uplift in recovered revenue by making these changes. Even simple adjustments, such as extending the dunning window, can have a powerful impact. While some businesses worry about providing "free access" during an extended dunning period, webhooks can be used to stop product access while dunning continues. 
</p>
`}</HTMLBlock>

<br />
