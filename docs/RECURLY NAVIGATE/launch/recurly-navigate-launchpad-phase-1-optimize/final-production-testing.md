---
title: 'Section 1: Final Production Testing'
excerpt: >-
  Walk through production testing, a quick final check of your subscription
  payment flow that ensures your site is customer-ready.
deprecated: false
hidden: true
metadata:
  robots: index
next:
  description: >-
    Click "Section 2: Dunning Optimization" to learn how to strategically
    configure your Dunning settings. 
  pages:
    - slug: dunning-optimization
      title: 'Section 2: Dunning Optimization'
      type: basic
---
# Trail Guide: Final Production Testing

It's vital to experience your customer's checkout journey from start to finish before going live — and it gives you a chance to catch potential payment issues along the way.

Watch this quick Navigate Trail Guide to learn how to run a real transaction, issue a refund, and be sure payments are working (so your customers don't find them first). For written reference, you'll find a step-by-step checklist at the bottom of this page.

<HTMLBlock>{`
<div id="trailguide"style="position:relative;overflow:hidden;aspect-ratio:1920/1080"><iframe src="https://share.synthesia.io/embeds/videos/f3384551-b4b2-4ab3-83fa-c8fe6e88c62f" title="Synthesia video player - Navigate Trail Guide: Check the boxes: final production test" allowfullscreen="" allow="encrypted-media; fullscreen; microphone; screen-wake-lock;" style="position:absolute;width:100%;height:100%;top:0;left:0;border:none;padding:0;margin:0;overflow:hidden"></iframe></div>
`}</HTMLBlock>

<HTMLBlock>{`
 {/*
                  Trail Guide: UI Walkthrough

                  This collection of actionable video guides is designed to help you grow, scale, and unlock the full potential of your subscription business with Recurly. This guide will walk you through the Recurly User Interface.

                  Getting Started with Your UI

                  Begin by opening your UI. You will see the dashboard, learn how to identify your site environment, and explore what you will see according to your user access permissions.

                  Your dashboard may look different depending on whether you are in a Sandbox, Development, or Production site. In a Sandbox environment, you will see a "Go Live" checklist. If you are in Production, you will see business insights and performance metrics.

                  At the top of the dashboard, you will find the Recurly Resources button. This is your shortcut to resources like developer documentation, Recurly Connect, and changelogs.

                  User Permissions

                  Check your user permissions. If you do not see all the items in the left-hand navigation, your permissions may be limited. Site Admins can add users and assign different roles, such as access to Analytics or Configuration. Check with your admin if something is missing. If you are the site admin and do not see a feature you need, reach out to support.

                  Site Environments

                  Many businesses use more than one site environment: Production, Development, and Sandbox. To avoid confusion, go to Configuration, then Site Settings, and assign each one a different color theme. This provides an easy visual reminder of where you are.

                  Tools for Subscriber Support and Quick Answers

                  Explore the tools that help you support your subscribers and find answers fast: Recurly's "AI Answers" and the "Customers" section of your UI Navigation Menu.

                  AI Answers

                  AI Answers is Recurly's native AI tool. You can ask it just about anything. For example, if you are curious about tax-inclusive vs. tax-exclusive pricing, or wondering how to retry payments or handle failed transactions, just type in your question. If it cannot find what you need, the Support team is available to help.

                  Customers Section

                  The "Customers section" is a go-to for your support team. If a subscriber has questions about billing, their subscription, or account details, you will use this section. You can search for their account, view transactions, or even manage subscription activity from here.

                  Tools for Performance Improvement and Strategy Optimization

                  Next, explore the tools that help you improve performance and optimize your subscription strategy: Recurly Compass and Analytics (specifically, Benchmarks and Explore).

                  Recurly Compass

                  In your navigation menu, you will see the "Compass" section. Compass offers strategic playbooks to help reduce churn, launch promotions, grow your business with confidence, and much more. These step-by-step guides are based on best practices gathered from many successful subscription businesses.

                  Analytics

                  In Analytics, you will find a wide array of prebuilt dashboards curated for your success, such as how your plans are performing, churn metrics, and much more.

                  Two key tools worth highlighting are:
                  Benchmarks Overview: This gives you a quick snapshot of how your business compares to industry peers.
                  Explore Tool: This is ideal for your internal data team to build and save custom dashboards. If you do not see Explore in your account, the Support team can help you enable it.

                  Account Configuration and Management

                  Finally, let's look at where to configure your account, connect integrations, and manage users.

                  Configuration

                  The "Configuration" section is where you will manage nearly everything in your setup. From pricing plans and coupons to invoice templates, taxes, currencies, shipping, dunning campaigns, payment gateways, and much more. If you are adjusting or expanding your subscription setup, this is your go-to spot.

                  Integrations

                  Beneath Configurations, you will see "Integrations." This is where you will find the third-party tools that Recurly supports. Some are self-installed, but others may require additional setup via documentation or assistance from the Recurly team. Make sure to reach out to support if you need any help.

                  Admin Section

                  The Admin section is where you manage users, roles, SSO settings, and upgrade your Recurly plan when needed.

                  Recurly Support

                  Recurly is always here to help. If you have any questions about your Recurly UI, you can find assistance right inside your Recurly app. Click on Recurly Resources in the top right corner of your user interface for fast access to documentation, or ask our AI Answers tool anything about Recurly. You can also open a quick conversation with the Recurly Chatbot, at the bottom right corner of your screen. As always, documentation and support tickets are available at support.recurly.com.

                  A handy Navigate Resource Guide is available for you to bookmark or download. This is your one-stop document for everything you need to know about Recurly support tools and status updates.
                  */}

  ### 2. Download: Navigate Resource Guide

  Save this guide for an easy reference of where to find support, helpful tools, and more.

  <Embed typeOfEmbed="pdf" url="https://go.recurly.com/recurly_navigate_resource_guide.html" href="https://go.recurly.com/recurly_navigate_resource_guide.html" providerUrl="https://go.recurly.com" providerName="Recurly" />

  {/*Recurly Navigate Resource Guide
                This guide is a handy cheat sheet for finding all your essential Recurly links, tools, and support resources.

                Recurly Support
                Whether you have a quick question or need deeper guidance, Recurly Support is here to help via email, live chat, AI Answers, or the Support Portal.

                Email: support@recurly.com 


                Web Portal [support.recurly.com/hc/en-us]
                Support Tickets are available in the Support Portal) 

                Live Chat: Available in the bottom-right corner of the Support Portal, Recurly app, and documentation pages.

                In-App Tools
                Recurly offers several in-app tools to help guide progress, keep you informed, and answer questions.

                AI Answers: A first stop for support, located at the top of your left-hand user menu.

                Compass: An AI-powered suite embedded throughout the Recurly app, offering insights and playbooks for subscription growth.

                Recurly Connect and Resources
                Check out Recurly's customer hub for insights and innovation, Recurly Connect. You can also find it by clicking the "Recurly Resources" button in the top-right corner of the UI.

                Visit the Recurly Resource Center to explore industry news, product updates, blog posts, and more.

                Stay Up-to-Date
                Recurly offers a variety of newsletters and a 24/7 status page.

                Recurly newsletters: From product updates to event announcements; subscribe here.

                Recurly status page: Get updates.*/}
</Accordion>

<Accordion title="Week 2: Final Production Testing">
  # Week 2: Final Production Testing

  This section will cover production testing, a quick final check of your subscription payment flow.

  It's vital to experience the customer's checkout journey from start to finish before going live — and it gives a chance to catch potential payment issues along the way.

  ## Week 2 Resources

  This two-minute Trail Guide that will guide you through your final production testing steps. Just follow along! If assistance is needed with 3DS compliance or troubleshooting gateway or checkout configurations, links to documentation are provided below

  ### 1. Trail Guide: Final production testing

  <HTMLBlock>{\`
                                      <div style="position: relative; overflow: hidden; aspect-ratio: 1920/1080"><iframe src="https://share.synthesia.io/embeds/videos/ea84740d-7ca0-4aed-a790-07dd95464993" loading="lazy" title="Synthesia video player - Launchpad: Check the boxes: final production test" allowfullscreen allow="encrypted-media; fullscreen; microphone;" style="position: absolute; width: 100%; height: 100%; top: 0; left: 0; border: none; padding: 0; margin: 0; overflow:hidden;"></iframe></div>
  \`}</HTMLBlock>

  {/*
              Navigate Trail Guide
              Launchpad: Check the boxes — Final test in production

              Welcome to Launchpad, part of the Recurly Navigate program! This collection of actionable guides is designed to ignite your Recurly liftoff.

              This program helps optimize and prepare for continued success, boosting subscription businesses from production into transaction, and beyond.

              Today, we'll kick off with a quick final test in production. It's best practice to do this before customers visit your site. After completing these few steps, you are ready for liftoff!

              Open your favorite checkout page, grab your card, and walk through the payment process like a real customer.

              Remember, help is available right inside of your Recurly App. If at any point during this Trail Guide you need additional context, you can use the "AI Answers" tool, click the "Recurly Resources" button, or open the Chatbot. And of course, you can always navigate to support.recurly.com for more options.

              Now let's get started!

              Steps for Final Test in Production:
              • Find your product and head to checkout.
              • Complete the form, making sure to include all required information on the checkout page.
              • Subscribe.
              • Open your Recurly app and make sure the payment was successful.
              • Issue a refund for that transaction to check that it goes through.
              • If you are based in the EU, remember to complete a test payment with 3D Secure to ensure SCA compliance.

              Review of Steps:
              • Subscribe to your own service or product using a real card.
              • Check that the payment was finalized.
              • Issue a refund, making sure it completes.
              • If you are in the EU, test your SCA compliance with 3D Secure.
              • For comprehensive 3D compliance documentation, refer to the relevant resources.

              Troubleshooting Failed Payments:

              Did something fail? The usual culprits are your payment gateway or checkout page. Refer to documentation to help test your gateway and double-check your checkout page. This should help identify the most common issues with configuration. If neither of those solve the problem, your next best step is to open a support ticket.

              Your site is now tested and customer-ready!

              Thanks for joining for this Navigate Launchpad video! The Navigate program helps optimize dunning setup and strategy for maximum revenue recovery.
              */}

  ### 2. Additional documentation

  <Cards columns={4}>
    <Card title="3DS Compliance" href="https://docs.recurly.com/docs/revised-payment-services-directive-psd2">
      **European Merchants**: This comprehensive documentation will help you prepare for 3DS compliance to finalize your production testing.
    </Card>

    <Card title="Test gateway" href="https://docs.recurly.com/recurly-subscriptions/docs/test#/">
      **Effortlessly test your transaction configurations** with Recurly's Test Gateway, ensuring seamless live operations.
    </Card>

    <Card title="Explore checkout" href="https://docs.recurly.com/recurly-subscriptions/docs/checkout#configuration-landing-page">
      Streamline your customers' payment experience with customizable styles, hostnames, and configurations. Get started easily and engage effectively.
    </Card>
  </Cards>
</Accordion>

<Accordion title="Week 3: Dunning Optimization">
  # Week 3: Dunning Optimization

  This section focuses on Dunning, a topic that can have a huge impact on revenue.

  Dunning refers to the process of recovering failed payments and preventing subscriber churn, and is one of the easiest ways to recover revenue, retain customers, and resolve payment issues. Even small improvements to your Dunning flow can drive meaningful results. Start simple, test often, and revisit this as your business grows.

  ## Week 3 Resources

  To help build and fine-tune a Dunning strategy, three quick resources are provided below. You'll find a Navigate Trail Guide that will help you understand how Dunning works, an on-demand webinar to help you optimize your setup, and  a downloadable checklist for an easy-to-follow Dunning optimization reference.

  ### 1. Trail Guide: Dunning done right

  Navigate your Dunning setup, understand how it works, and learn strategic best practices in 5 minutes.

  <HTMLBlock>{\`
                                  <div style="position: relative; overflow: hidden; aspect-ratio: 1920/1080"><iframe src="https://share.synthesia.io/embeds/videos/6c8cf12d-c792-4e62-96fe-618d57e1316a" loading="lazy" title="Synthesia video player - Launchpad: Easy Wins: Dunning Done Right" allowfullscreen allow="encrypted-media; fullscreen; microphone;" style="position: absolute; width: 100%; height: 100%; top: 0; left: 0; border: none; padding: 0; margin: 0; overflow:hidden;"></iframe></div>
  \`}</HTMLBlock>

  {/*
              Launchpad Trail Guide: Easy Wins — Dunning Done Right

              Introduction

              Welcome to Launchpad, part of the Recurly Navigate program! This collection of actionable guides is designed to ignite your Recurly liftoff. This guide will help you optimize your dunning strategy, reducing churn and recovering revenue without adding complexity to your workflow.

              Dunning may not sound exciting, but when done right, it's one of the simplest ways to recover revenue that might otherwise slip through the cracks. Just a few small changes can boost your recovery rates by up to 5%.

              What is Dunning?

              Dunning is the process of automatically retrying failed payments and nudging subscribers to update their billing information. Payment failures happen as a part of running a subscription business. What truly matters is the subsequent action taken. With a smart dunning setup, failed payments can be turned into recovered revenue without manually chasing down customers. These improvements are quick to make and easy to manage.

              How Dunning Works in Recurly

              Dunning in Recurly is powered by two key components:
              • Intelligent Retries: These use machine learning to choose the best time to retry failed payments.
              • Dunning Emails: These reach out to subscribers with helpful reminders.

              Once set up correctly, these components work together to recover revenue and help reduce churn.

              Tips to Improve Recovery Rates

              Here are a few key tips to improve your recovery rates:

              Extend your dunning window.
              By default, the dunning cycle is 10 days. It is recommended to adjust it to 27 days for monthly plans or 60 days for plans longer than 2 months. This allows intelligent retries ample time to work behind the scenes, hand-in-hand with dunning emails.

              Give messages a bit of room to breathe.
              Leaving four or five days between each email gives customers time to take action without overwhelming them.

              Switch up your messaging.
              Don't be afraid to get creative. Each email should have a different tone and focus. Be sure to include helpful information, like the subscription price, and always keep it fresh and friendly.

              Highlight the value of your service.
              Remind subscribers what they will lose if they do not update their payment method.
              • Will they lose access?
              • Will special offers or perks no longer be available?
              • Will legacy pricing no longer apply?
              Be specific and straightforward.

              Using Recurly Compass for Dunning Optimization

              Recurly has a helpful native AI application called Compass. Compass provides a playbook that will instantly update your dunning window if it isn't already optimized.

              To use Compass:
              • Open your Recurly app.
              • Find "Compass" in your left-hand navigation window.
              • Click on "Playbooks."
              • If dunning isn't already up to scratch, you will see the Dunning playbook available to open.
              • Select "Run Play."

              After running the playbook, you can then go into your dunning settings and revamp your messaging.

              Additional Resources

              Recurly is here to help. For a deep dive into dunning strategy, check out the on-demand webinar: "Stop the Leak: How to Optimize Dunning for Growth." Also, make sure to grab the handy checklist to keep tabs on your setup. You can find help and access documentation directly inside your Recurly app, or you can search Compass with any questions you have about dunning.
              */}

  ### 2. On-demand webinar: Stop the Leak: How to optimize Dunning for growth

  Discover proven strategies to reduce involuntary churn and recover lost revenue in this lunch and learn led by Hannah Wheeldon, Strategic CSM at Recurly. Gain actionable insights tailored for DTC businesses, with valuable takeaways for B2B, and learn how to optimize your dunning process for long-term growth.

  <Image align="center" border={true} src="https://files.readme.io/5909cd01ef0dbb50d8aecd11abab104ecbd19f500da5eb2c4727e6f83ea21021-Screenshot_2025-11-17_at_6.28.54_PM.png" />

  <Callout icon="⏯️" theme="default">
    **<Anchor label="Watch On-Demand Here" target="_blank" href="https://recurly.registration.goldcast.io/webinar/a65f472f-9876-4736-9209-5b7b669de773">Watch On-Demand Here</Anchor>**
  </Callout>

  {/*
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
              */}
`}</HTMLBlock>

<br />

<Callout icon="🖐️" theme="default">
  **Find a hiccup?** Double check your **[gateway](https://docs.recurly.com/recurly-subscriptions/docs/test)** and **<Anchor label="checkout" target="_blank" href="https://docs.recurly.com/recurly-subscriptions/docs/checkout#configuration-landing-page">checkout</Anchor>** configurations. If manual troubleshooting doesn't do the trick, Support is your best next step: **<Anchor label="contact support" target="_blank" href="mailto:support@recurly.com">contact support</Anchor>.** 
</Callout>

<br />

# 3DS Compliance

**European Merchants**: The comprehensive documentation below will help you prepare for 3DS compliance and finalize your production testing. 

<Anchor label="https://docs.recurly.com/recurly-subscriptions/docs/revised-payment-services-directive-psd2" target="_blank">https://docs.recurly.com/recurly-subscriptions/docs/revised-payment-services-directive-psd2</Anchor>

<br />

<br />

# Final Production Testing: Step-by-Step

**Use this checklist** to ensure you've taken all of the necessary steps to complete Final Production Testing. If you have any trouble finding what you need, refer back to "**[Trail Guide: Final Production Testing](#trailguide)**" for guidance.

* [ ] **Complete a Live Checkout Test:**

  Choose a live checkout page and purchase a product or subscription using a real card, then confirm the checkout completes successfully.

   
* [ ] **Verify the Payment in Recurly:**

  Log in to your Recurly App and confirm the test transaction shows a successful payment.
* [ ] **Issue and Confirm a Refund:**

  Refund the test transaction in Recurly and confirm the refund processes successfully.
* [ ] **(EU Only) Test 3D Secure / SCA Compliance:**

  Complete a test payment using 3D Secure to confirm your checkout meets SCA requirements.
* [ ] **Troubleshoot if a Step Fails:**

  Review your payment gateway and checkout configuration using the provided documentation, and contact support if issues persist.

## What a way to start!

Your site is now tested and customer ready. Now let's move on to one of the most practical and effective ways to protect your recurring revenue.

<br />
