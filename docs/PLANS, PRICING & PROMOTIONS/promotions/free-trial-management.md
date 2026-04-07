---
title: Free trial management
excerpt: >-
  Attract potential customers by offering free trials with Recurly's Free Trial
  Management. Test drive your offerings without any obligation, providing an
  efficient way to increase user acquisition and engagement.
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

Free trials can be defined within Recurly's system in terms of days or months, with automatic transition to a paid subscription at the end of the trial period. Subscriptions can be canceled anytime before the trial ends, preventing any charges. With options to require or bypass billing information for the trial period, Recurly provides a flexible and user-friendly interface for both businesses and customers.

# Key benefits

* **Boost user acquisition:** Offering a free trial helps attract more customers by allowing them to test your product or service risk-free.
* **Increase engagement:** Users who sign up for a free trial are more likely to engage with your product or service, improving user experience and satisfaction.
* **Flexible billing:** Choose to require or bypass billing information during the trial period based on your business model.
* **Automate transition:** Automatic transition to paid subscriptions at the end of the trial period helps in seamless conversion and enhances user experience.
* **Custom notifications:** Automatically notify your customers when their free trial is about to end, improving communication and transparency.

# Key details

## Free trials

<Image align="center" border={true} width="80% " src="https://files.readme.io/b3456541efd2938c0607bb440d3b5176b6884337f18b628a7f6ff86037ae4833-image.png" className="border" />

Recurly's plans offer the flexibility to include an optional trial period, which can be defined in either days or months. This allows potential customers to try out your service before committing to a paid subscription. At the end of the trial period, the subscription will automatically convert to a paid one, facilitating a smooth transition for your subscribers.

Without a trial period, a new subscription request will incur the full charge for the subscription's billing period. However, when a trial period is in place and billing information is collected, Recurly ensures secure payment validation by authorizing a $1.00 charge on the subscriber's credit card, which is immediately voided.

Additionally, Recurly offers the option to set up free trials using coupons. This can be a strategic move to attract more subscribers by offering a risk-free trial period. To learn more about leveraging free trials through coupons, <a href="https://docs.recurly.com/docs/coupons" target="_blank">visit this page</a>.

However, if a subscription is canceled before the end of the trial period, no charges will be applied. The subscription will simply expire at the end of the trial. Conversely, if the trial period ends without cancellation, the subscription will be billed normally.

## Subscription and Period Term Dates

It's important to note that adding a free trial to a plan will extend the subscription term. For instance, an annual plan billed monthly with a 30-day free trial will result in a 13-month subscription term.

If a subscription is created with a start date in the past and it has a free trial and the trial dates are in the current billing period, then the subscription is in a free trial and the trial end date and subscription terms are calculated from the start date.

If a subscription is created with a start date in the past and it has a free trial and the trial dates are prior to the current billing period, then the sub renewal dates reflect the start date plus trial length.

### Cardless free trials

Recurly provides the option to either require or bypass billing information for free trials at the plan level. This setting is accessible when creating a plan with a trial period. Please note that when a plan has a set up fee, the fee is charged immediately. If you don't want to require billing information for your free trial, a coupon, gift card, or other credits can be used to cover the cost of the setup fee, allowing you to bypass the billing information step.

<Image align="center" border={true} width="80% " src="https://files.readme.io/b8694653d92f04020cd46c0f62647a3f4ba7ac55375c4cb00628dd00ba5ac2ab-image.png" className="border" />

Free trial coupons can be used on any plan. However, the plan's billing requirement setting determines if the billing information needs to be presented.

If you change your free trial settings, the new settings will only apply to new sign-ups. For subscriptions that start with a free trial as a future date, the billing settings at the time the subscription starts will be used.

## Transition from trial to subscription

When the trial ends and the subscription payment isn’t fulfilled, it may enter the dunning process if a trial dunning campaign is configured, or if a customer has not added their billing information at the time of renewal, the subscription will **expire**. However, exceptions are made when the invoice at renewal is $0 or when the plan fee is set to $0; in these cases, the subscription can renew without requiring the customer's billing information.

## Trial ending email

The Trial Ending email is a valuable tool designed to notify your customers 3 days before the conclusion of their free trial. It is highly recommended to enable this feature, particularly for free trial plans that do not mandate billing information at the point of sign-up.

> This practice aligns with certain card brand regulations that require clear communication with customers as their trial period approaches its end. Some card brands have mandates to communicate with customers when their trial is ending.

## Checkout and Hosted payment page support

If you use Recurly's either Checkout or Hosted payment pages, you will have the flexibility to require or bypass billing information for your subscriptions with free trials.

<Image align="center" border={true} width="80% " src="https://files.readme.io/df31c3a-image.png" className="border" />
