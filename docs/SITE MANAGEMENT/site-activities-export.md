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

### Required plan

This feature is currently available for all merchants on an **Elite Recurly plan, with an Admin role, or an Admin permission** included in their role. To adopt this feature onto your Elite site, you will need to create a support request or contact your CSM to have the feature enabled. This export is also available as an optional add-on for customers on Recurly's Starter and Professional plans. Please reach out to Support or your CSM for more information. 

Recurly's Site Activities export is a comprehensive tool designed to capture and log activities related to your Recurly site. Unlike the Account Activities export, which focuses on customer account-level actions, the Site Activities export zeroes in on changes and actions pertaining to the Recurly site itself. This includes, but is not limited to, plan modifications, site setting updates, user management alterations, and user login activities.

> 🚧 Please Note
> 
> The Site Activities export will only display data from activities conducted after the Site Activities feature flag is turned on in your site. It will not reflect historic events that pre-date the log becoming active on your Recurly site.
> 
> This export will only support **data retention for 12 months**. After data has been available for 12 months, it will no longer be accessible in this export. If you require data retention past 12 months, it is recommended that you back up your data in your own data system.

# Key details

## Field definitions

The fields below are the fields or columns that can be added to your dashboard through filtering. You can decide which of the metadata types below you would like to view for the corresponding entries (objects with activities).

Each entry in the Site Activities export is characterized by specific fields or columns, which can be customized through filtering. Here's a breakdown of the metadata types available:

[block:parameters]
{
  "data": {
    "h-0": "Field",
    "h-1": "Definition",
    "0-0": "<span id=\"event\">event</span>",
    "0-1": "The type of event that triggered the entry in the audit log.",
    "1-0": "<span id=\"resource_identifier\">resource_identifier</span>",
    "1-1": "The external UUID of the record that was audited. Typically, the druuid of the record_id.",
    "2-0": "<span id=\"resource_type\">resource_type</span>",
    "2-1": "The external type of the record that was audited.",
    "3-0": "<span id=\"target_resource_identifier\">target_resource_identifier</span>",
    "3-1": "The external UUID of the target of the record.",
    "4-0": "<span id=\"target_resource_type\">target_resource_type</span>",
    "4-1": "The external type of the target of the record.",
    "5-0": "<span id=\"principal_resource_identifier\">principal_resource_identifier</span>",
    "5-1": "The external identifier of the principal. This could be the email or API key name/masked value.",
    "6-0": "<span id=\"principal_resource_type\">principal_resource_type</span>",
    "6-1": "The external type of the principal."
  },
  "cols": 2,
  "rows": 7,
  "align": [
    "left",
    "left"
  ]
}
[/block]


## Entries

The table below showcases the change activities and their corresponding objects that Recurly logs and makes available through this report. Recurly continues to expand the objects captured within this report. If there are any Recurly objects not represented below but you wish to obtain their event action, please contact your CSM for further guidance.

[block:parameters]
{
  "data": {
    "h-0": "Event",
    "h-1": "Actions",
    "h-2": "Trigger",
    "0-0": "login",
    "0-1": "success",
    "0-2": "Successful login from a user to the merchant site",
    "1-0": "user ",
    "1-1": "create, delete, update",
    "1-2": "A user is added, roles updated or removed from the site",
    "2-0": "role ",
    "2-1": "create, update, delete",
    "2-2": "A new role is created, updated or removed from a site",
    "3-0": "account_updater ",
    "3-1": "enable, disable, update",
    "3-2": "Account updater settings changed on the site.",
    "4-0": "analytics_settings",
    "4-1": "update",
    "4-2": "The analytics dashboard settings are updated.",
    "5-0": "coupon_settings",
    "5-1": "update",
    "5-2": "The site-wide coupon settings are updated.",
    "6-0": "currency_settings",
    "6-1": "update",
    "6-2": "Currencies the site has enabled are updated.",
    "7-0": "hosted_page_settings",
    "7-1": "update",
    "7-2": "The site-wide HPP settings are updated.",
    "8-0": "hosted_account_management_settings",
    "8-1": "update",
    "8-2": "The site-wide HAM settings are updated.",
    "9-0": "invoice_settings",
    "9-1": "update",
    "9-2": "The site-wide invoice settings are updated.",
    "10-0": "tax_settings",
    "10-1": "update",
    "10-2": "The site-wide tax settings are updated.",
    "11-0": "custom_field_definition",
    "11-1": "create, update, delete",
    "11-2": "A custom field definition is added, updated or removed from a site.",
    "12-0": "avalara_credentials",
    "12-1": "create, update, delete",
    "12-2": "Avalara credentials are added, updated or removed from a site. Schema notes: Excludes the system marking credentials invalid. User updates only.",
    "13-0": "plan",
    "13-1": "create, update, delete",
    "13-2": "A plan is added, updated or removed from a site. **Admin UI only. **Schema notes: Excludes plan email configuration.  \nNeeds update to use dunning campaign code",
    "14-0": "add_on",
    "14-1": "create, update, delete",
    "14-2": "An add on is added to a plan, updated or removed from a plan. **Admin UI only. **Schema notes: Needs update to use measured unit codes",
    "15-0": "coupon",
    "15-1": "create, update",
    "15-2": "A coupon is added, updated or removed from a site. **Admin UI only.**",
    "16-0": "coupon",
    "16-1": "generate_codes",
    "16-2": "Generate more unique coupon codes. **Admin UI only.**",
    "17-0": "coupon",
    "17-1": "expire, restore",
    "17-2": "A coupon is manually expired or restored on a site. **Admin UI only.**",
    "18-0": "unique_coupon_code",
    "18-1": "expire, restore",
    "18-2": "A unique coupon code is manually expired or restored on a site. **Admin UI only.**",
    "19-0": "email_settings",
    "19-1": "update",
    "19-2": "Email settings for a template are updated.",
    "20-0": "email_templates",
    "20-1": "create, update, delete, reset",
    "20-2": "Email templates are created, updated, deleted or reset. Schema notes: Excludes audience selector and attachment changes",
    "21-0": "payment_gateways",
    "21-1": "create, update, delete",
    "21-2": "A payment gateway is created, updated or removed from a site. Schema notes: Excludes changing default gateways",
    "22-0": "dunning_campaign",
    "22-1": "create, update, disable, enable",
    "22-2": "A dunning campaign is added, updated, disabled or re-enabled on a site. **Admin UI only.  **  \nSchema notes: Excludes auditing plans dunning campaign id when changed",
    "23-0": "dunning_campaign_settings",
    "23-1": "update",
    "23-2": "The site wide dunning campaign settings are updated. **Admin UI only.**",
    "24-0": "item",
    "24-1": "create, update, disable, enable",
    "24-2": "An item is created, updated, disabled or re-enabled on a site. **Admin UI only.**",
    "25-0": "entitlement",
    "25-1": "create, update, delete",
    "25-2": "An entitlement configuration is created, updated or removed from a site.",
    "26-0": "business_entity",
    "26-1": "create, update, delete",
    "26-2": "A business entity is created, updated or removed from a site. **Admin UI only. **  \nSchema notes: Does not include auditing the creation of new Recurly revenue recognition GL accounting codes.",
    "27-0": "site_settings",
    "27-1": "update",
    "27-2": "General Site configuration settings are updated.",
    "28-0": "invoice_template",
    "28-1": "create, update",
    "28-2": "An invoice template is created or updated.",
    "29-0": "webhook_endpoint",
    "29-1": "create, update, delete, pause, resume",
    "29-2": "A Webhooks notification endpoint was created, updated, deleted, paused or resumed on a site.  \nSchema notes: Excludes changing pre-renewal webhook settings.",
    "30-0": "api_key",
    "30-1": "create, view, update, regenerate, delete",
    "30-2": "A private API key is added, details are updated, it is regenerated or deleted on a site.",
    "31-0": "public_key",
    "31-1": "regenerate",
    "31-2": "The public key has been regenerated on a site.",
    "32-0": "shipping_method",
    "32-1": "create, update, delete",
    "32-2": "A shipping method is created, updated or deleted on a site **Admin UI only**,  Schema notes: excludes Recurly revenue recognition fields",
    "33-0": "apple_pay_settings",
    "33-1": "update",
    "33-2": "Apple Pay configuration settings are updated on a site.  \nSchema notes: Excludes managed Apple Pay domains"
  },
  "cols": 3,
  "rows": 34,
  "align": [
    "left",
    "left",
    "left"
  ]
}
[/block]


> 📘 Recurly Revenue Recognition
> 
> At this time we do not log site activities for Recurly RevRec. No revrec-related data will be included in the Site Activities export.

# Implementation guide

### 1. Accessing the Site Activities export

1. **Login** to your Recurly account.
2. You must have a Site Admin role, or an Admin permission included in your role to access the Admin Exports page on Recurly. Navigate to the **“Admin”** section located on the navigation panel.
3. Click on the **“Admin Exports”** tab.
4. Here, you'll find the **Site Activities** option. Click on it to access the log.

### 2. Filtering the log entries

1. Once inside the Site Activities Export, you'll see various filtering options at the top.
2. Choose the desired **date range** to narrow down the log entries.
3. Use the **metadata types** dropdown to select specific fields you wish to view.
4. Click on **“Apply Filters”** to update the log based on your selected criteria.

### 3. Viewing specific log details

1. Scroll through the log to find entries of interest.
2. Click on any entry to expand it and view detailed information.
3. Here, you'll see details like the event type, resource identifier, principal resource type, IP address, and more.

### 4. Exporting the log

1. After filtering and selecting the desired log entries, locate the **“Export”** button at the top right corner.
2. Click on it and choose your preferred **file format** (e.g., CSV, Excel).
3. The download will start automatically. Save the file to your desired location on your computer.

### 5. Interpreting the log

1. Open the exported file using the appropriate software (e.g., Microsoft Excel for .xlsx files).
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