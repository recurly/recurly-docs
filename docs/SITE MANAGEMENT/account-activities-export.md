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

### Required plan

This feature or setting is available to all customers on any Recurly subscription plan.

# Accessing user exports

1. **Go** to the **Admin** section of Recurly.
2. In the left-side panel, **navigate** to the "**Admin Exports**" option,
3. Select "**Account Activities**" from the list of available exports.

You can access account activities at two levels:

- **Account level** — view activity for a specific customer account directly on their account page
- **Site level** — access the full activity log for your entire site via **Admin → Admin Exports**


<Image src="https://files.readme.io/e1c4a16aba0142612cd6333c0ae95b3bcbba27d5d6f49dd7d89be67ee9126e61-image.png" align="center" width="600px" border={true} />


## Explore interface

The Explorer is divided into three areas:

| Interface Area              | Description                                                                                                                                                                                                                  |
| --------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Left panel -Workbook        | Agent Ask natural-language questions about your invoice data. The agent suggests fields and runs queries on your behalf.                                                                                                     |
| Center panel - Field picker | Browse and search the full field catalog. Fields are grouped by topic. Click any field to add it to your active query. Use the In-use filter to see only selected fields.                                                    |
| Right panel - results area  | Toggle between Results (table view), Chart (visualization), or Both. Use the Options tab to configure axes, grouping, and chart type. Click Preview to run a sample query and verify your field selection before committing. |


<Image src="https://files.readme.io/151e9a40bf36f6e8fc2438ae06a4ad5511128db459e51697062f0d77d3dfe510-image.png" align="center" border={true} />


### Pre-built sample queries

- **List of activities** - Returns a row-level list of all account activity events within the active date scope, including actor, action type, affected object, and timestamp.
- **Count of activities** - Returns a grouped count of activity events broken down by activity type, giving a quick summary of the most common actions across your accounts.

### Using the Workbook Agent

The Workbook Agent is the fastest way to start an analysis. Type a question in the text box at the bottom of the left panel and press Enter (or click the send icon).

**Example prompts:**

- “Show me all activity on account ABC123 in the last 14 days”
- “Which actors made the most changes to accounts this month?”
- “List all subscription cancellations performed via API in the past 30 days”
- “Count account activities by type for the current revenue period”
- “Show me all activities where the acted-upon object is a billing info record”

### Available Fields

- **Account code** — filter activity to a specific customer account
- **Acted upon object ID** — filter by the unique ID of the object where the activity occurred, such as a specific invoice or transaction. Click any Acted ID in the table to open that object directly in a new tab
- **Acted type** — filter by the type of object the activity occurred on, such as an invoice or a subscription
- **Actor name** — filter by the entity that performed the action — this could be the Recurly Background Bot, an API call, or a specific user
- **Actor type** — filter by the type of actor, such as a user
- **Created at time/date** — filter by the timestamp or date the activity occurred
- **Verb** — filter by the action performed, such as `sent_email`, `renewed`, or `marked_past_due`
- **Metadata** — filter by specific details about the activity, such as a plan name or invoice ID

### Creating a new report

1. Browse and search the full field catalog. Fields are grouped by data topic.&#x20;
2. Click any field to add it to your active query. Use the In-use filter to see only selected fields.
3. Toggle between Results (table view), Chart (visualization), or both.&#x20;
4. Use the Options tab to configure axes, grouping, and chart type.&#x20;

### Filtering your data

1. **Standard Filters:** Drag and drop any field into the Filters section of the query builder, or click the drop-down/actions menu next to the field header in your data view and select Filter.
2. **Filtered Measures:** To create a measure that is specifically tied to one dimension (e.g., Acted Type by Actor Name), create a pivot table with your target metric and the dimension. Right-click the measure under a specific pivot value and select Create filtered measure.&#x20;


<Image src="https://files.readme.io/05aeff02dce97d132b08e141ab868faad8ef6930bfbe0d731b0d3a91e242cd62-image.png" align="center" width="500px" />


### Downloading your data

To download your activity data, from the menu, select **Tab** - **Download**. You can choose from several file format options including CSV, Excel and JSON.


<Image src="https://files.readme.io/874a53d85998063a2ffc63b6f02421aee951ce68b58eab805d340e0d900f54c6-image.png" align="center" border={true} />


![]()


<Image src="https://files.readme.io/5eeb0615dbbaa65e7a6566580fc02a36aef6bc8f232a8543b33977c284b805f0-image.png" align="center" width="300px" border={true} />


<br />

> **Note:** The table visualization displays a maximum of 5,000 rows. For larger datasets, downloading the file ensures you can access and analyze the complete results.

| Id                                                             | Example                                     | Description                                                                                                         | Data type (max size) |
| :------------------------------------------------------------- | :------------------------------------------ | :------------------------------------------------------------------------------------------------------------------ | :------------------- |
| <span id="account_code">account\_code</span>                   | 123456789                                   | The unique identifier for the customer account associated with the activity.                                        | string               |
| <span id="acted_upon_object_id">acted\_upon\_object\_id</span> | inv-abc123                                  | The unique identifier for the specific object where the activity occurred, such as an invoice or transaction.       | string               |
| <span id="acted_type">acted\_type</span>                       | invoice                                     | The type of object the activity occurred on, such as an invoice or subscription.                                    | string               |
| <span id="actor_name">actor\_name</span>                       | [jane@example.com](mailto:jane@example.com) | The entity that performed the activity — this could be the Recurly Background Bot, an API call, or a specific user. | string               |
| <span id="actor_type">actor\_type</span>                       | user                                        | The type of actor who performed the activity.                                                                       | string               |
| <span id="created_at">created\_at</span>                       | 2025-01-15T10:30:00Z                        | The timestamp when the activity occurred.                                                                           | datetime             |
| <span id="verb">verb</span>                                    | sent\_email                                 | The action performed on the object, such as `sent_email`, `renewed`, or `marked_past_due`.                          | string               |
| <span id="metadata">metadata</span>                            | plan\_name: Gold                            | Additional details about the activity, such as a plan name or invoice ID.                                           | string               |

<br />

<br />
