---
title: Webhooks (JSON & XML)
excerpt: Seamless synchronization with Recurly actions using Webhooks.
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

### Limitations

Webhooks should not be solely relied upon for critical functions. They should be used in conjunction with API responses.

# Definition

Webhooks serve as alerts, notifying your systems and partner applications of actions within Recurly. They are not standalone actionable items. Instead, they should be used in tandem with the Recurly API to ensure data integrity and synchronization. When an event in Recurly triggers a webhook, such as when an account is opened, Recurly will attempt to send this notification to the endpoint(s) you specify.

# Key benefits

* **Real-time updates**: Stay informed on significant events within Recurly as they happen.
* **Enhanced security**: Benefit from HTTP Basic Authentication for secure data transmission.
* **Reduced PCI scope**: Minimize PCI compliance burden with indirect handling of sensitive payment information.
* **Improved error handling**: Enjoy automatic retries for enhanced error resolution.
* **Payload format flexibility**: Choose between JSON and XML payload formats for tailored data handling.

# Key details

## Configuration & security

Recurly takes the security of webhooks seriously. If a webhook delivery fails, it will be retried. Webhooks also support HTTP Basic Authentication, ensuring that the request originates from Recurly's servers. Always refer to the [IP Allowlist documentation](https://docs.recurly.com/docs/ip-allowlist) for the current list of Recurly IPs and configure your endpoint to accept only these IPs.

> **Note**: Recurly does not advocate the use of specific web servers or plugins. However, if using Apache with ModSecurity, you may need to disable rule #990011 in mod\_security to unblock webhooks.

## Webhook details

Each webhook notification is stored for 15 days and is accessible through the application console. This console also provides insights into failure reasons. The timestamp for webhooks is in UTC, but it's translated to your site’s configured timezone when viewed in the application.

## Automatic retries

If Recurly receives an error in response to a webhook, the notification will be retried. After ten failed attempts, Recurly will cease sending the failed notification. The interval between retries is approximately 10 + x\* 2^(x+5) seconds, where x is the current attempt number. This means that the interval between the first few retries will be very short, but will extend exponentially in length as the retry number increases.

## Manual retries

Notifications can be individually retried by clicking on them and then pressing the Retry button.\
Notifications that are paused or failed can be bulk retried by selecting the appropriate button in the Webhook Actions select dropdown.

## Notification types

It is possible to configure / opt-in to only the specific notifications that you would like to receive, on an endpoint by endpoint basis. For example, if you have an endpoint that only needs to receive notifications about new accounts, but is not interested in updated accounts, you can configure that endpoint accordingly.

For a comprehensive list of notification types, please refer to the [Webhooks Developer Docs](https://recurly.com/developers/reference/webhooks/#lifecycle-events).

## Cross site request forgery (CSRF) for Rails applications

For Rails applications that enable forgery protection `protect_from_forgery`, it's essential to disable this protection for the action set up to listen for changes from Recurly.

## Webhook payloads: JSON vs. XML

Webhook payloads can be in JSON or XML formats. Each webhook endpoint can be configured to receive one payload type or the other. Recurly highly recommends the JSON webhooks due to their lightweight nature and alignment with best practices.

## Signature verification

For all JSON payloads, Recurly signs the notification and includes this signature in a recurly-signature request header. This verification provides additional assurance that Recurly sent the notification and it remains unchanged.

# Visit our dedicated developer page

For a deeper dive into Webhooks and their functionalities, please visit our dedicated [developer page](https://recurly.com/developers/reference/webhooks/#webhooks). Here, you'll find comprehensive guides on implementation, modifications, integrations, and more.
