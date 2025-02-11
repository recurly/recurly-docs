---
title: Renewal reminder and trial ending notifications
excerpt: >-
  Keep your customers informed and engaged with timely renewal reminders and
  trial ending notifications, ensuring a seamless subscription experience.
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

Renewal reminder and trial ending notifications are automated emails sent to subscribers to inform them of upcoming subscription renewals, trial period endings, and payment method expirations. These notifications are critical for maintaining communication with your customers and ensuring compliance with various payment and regional regulations.

# Key benefits

* **Improved customer engagement:** Timely reminders increase transparency and trust, keeping customers informed about their subscription status.
* **Compliance adherence:** Ensures your business complies with legal and payment brand requirements for subscription renewals and changes.
* **Reduced churn:** Proactive communication helps prevent service interruptions and encourages action on expired payment methods.
* **Enhanced experience:** Personalized notifications improve the customer experience, reinforcing the value of your service.

# Key Details

* **Improved customer engagement:** Timely reminders increase transparency and trust, keeping customers informed about their subscription status.
* **Compliance adherence:** Ensures your business complies with legal and payment brand requirements for subscription renewals and changes.
* **Reduced churn:** Proactive communication helps prevent service interruptions and encourages action on expired payment methods.
* **Enhanced experience:** Personalized notifications improve the customer experience, reinforcing the value of your service.\
  Key Details   

# Changing the renewal reminder date

Adjusting the renewal reminder date in your Recurly subdomain affects all subscriptions globally. If you extend the reminder period—changing it from, for example, 5 to 15 days—subscriptions set to renew sooner than the new period may not get a reminder. For subscriptions renewing in less time than the adjusted period, Recurly suggests directly contacting those customers to reduce potential churn.

## Renewal reminder emails

Renewal reminders are crucial for keeping customers informed about their upcoming subscription renewals. This feature is versatile, allowing activation across all plans, with the option to disable it for specific plans as needed. You can schedule these emails to be sent anywhere from 1 to 180 days before a subscription is due to renew, tailoring the timing to fit your business model.

### Different Types of Renewal Reminders

* **Term Renewal Reminder**: This email serves as a notice for upcoming subscription renewals, with a configurable lead time of 1 to 180 days. Sending such reminders may be mandated by regional laws or card brand agreements.
* **Bill Date Reminder**: Aimed at reminding customers of their next billing date, this reminder can also be scheduled between 1 and 180 days in advance. Like term renewal reminders, these may be required by law in various jurisdictions.
* **Annual Reminder**: Sent yearly from the start of a customer's subscription, annual reminders are essential for compliance in regions with specific mandates for such notifications. They are especially relevant for subscriptions with term lengths of less than one year.
* **Mastercard Reminder Template**: Exclusively for customers using Mastercard, this template complies with Mastercard’s specific guidelines, including timing and content, such as cancellation instructions.

**Per Mastercard’s regulations:**

1. You can configure your emails to be sent prior to the customer’s bill date.
2. You will wish to ensure that your email includes clear instructions for how the customer can cancel their subscription.\
   If multiple renewal reminder emails are scheduled for the same days prior, then the Mastercard template will take precedence over other renewal reminder templates.

* **Ramp Price Change Renewal Notification**: Notifies customers about upcoming changes in pricing at the start of new ramp intervals. This template, part of the Subscription Renewal templates, can be tailored to include specific information like the start date and price of the next ramp interval. If scheduled for the same day as other reminders, it is prioritized.

### Payment method-specific reminders

* **SEPA Payment Method**: This reminder, sent ahead of the bill date, caters to customers with SEPA as their payment method, adhering to SEPA's unique requirements.
* **BACS Payment Method**: This reminder, sent ahead of the bill date, caters to customers with BACS as their payment method, adhering to BACs' unique requirements.
* **Expired Credit Card Template**: Alerts customers in advance if their credit card on file has expired or will expire by the next billing cycle, urging them to update their payment information.

## Trial ending emails

Trial ending emails are designed to proactively inform customers when their free trial period is nearing its end, encouraging them to transition to a paid subscription. This feature can be specifically activated for each subscription plan, ensuring that reminders are only sent out where they're most relevant.

### Activation and customization

* To enable trial ending emails, select the "Send Trial Ending Emails?" option when creating or editing a subscription plan. This ensures subscribers are made aware their trial period is ending, prompting them to consider continuing with a paid plan.
* The timing for these emails is set to automatically send reminders 3 days before the end of a trial. For custom trial periods, the length must be at least 4 days to trigger the sending of a trial ending email.
* The "Trial Ending" email template is customizable within the Email Templates section of Recurly. This allows you to align the message with your brand voice and specific messaging strategies, ensuring a consistent experience for your customers.

# Prerenewal Webhook Notifications

Prerenewal webhook notifications extend the functionality of the renewal reminders by integrating them with your wider ecosystem. Similar to the email notifications, each renewal notification type can also trigger a webhook. These webhooks allow for a default setting, which you can customize to align with your preferred timing, specified in days before a subscription's renewal.

Utilize these webhook notifications to initiate actions beyond email alerts, such as triggering emails through an external provider or instigating other system events relevant to an upcoming renewal.

## Configuring webhook notifications

To set up your prerenewal webhook notifications globally:

1. Go to the Recurly App and find the webhook notification configuration section.
2. Here, you'll find options to adjust the default settings for prerenewal notifications to suit your operational requirements. These adjusted defaults will then apply across all endpoints that utilize prerenewal notification events.

For a deeper dive into webhook notifications, including prerenewal notifications, and how to best implement them within your workflow, refer to our comprehensive [webhook developer documentation](https://recurly.com/developers/reference/webhooks/#prerenewal-notifications).

Below is an example of the Prerenewal Default Webhook Configuration in the Recurly App, illustrating how these settings can be adjusted to meet your specific needs.

<Image align="center" className="border" width="50% " border={true} src="https://files.readme.io/1c1469c-Prerenewal_Default_Webhook_Configuration.png" />

<br />

<Image align="center" className="border" width="50% " border={true} src="https://files.readme.io/b8d7cb2-Prerenewal_Notification_Events.png" />

# Important considerations

* **Adyen Hosted Payment Page Users:** For those using Adyen Hosted Payment Pages (HPP), it's important to note that Recurly cannot access certain required information, such as the mandate ID. Therefore, you'll need to manage the sending of renewal reminder emails yourself to comply with specific requirements.
* **Email Template Prioritization:** When both a general Renewal Reminder and a specific template for an Expired Card or SEPA / BACS are enabled, the system prioritizes the email that prompts the customer to take immediate action. This ensures that critical information, particularly regarding payment method updates, is communicated effectively.

If an expired payment method is on file, or a SEPA / BACS payment method is used, the corresponding template (Expired Card, SEPA, or BACS) will be sent instead of a standard Renewal Reminder, emphasizing the need for the customer to update their payment details to avoid interruption in service. This approach helps in mitigating potential subscription discontinuity and enhances customer experience by keeping them well-informed about their subscription status and any required actions.

# FAQs

#### What happens when the trial\_ends\_at date is updated via API to extend the trial?

If you update the trial\_ends\_at date through the API to extend the trial period, and the new end date is more than 3 days away, the trial ending email will not be sent until it's within the 3-day reminder window. This ensures that reminders are timely and relevant to the updated trial period.

### Will renewal reminders be sent for subscriptions with a future start date?

Yes, renewal reminders will be sent for subscriptions that have a future start date, provided that this date is set at least 2 days in advance. This allows for adequate notice to customers about upcoming renewals, even for subscriptions not immediately active.

### What happens if there is no email address on file for a customer?

In cases where a customer's email address is not on file, Recurly will use the site's default email settings. However, it's recommended as a best practice to always collect and pass the customer's email address to Recurly. You have the flexibility to configure both "email to" and "cc email to" addresses in the email templates section to ensure communications reach the intended recipients.

### Is it possible to set up renewal reminders and trial ending emails through the API?

Currently, configuring renewal reminders and trial ending emails can only be done via the Recurly admin console. The ability to manage these settings through the API is something being considered for future development to enhance flexibility and automation capabilities.

### If I disable the renewal reminders or trial ending emails within the Email Templates section of Recurly, will that stop the emails from going out?

Yes, disabling email templates will stop emails from being sent.
