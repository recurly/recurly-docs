---
title: Postpone subscription
excerpt: >-
  Master the art of subscription flexibility with Recurly's 'Postpone' feature,
  ensuring tailored billing cycles for your clients
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

The 'Postpone Subscription' feature in Recurly offers a solution to adjust a customer's current billing cycle, either by extending or shortening it. This comes handy when the billing date needs modification from its initial anniversary.

# Key benefits

* **Billing flexibility:** Easily adjust billing cycles, meeting both business and customer needs.
* **Cost-effective adjustments:** Instead of creating new subscription plans or making complex changes, simply postpone to align with specific dates.
* **Enhanced customer experience:** Provide customers with tailored billing solutions without affecting their subscription services.
* **Streamlined administrative processes:** Both API and Admin Console support make implementation smooth.
* **Retention strategy:** Can cater to special requests or situations where a customer needs short-term changes, increasing loyalty.

# Key details

Postponing a subscription essentially changes the subscriber's next bill date. Until the postponed date is reached, no further subscription invoices are generated. An essential aspect to remember is that when a subscription gets postponed, the future billing dates will permanently adjust in line with the new date.

For instance, a yearly subscription running from May 15, 2016, to May 20, 2017, when postponed to December 10, 2016, will now cover May 15, 2016, to December 10, 2016. Following this, the new billing cycle will start from December 10, 2016, to December 10, 2017.

**Note:** If any immediate changes are made post-postponing, they could potentially prorate more than the standard 100%. It's crucial to be aware of this, as it can lead to charges and credits that might surpass the initial per unit price.

Recurly’s feature to postpone doesn't invoice the customer for any extra time added. However, if an immediate change is executed after postponement, the system assumes the customer has already been charged for the extended period and credits them accordingly.

## **Postpone via admin console**

```
  a. Access the desired customer's account.
  b. View the relevant subscription. Within the subscription details, locate the 'Current Period.'
  c. Next to 'Current Period', click on the 'Change' hyperlink.
  d. Input the date when you'd like the current period to conclude and set the new bill date.
```

## **Postpone via API**

1. If using the V2 API, employ the 'Postpone Subscription' call. [Learn more here](https://dev.recurly.com/docs/postpone-subscription).
2. If you're operating through the V3 API, the 'Modify Subscription' call should be your go-to. [Discover more about this here](https://developers.recurly.com/api/v2019-10-10/index.html#operation/modify_subscription).

# Important remarks

* **Calendar Billing Note:** Adjusting a single subscription's bill date doesn't simultaneously modify all subscription bill dates for that account. For instance, if an account's subscriptions uniformly bill on the 15th of each month, changing one won't impact the rest.
* **Alternative to Postponement:** Should you aim to skip several billing cycles without altering the regular billing date, consider the 'Pause Subscription' feature instead. [Read more about pausing subscriptions](https://docs.recurly.com/docs/pause-subscription).
