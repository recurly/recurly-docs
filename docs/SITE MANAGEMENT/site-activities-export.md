---
title: Site activities export
excerpt: >-
  Harness the power of Recurly's Site Activities export to monitor, track, and
  analyze site-level activities, ensuring transparency and control over your
  Recurly site's operations.
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

Recurly's Site Activities export is a comprehensive tool designed to capture and log activities related to your Recurly site. Unlike the Account Activities export, which focuses on customer account-level actions, the Site Activities export zeroes in on changes and actions pertaining to the Recurly site itself. This includes, but is not limited to, plan modifications, site setting updates, user management alterations, and user login activities

### Required plan

This feature is currently available for all merchants on an **Elite Recurly plan, with an Admin role, or an Admin permission** included in their role. To adopt this feature onto your Elite site, you will need to create a support request or contact your CSM to have the feature enabled. This export is also available as an optional add-on for customers on Recurly's Starter and Professional plans. Please reach out to Support or your CSM for more information.

> 🚧 Please Note
>
> The Site Activities export will only display data from activities conducted after the Site Activities feature flag is turned on in your site. It will not reflect historic events that pre-date the log becoming active on your Recurly site.
>
> This export will only support **data retention for 12 months**. After data has been available for 12 months, it will no longer be accessible in this export. If you require data retention past 12 months, it is recommended that you back up your data in your own data system.

> 📘 Recurly Revenue Recognition
>
> At this time we do not log site activities for Recurly RevRec. No revrec-related data will be included in the Site Activities export.

<br />

##

##

### Accessing the site activities export

1. **Go** to the **Admin** section of Recurly.
2. In the left-side panel, **navigate** to the "**Admin Exports**" option,
3. Select "**Site Activities**" from the list of available exports.


<Image src="https://files.readme.io/e5df84fdf53a75223a38673c220185784c0cc6748427ba15b680f0dba6e48f78-image.png" align="center" width="500px" border={true} />


<br />

## Explore interface

The Explorer is divided into three areas:

| Interface Area              | Description                                                                                                                                                               |
| --------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Left panel -Workbook        | Agent Ask natural-language questions about your invoice data. The agent suggests fields and runs queries on your behalf.                                                  |
| Center panel - Field picker | Browse and search the full field catalog. Fields are grouped by topic. Click any field to add it to your active query. Use the In-use filter to see only selected fields. |


<Image src="https://files.readme.io/ef44d9d824e787df7921eee54598bb2844a4af227d5ea719a4f5d9b8c9049047-image.png" align="center" width="700px" border={true} />


### Pre-built sample queries

- **List of site activities** - Returns a row-level list of all site activity events within the active date scope, including actor, action type, affected object, and timestamp.
- **Count of site activities** - Returns a grouped count of site activity events broken down by activity type, giving a quick summary of the most common actions across your site.

### Using the Workbook Agent

The Workbook Agent is the fastest way to start an analysis. Type a question in the text box at the bottom of the left panel and press Enter (or click the send icon).

**Example prompts:**

- “Show me all activity on account ABC123 in the last 14 days”
- “Which actors made the most changes to accounts this month?”
- “List all subscription cancellations performed via API in the past 30 days”
- “Count account activities by type for the current revenue period”
- “Show me all activities where the acted-upon object is a billing info record”

### Available Fields

The fields below are the fields or columns that can be added to your dashboard through filtering. You can decide which of the metadata types below you would like to view for the corresponding entries (objects with activities).

Each entry in the Site Activities export is characterized by specific fields or columns, which can be customized through filtering. Here's a breakdown of the metadata types available:

| Field                                                                           | Example                              | Description                                                                                     | Data type (max size) |
| ------------------------------------------------------------------------------- | ------------------------------------ | ----------------------------------------------------------------------------------------------- | -------------------- |
| <span id="event">event</span>                                                   | `plan`                               | The type of event that triggered the entry in the audit log.                                    | String (—)           |
| <span id="resource_identifier">resource\_identifier</span>                      | `druuid-1234...`                     | The external UUID of the record that was audited. Typically, the druuid of the record\_id.      | String (—)           |
| <span id="resource_type">resource\_type</span>                                  | `plan`                               | The external type of the record that was audited.                                               | String (—)           |
| <span id="target_resource_identifier">target\_resource\_identifier</span>       | `druuid-5678...`                     | The external UUID of the target of the record.                                                  | String (—)           |
| <span id="target_resource_type">target\_resource\_type</span>                   | `site`                               | The external type of the target of the record.                                                  | String (—)           |
| <span id="principal_resource_identifier">principal\_resource\_identifier</span> | `user@example.com` or `api-key-name` | The external identifier of the principal. This could be the email or API key name/masked value. | String (—)           |
| <span id="principal_resource_type">principal\_resource\_type</span>             | `user` or `api_key`                  | The external type of the principal.                                                             | String (—)           |

## Entries

The table below showcases the change activities and their corresponding objects that Recurly logs and makes available through this report. Recurly continues to expand the objects captured within this report. If there are any Recurly objects not represented below but you wish to obtain their event action, please contact your CSM for further guidance.

**Plan events are supported in both the Admin UI and API v3.**

| Event                                 | Actions                                  | Trigger                                                                                                                                                                                       |
| ------------------------------------- | ---------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| login                                 | success                                  | Successful login from a user to the merchant site                                                                                                                                             |
| user                                  | create, delete, update                   | A user is added, roles updated or removed from the site                                                                                                                                       |
| role                                  | create, update, delete                   | A new role is created, updated or removed from a site                                                                                                                                         |
| account\_updater                      | enable, disable, update                  | Account updater settings changed on the site.                                                                                                                                                 |
| analytics\_settings                   | update                                   | The analytics dashboard settings are updated.                                                                                                                                                 |
| coupon\_settings                      | update                                   | The site-wide coupon settings are updated.                                                                                                                                                    |
| currency\_settings                    | update                                   | Currencies the site has enabled are updated.                                                                                                                                                  |
| hosted\_page\_settings                | update                                   | The site-wide HPP settings are updated.                                                                                                                                                       |
| hosted\_account\_management\_settings | update                                   | The site-wide HAM settings are updated.                                                                                                                                                       |
| invoice\_settings                     | update                                   | The site-wide invoice settings are updated.                                                                                                                                                   |
| tax\_settings                         | update                                   | The site-wide tax settings are updated.                                                                                                                                                       |
| custom\_field\_definition             | create, update, delete                   | A custom field definition is added, updated or removed from a site.                                                                                                                           |
| avalara\_credentials                  | create, update, delete                   | Avalara credentials are added, updated or removed from a site. Schema notes: Excludes the system marking credentials invalid. User updates only.                                              |
| plan                                  | create, update, delete                   | A plan is added, updated or removed from a site. **Supported in Admin UI and API v3.** Schema notes: Excludes plan email configuration. Needs update to use dunning campaign code.            |
| add\_on                               | create, update, delete                   | An add on is added to a plan, updated or removed from a plan. **Supported in Admin UI and API v3.**                                                                                           |
| measured\_unit                        | create, update, delete                   | A measured unit is added, updated or removed from a site.                                                                                                                                     |
| coupon                                | create, update                           | A coupon is added, updated or removed from a site. **Admin UI only.**                                                                                                                         |
| coupon                                | generate\_codes                          | Generate more unique coupon codes. **Admin UI only.**                                                                                                                                         |
| coupon                                | expire, restore                          | A coupon is manually expired or restored on a site. **Admin UI only.**                                                                                                                        |
| unique\_coupon\_code                  | expire, restore                          | A unique coupon code is manually expired or restored on a site. **Admin UI only.**                                                                                                            |
| email\_settings                       | update                                   | Email settings for a template are updated.                                                                                                                                                    |
| email\_templates                      | create, update, delete, reset            | Email templates are created, updated, deleted or reset. Schema notes: Excludes audience selector and attachment changes.                                                                      |
| payment\_gateways                     | create, update, delete                   | A payment gateway is created, updated or removed from a site. Schema notes: Excludes changing default gateways.                                                                               |
| dunning\_campaign                     | create, update, disable, enable          | A dunning campaign is added, updated, disabled or re-enabled on a site. **Admin UI only.** Schema notes: Excludes auditing plans dunning campaign id when changed.                            |
| dunning\_campaign\_settings           | update                                   | The site wide dunning campaign settings are updated. **Admin UI only.**                                                                                                                       |
| item                                  | create, update, disable, enable          | An item is created, updated, disabled or re-enabled on a site. **Supported in Admin UI and API v3.**                                                                                          |
| entitlement                           | create, update, delete                   | An entitlement configuration is created, updated or removed from a site.                                                                                                                      |
| business\_entity                      | create, update, delete                   | A business entity is created, updated or removed from a site. **Admin UI only.** Schema notes: Does not include auditing the creation of new Recurly revenue recognition GL accounting codes. |
| site\_settings                        | update                                   | General Site configuration settings are updated.                                                                                                                                              |
| invoice\_template                     | create, update                           | An invoice template is created or updated.                                                                                                                                                    |
| webhook\_endpoint                     | create, update, delete, pause, resume    | A Webhooks notification endpoint was created, updated, deleted, paused or resumed on a site. Schema notes: Excludes changing pre-renewal webhook settings.                                    |
| api\_key                              | create, view, update, regenerate, delete | A private API key is added, details are updated, it is regenerated or deleted on a site.                                                                                                      |
| public\_key                           | regenerate                               | The public key has been regenerated on a site.                                                                                                                                                |
| shipping\_method                      | create, update, delete                   | A shipping method is created, updated or deleted on a site. **Admin UI only.** Schema notes: Excludes Recurly revenue recognition fields.                                                     |
| apple\_pay\_settings                  | update                                   | Apple Pay configuration settings are updated on a site. Schema notes: Excludes managed Apple Pay domains.                                                                                     |

### Creating a new report

1. Browse and search the full field catalog. Fields are grouped by data topic.&#x20;
2. Click any field to add it to your active query. Use the In-use filter to see only selected fields.
3. Toggle between Results (table view), Chart (visualization), or both.&#x20;
4. Use the Options tab to configure axes, grouping, and chart type.&#x20;

### Filtering your data

1. **Standard Filters:** Drag and drop any field into the Filters section of the query builder, or click the drop-down/actions menu next to the field header in your data view and select Filter.
2. **Filtered Measures:** To create a measure that is specifically tied to one dimension (e.g., Acted Type by Actor Name), create a pivot table with your target metric and the dimension. Right-click the measure under a specific pivot value and select Create filtered measure.&#x20;


<Image src="https://files.readme.io/c9c6cc6ed76b747ad36ebf7b8dcbfc671d465913f74963e969242f2ef9ca02a1-image.png" align="center" width="500px" border={true} />


### Downloading your data

To download your activity data, from the menu, select **Tab** - **Download**. You can choose from several file format options including CSV, Excel and JSON.


<Image src="https://files.readme.io/5aa93a8e225a22e569fb3a8783b6d661992709e84c8174b4956266cfaa70e175-image.png" align="center" border={true} />



<Image src="https://files.readme.io/4e2e34d9b6f474f1bdb99ef5d92c8be32a1ea64d7777f67023eac0e4d51fc555-image.png" align="center" width="300px" border={true} />


<br />
