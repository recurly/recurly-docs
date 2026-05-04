---
title: Account activities export
excerpt: >-
  Track and export a detailed log of all account-level actions in Recurly —
  filter by actor, verb, object, and date to audit changes and understand user
  behavior.
deprecated: false
hidden: false
metadata:
  title: ''
  description: >-
    Dive into Recurly's Custom Fields to personalize your data, enhancing
    account, charge, item, plan, and subscription details for a tailored
    experience.
  robots: index
next:
  description: ''
---
# Overview

The Account Activities export gives you a detailed log of every user action and modification made within customer accounts on your Recurly site. Use it to audit changes, monitor account interactions, and analyze activity patterns across your subscriber base.

You can access account activities at two levels:

* **Account level** — view activity for a specific customer account directly on their account page
* **Site level** — access the full activity log for your entire site via **Admin → Admin Exports**

<Image align="center" border={true} width="75%" src="https://files.readme.io/2ede107c5f42b2c1f59b5cde5991d8278042fc5307e7038bf87727dc1a506f26-image.png" className="border" />

### Required plan

This feature or setting is available to all customers on any Recurly subscription plan.

## Filters

Use these filters on the Explore screen to narrow down your activity data. You can also select or exclude specific fields from your report view.

<Image align="center" border={true} width="75%" src="https://files.readme.io/d2e40d3-image.png" className="border" />

* **Account code** — filter activity to a specific customer account
* **Acted upon object ID** — filter by the unique ID of the object where the activity occurred, such as a specific invoice or transaction. Click any Acted ID in the table to open that object directly in a new tab
* **Acted type** — filter by the type of object the activity occurred on, such as an invoice or a subscription
* **Actor name** — filter by the entity that performed the action — this could be the Recurly Background Bot, an API call, or a specific user
* **Actor type** — filter by the type of actor, such as a user
* **Created at time/date** — filter by the timestamp or date the activity occurred
* **Verb** — filter by the action performed, such as `sent_email`, `renewed`, or `marked_past_due`
* **Metadata** — filter by specific details about the activity, such as a plan name or invoice ID

### Additional filters

For deeper searches, the following additional filters are available:

<Image align="center" border={true} width="75%" src="https://files.readme.io/41d2a24bfe96868189eb68027aa89ce034856578a98e22c352b1ce84e56a7e55-image.png" className="border" />

* **Search entire dataset** — search for specific keywords across all activity data
* **Account activities acted type** — focus on a particular acted type or object
* **Account activities created at date** — define a specific date range for the activities you want to analyze

## Visualization options

Choose how to display your activity data on the Explore screen. The default view is a table, but you can switch to any of the following:

<Image align="center" border={true} width="75%" src="https://files.readme.io/74b5576-image.png" className="border" />

* Table (default)
* Column chart
* Bar graph
* Scatterplot
* Line graph
* Pie chart
* Map
* Single value

Additional visualization options are available by clicking the ellipsis button at the end of the options list.

<Image align="center" border={true} width="75%" src="https://files.readme.io/7d1e84eab93679dc431d50a4fde29bdbeb3e42fb6ada5cbc76e4249db1e91fb6-image.png" className="border" />

## Downloading your data

To download your activity data, click the gear icon in the top-right corner of the Explore screen and select **Download**. You can choose from several file format options.

<Image align="center" border={true} width="75%" src="https://files.readme.io/e0907da3813c8b91a2177b5cece59f9c84205263b27ba01a13a1468aa3e279ed-image.png" className="border" />

<Image align="center" border={true} width="75%" src="https://files.readme.io/5e2363e0a6c17ae93ef300504086dfed3417475ed1037821e5daae08cd8a4d41-image.png" className="border" />

> **Note:** The table visualization displays a maximum of 5,000 rows. For larger datasets, downloading the file ensures you can access and analyze the complete results.

| Id                                                          | Example                                     | Description                                                                                                         | Data type (max size) |
| :---------------------------------------------------------- | :------------------------------------------ | :------------------------------------------------------------------------------------------------------------------ | :------------------- |
| <span id="account_code">account_code</span>                 | 123456789                                   | The unique identifier for the customer account associated with the activity.                                        | varchar(50)          |
| <span id="acted_upon_object_id">acted_upon_object_id</span> | inv-abc123                                  | The unique identifier for the specific object where the activity occurred, such as an invoice or transaction.       | varchar(50)          |
| <span id="acted_type">acted_type</span>                     | invoice                                     | The type of object the activity occurred on, such as an invoice or subscription.                                    | varchar(50)          |
| <span id="actor_name">actor_name</span>                     | [jane@example.com](mailto:jane@example.com) | The entity that performed the activity — this could be the Recurly Background Bot, an API call, or a specific user. | varchar(255)         |
| <span id="actor_type">actor_type</span>                     | user                                        | The type of actor who performed the activity.                                                                       | varchar(50)          |
| <span id="created_at">created_at</span>                     | 2025-01-15T10:30:00Z                        | The timestamp when the activity occurred.                                                                           | datetime             |
| <span id="verb">verb</span>                                 | sent_email                                  | The action performed on the object, such as `sent_email`, `renewed`, or `marked_past_due`.                          | varchar(50)          |
| <span id="metadata">metadata</span>                         | plan_name: Gold                             | Additional details about the activity, such as a plan name or invoice ID.                                           | tex                  |

<br />

<br />
