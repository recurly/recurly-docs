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

# Key details

## Field definitions

The fields below are the fields or columns that can be added to your dashboard through filtering. You can decide which of the metadata types below you would like to view for the corresponding entries (objects with activities).

Each entry in the Site Activities export is characterized by specific fields or columns, which can be customized through filtering. Here's a breakdown of the metadata types available:

| Field                                                                         | Example                              | Description                                                                                     | Data type (max size) |
| ----------------------------------------------------------------------------- | ------------------------------------ | ----------------------------------------------------------------------------------------------- | -------------------- |
| <span id="event">event</span>                                                 | `plan`                               | The type of event that triggered the entry in the audit log.                                    | String (—)           |
| <span id="resource_identifier">resource_identifier</span>                     | `druuid-1234...`                     | The external UUID of the record that was audited. Typically, the druuid of the record_id.       | String (—)           |
| <span id="resource_type">resource_type</span>                                 | `plan`                               | The external type of the record that was audited.                                               | String (—)           |
| <span id="target_resource_identifier">target_resource_identifier</span>       | `druuid-5678...`                     | The external UUID of the target of the record.                                                  | String (—)           |
| <span id="target_resource_type">target_resource_type</span>                   | `site`                               | The external type of the target of the record.                                                  | String (—)           |
| <span id="principal_resource_identifier">principal_resource_identifier</span> | `user@example.com` or `api-key-name` | The external identifier of the principal. This could be the email or API key name/masked value. | String (—)           |
| <span id="principal_resource_type">principal_resource_type</span>             | `user` or `api_key`                  | The external type of the principal.                                                             | String (—)           |

> **Note:** Data type and max size vary by implementation. This table documents the expected format at a high level.

## Entries

The table below showcases the change activities and their corresponding objects that Recurly logs and makes available through this report. Recurly continues to expand the objects captured within this report. If there are any Recurly objects not represented below but you wish to obtain their event action, please contact your CSM for further guidance.

**Plan events are supported in both the Admin UI and API v3.**

| Event                              | Actions                                  | Trigger                                                                                                                                                                                       |
| ---------------------------------- | ---------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| login                              | success                                  | Successful login from a user to the merchant site                                                                                                                                             |
| user                               | create, delete, update                   | A user is added, roles updated or removed from the site                                                                                                                                       |
| role                               | create, update, delete                   | A new role is created, updated or removed from a site                                                                                                                                         |
| account_updater                    | enable, disable, update                  | Account updater settings changed on the site.                                                                                                                                                 |
| analytics_settings                 | update                                   | The analytics dashboard settings are updated.                                                                                                                                                 |
| coupon_settings                    | update                                   | The site-wide coupon settings are updated.                                                                                                                                                    |
| currency_settings                  | update                                   | Currencies the site has enabled are updated.                                                                                                                                                  |
| hosted_page_settings               | update                                   | The site-wide HPP settings are updated.                                                                                                                                                       |
| hosted_account_management_settings | update                                   | The site-wide HAM settings are updated.                                                                                                                                                       |
| invoice_settings                   | update                                   | The site-wide invoice settings are updated.                                                                                                                                                   |
| tax_settings                       | update                                   | The site-wide tax settings are updated.                                                                                                                                                       |
| custom_field_definition            | create, update, delete                   | A custom field definition is added, updated or removed from a site.                                                                                                                           |
| avalara_credentials                | create, update, delete                   | Avalara credentials are added, updated or removed from a site. Schema notes: Excludes the system marking credentials invalid. User updates only.                                              |
| plan                               | create, update, delete                   | A plan is added, updated or removed from a site. **Supported in Admin UI and API v3.** Schema notes: Excludes plan email configuration. Needs update to use dunning campaign code.            |
| add_on                             | create, update, delete                   | An add on is added to a plan, updated or removed from a plan. **Supported in Admin UI and API v3.**                                                                                           |
| measured_unit                      | create, update, delete                   | A measured unit is added, updated or removed from a site.                                                                                                                                     |
| coupon                             | create, update                           | A coupon is added, updated or removed from a site. **Admin UI only.**                                                                                                                         |
| coupon                             | generate_codes                           | Generate more unique coupon codes. **Admin UI only.**                                                                                                                                         |
| coupon                             | expire, restore                          | A coupon is manually expired or restored on a site. **Admin UI only.**                                                                                                                        |
| unique_coupon_code                 | expire, restore                          | A unique coupon code is manually expired or restored on a site. **Admin UI only.**                                                                                                            |
| email_settings                     | update                                   | Email settings for a template are updated.                                                                                                                                                    |
| email_templates                    | create, update, delete, reset            | Email templates are created, updated, deleted or reset. Schema notes: Excludes audience selector and attachment changes.                                                                      |
| payment_gateways                   | create, update, delete                   | A payment gateway is created, updated or removed from a site. Schema notes: Excludes changing default gateways.                                                                               |
| dunning_campaign                   | create, update, disable, enable          | A dunning campaign is added, updated, disabled or re-enabled on a site. **Admin UI only.** Schema notes: Excludes auditing plans dunning campaign id when changed.                            |
| dunning_campaign_settings          | update                                   | The site wide dunning campaign settings are updated. **Admin UI only.**                                                                                                                       |
| item                               | create, update, disable, enable          | An item is created, updated, disabled or re-enabled on a site. **Supported in Admin UI and API v3.**                                                                                          |
| entitlement                        | create, update, delete                   | An entitlement configuration is created, updated or removed from a site.                                                                                                                      |
| business_entity                    | create, update, delete                   | A business entity is created, updated or removed from a site. **Admin UI only.** Schema notes: Does not include auditing the creation of new Recurly revenue recognition GL accounting codes. |
| site_settings                      | update                                   | General Site configuration settings are updated.                                                                                                                                              |
| invoice_template                   | create, update                           | An invoice template is created or updated.                                                                                                                                                    |
| webhook_endpoint                   | create, update, delete, pause, resume    | A Webhooks notification endpoint was created, updated, deleted, paused or resumed on a site. Schema notes: Excludes changing pre-renewal webhook settings.                                    |
| api_key                            | create, view, update, regenerate, delete | A private API key is added, details are updated, it is regenerated or deleted on a site.                                                                                                      |
| public_key                         | regenerate                               | The public key has been regenerated on a site.                                                                                                                                                |
| shipping_method                    | create, update, delete                   | A shipping method is created, updated or deleted on a site. **Admin UI only.** Schema notes: Excludes Recurly revenue recognition fields.                                                     |
| apple_pay_settings                 | update                                   | Apple Pay configuration settings are updated on a site. Schema notes: Excludes managed Apple Pay domains.                                                                                     |

> 📘 Recurly Revenue Recognition
>
> At this time we do not log site activities for Recurly RevRec. No revrec-related data will be included in the Site Activities export.

# Implementation guide

### 1. Accessing the Site Activities export

1. **Log in** to your Recurly account.
2. You must have a Site Admin role, or an Admin permission included in your role to access the Admin Exports page on Recurly. Navigate to the **Admin** section located on the navigation panel.
3. Select the **Admin Exports** tab.
4. Find **Site Activities**, then select it to access the log.

### 2. Filtering the log entries

1. Once inside the Site Activities Export, you'll see various filtering options at the top.
2. Choose the desired **date range** to narrow down the log entries.
3. Use the **metadata types** dropdown to select specific fields you wish to view.
4. Select **Apply Filters** to update the log based on your selected criteria.

### 3. Viewing specific log details

1. Scroll through the log to find entries of interest.
2. Select any entry to expand it and view detailed information.
3. Here, you'll see details like the event type, resource identifier, principal resource type, IP address, and more.

### 4. Exporting the log

1. After filtering and selecting the desired log entries, locate the **Export** button at the top right corner.
2. Select it and choose your preferred **file format** (for example, CSV or Excel).
3. The download will start automatically. Save the file to your desired location on your computer.

### 5. Interpreting the log

1. Open the exported file using the appropriate software (for example, Microsoft Excel for `.xlsx` files).
2. The columns represent the different fields like event, resource identifier, and more.
3. Review the entries to understand the changes and actions taken on your Recurly site.

### 6. Taking action based on log insights

1. Based on the insights from the log, identify any unusual or unauthorized activities.
2. If you spot any suspicious activity, consider updating user permissions or changing passwords.
3. For any changes or actions you don't recognize, reach out to the respective team members for clarification.

### 7. Regular monitoring

1. Make it a habit to regularly check the Site Activities export to stay updated on all site-level activities.
2. Set reminders or schedule periodic reviews to ensure you don't miss out on any critical updates or changes.

### 8. Seeking assistance

1. If you encounter any challenges or have questions about specific entries, reach out to Recurly's support team.
2. For feature requests or feedback on the Site Activities export, contact your CSM.

By following these steps, you can effectively utilize the Site Activities export to monitor, track, and analyze activities on your Recurly site, ensuring transparency, security, and operational efficiency.