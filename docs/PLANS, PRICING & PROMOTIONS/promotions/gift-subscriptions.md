---
title: Gift subscriptions
excerpt: >-
  Delve into the world of gift subscriptions with Recurly, where gifting is more
  than just a one-time transaction. It's a tool to reach new customers, boost
  engagement and improve your bottom line.
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

# Definition

Gift subscriptions are a method for existing customers to purchase a subscription as a gift for someone else. They can be implemented through two distinct ways on Recurly platform: Gift Cards and Gift Plans. Each option offers a unique way to engage with your customers and expand your business.

# Key benefits

- **Acquisition and retention synergy**: Gift subscriptions can attract new users and improve loyalty among current customers.
- **Revenue expansion**: Tapping into the gift market can open up additional revenue streams.
- **Customer-centric flexibility**: Offers choices between Gift Cards and Gift Subscriptions to suit varied customer preferences.

# Key details

Gift subscriptions, whether through Gift Cards or Gift Subscriptions Plans, provide flexibility, enhance customer acquisition, and drive revenue. 

**Gift Cards** offer a broad range of benefits. They are purchased on the giver's account and redeemed by the recipient when ready. Recurly's <a href="https://docs.recurly.com/docs/gift-cards" target="_blank">Gift Cards</a> support a fully featured gift checkout, redemption, and automated emails to both the giver and recipient.

On the other hand, **Gift Subscriptions Plans** involve upfront payment for a specific period of service. The Gift Subscription starts at the time of purchase, and the merchant handles the messaging and delivery to the recipient. 

Both options offer unique benefits and can be tailored to your business needs, offering flexibility to your customers.

# Configuring gift subscriptions

Setting up Gift Subscriptions on Recurly is straightforward and involves the following steps:

1. **Choose your gift subscription method**: Based on your business model and customer preferences, choose between Gift Cards and Gift Plans.

2. **Implementing gift cards**: Visit the dedicated page on implementing Recurly's Gift Cards. Follow the detailed instructions to configure your Gift Card option effectively.

3. **Implementing gift plans**: Gift Plans are set up as separate plans on your Recurly account. Depending on your requirements, you can set up non-recurring or recurring Gift Plans.

   - For non-recurring gift plans, create a new plan with "1" billing cycle and set the recurring cycle to the length of the gift.

   - For recurring gift plans, either use your regular plans or create a separate plan set to "Auto renew until canceled". 

   [block:image]{"images":[{"image":["https://files.readme.io/ef06d61-image.png",null,null],"align":"center","border":true}]}[/block]

   <br />

4. **Gift delivery**: Since Recurly does not support the collection of gift recipient information, set up an external system to collect this data and send automated emails.

5. **End of gift**: If the Gift Plan is non-recurring, it will end after a specific period. Handle end-of-gift messaging outside Recurly using the `expired_subscription_notification` webhook. Use this webhook to trigger your end-of-gift email to upsell to the gift recipient or the giver.

By following these steps, you can successfully implement Gift Subscriptions on your Recurly platform and leverage them to grow your business.

### Recurring plans

To create a recurring gift plan, you can either use your regular plans, or create a separate plan that is set to "Auto renew until canceled". The benefit of having a separate plan in this case is the ability to track when the plan was purchased "as a gift".

### Gift delivery

Unlike Gift Cards, Recurly does not support the collection of gift recipient information or a custom gift message, or email communications with the gift recipient. You will need to collect this information in your gift checkout and setup automated emails in a system external to Recurly.

### End of gift

If the gift plan is non-recurring, it will come to an end after a specific amount of time. The only email Recurly sends at the end of a gift plan is the Subscription Expired email, and this goes to the account's email address. While this email template can be configured to send based on the plan, it is the same template for all plans, so it will be hard to have gift specific messaging in this email if it is being shared with non-gift plans.

Due to the above, we suggest end of gift messaging be handled outside of Recurly using the `expired_subscription_notification` webhook. If this webhook is received for a gift plan, you can trigger your own end of gift email to upsell the associated gift recipient, or the gifter who's account the gift subscription is on.