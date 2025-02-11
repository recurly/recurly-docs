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

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th style={{ textAlign: "left" }}>
        Field
      </th>

      <th style={{ textAlign: "left" }}>
        Definition
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="event">event</span>
      </td>

      <td style={{ textAlign: "left" }}>
        The type of event that triggered the entry in the audit log.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="resource_identifier">resource\_identifier</span>
      </td>

      <td style={{ textAlign: "left" }}>
        The external UUID of the record that was audited. Typically, the druuid of the record\_id.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="resource_type">resource\_type</span>
      </td>

      <td style={{ textAlign: "left" }}>
        The external type of the record that was audited.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="target_resource_identifier">target\_resource\_identifier</span>
      </td>

      <td style={{ textAlign: "left" }}>
        The external UUID of the target of the record.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="target_resource_type">target\_resource\_type</span>
      </td>

      <td style={{ textAlign: "left" }}>
        The external type of the target of the record.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="principal_resource_identifier">principal\_resource\_identifier</span>
      </td>

      <td style={{ textAlign: "left" }}>
        The external identifier of the principal. This could be the email or API key name/masked value.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="principal_resource_type">principal\_resource\_type</span>
      </td>

      <td style={{ textAlign: "left" }}>
        The external type of the principal.
      </td>
    </tr>
  </tbody>
</Table>

## Entries

The table below showcases the change activities and their corresponding objects that Recurly logs and makes available through this report. Recurly continues to expand the objects captured within this report. If there are any Recurly objects not represented below but you wish to obtain their event action, please contact your CSM for further guidance.

<Table align={["left","left","left"]}>
  <thead>
    <tr>
      <th style={{ textAlign: "left" }}>
        Event
      </th>

      <th style={{ textAlign: "left" }}>
        Actions
      </th>

      <th style={{ textAlign: "left" }}>
        Trigger
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td style={{ textAlign: "left" }}>
        login
      </td>

      <td style={{ textAlign: "left" }}>
        success
      </td>

      <td style={{ textAlign: "left" }}>
        Successful login from a user to the merchant site
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        user 
      </td>

      <td style={{ textAlign: "left" }}>
        create, delete, update
      </td>

      <td style={{ textAlign: "left" }}>
        A user is added, roles updated or removed from the site
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        role 
      </td>

      <td style={{ textAlign: "left" }}>
        create, update, delete
      </td>

      <td style={{ textAlign: "left" }}>
        A new role is created, updated or removed from a site
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        account\_updater 
      </td>

      <td style={{ textAlign: "left" }}>
        enable, disable, update
      </td>

      <td style={{ textAlign: "left" }}>
        Account updater settings changed on the site.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        analytics\_settings
      </td>

      <td style={{ textAlign: "left" }}>
        update
      </td>

      <td style={{ textAlign: "left" }}>
        The analytics dashboard settings are updated.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        coupon\_settings
      </td>

      <td style={{ textAlign: "left" }}>
        update
      </td>

      <td style={{ textAlign: "left" }}>
        The site-wide coupon settings are updated.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        currency\_settings
      </td>

      <td style={{ textAlign: "left" }}>
        update
      </td>

      <td style={{ textAlign: "left" }}>
        Currencies the site has enabled are updated.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        hosted\_page\_settings
      </td>

      <td style={{ textAlign: "left" }}>
        update
      </td>

      <td style={{ textAlign: "left" }}>
        The site-wide HPP settings are updated.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        hosted\_account\_management\_settings
      </td>

      <td style={{ textAlign: "left" }}>
        update
      </td>

      <td style={{ textAlign: "left" }}>
        The site-wide HAM settings are updated.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        invoice\_settings
      </td>

      <td style={{ textAlign: "left" }}>
        update
      </td>

      <td style={{ textAlign: "left" }}>
        The site-wide invoice settings are updated.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        tax\_settings
      </td>

      <td style={{ textAlign: "left" }}>
        update
      </td>

      <td style={{ textAlign: "left" }}>
        The site-wide tax settings are updated.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        custom\_field\_definition
      </td>

      <td style={{ textAlign: "left" }}>
        create, update, delete
      </td>

      <td style={{ textAlign: "left" }}>
        A custom field definition is added, updated or removed from a site.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        avalara\_credentials
      </td>

      <td style={{ textAlign: "left" }}>
        create, update, delete
      </td>

      <td style={{ textAlign: "left" }}>
        Avalara credentials are added, updated or removed from a site. Schema notes: Excludes the system marking credentials invalid. User updates only.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        plan
      </td>

      <td style={{ textAlign: "left" }}>
        create, update, delete
      </td>

      <td style={{ textAlign: "left" }}>
        A plan is added, updated or removed from a site. **Admin UI only.**Schema notes: Excludes plan email configuration.\
        Needs update to use dunning campaign code
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        add\_on
      </td>

      <td style={{ textAlign: "left" }}>
        create, update, delete
      </td>

      <td style={{ textAlign: "left" }}>
        An add on is added to a plan, updated or removed from a plan. **Admin UI only.**Schema notes: Needs update to use measured unit codes
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        coupon
      </td>

      <td style={{ textAlign: "left" }}>
        create, update
      </td>

      <td style={{ textAlign: "left" }}>
        A coupon is added, updated or removed from a site. **Admin UI only.**
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        coupon
      </td>

      <td style={{ textAlign: "left" }}>
        generate\_codes
      </td>

      <td style={{ textAlign: "left" }}>
        Generate more unique coupon codes. **Admin UI only.**
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        coupon
      </td>

      <td style={{ textAlign: "left" }}>
        expire, restore
      </td>

      <td style={{ textAlign: "left" }}>
        A coupon is manually expired or restored on a site. **Admin UI only.**
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        unique\_coupon\_code
      </td>

      <td style={{ textAlign: "left" }}>
        expire, restore
      </td>

      <td style={{ textAlign: "left" }}>
        A unique coupon code is manually expired or restored on a site. **Admin UI only.**
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        email\_settings
      </td>

      <td style={{ textAlign: "left" }}>
        update
      </td>

      <td style={{ textAlign: "left" }}>
        Email settings for a template are updated.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        email\_templates
      </td>

      <td style={{ textAlign: "left" }}>
        create, update, delete, reset
      </td>

      <td style={{ textAlign: "left" }}>
        Email templates are created, updated, deleted or reset. Schema notes: Excludes audience selector and attachment changes
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        payment\_gateways
      </td>

      <td style={{ textAlign: "left" }}>
        create, update, delete
      </td>

      <td style={{ textAlign: "left" }}>
        A payment gateway is created, updated or removed from a site. Schema notes: Excludes changing default gateways
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        dunning\_campaign
      </td>

      <td style={{ textAlign: "left" }}>
        create, update, disable, enable
      </td>

      <td style={{ textAlign: "left" }}>
        A dunning campaign is added, updated, disabled or re-enabled on a site. **Admin UI only.**\
        Schema notes: Excludes auditing plans dunning campaign id when changed
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        dunning\_campaign\_settings
      </td>

      <td style={{ textAlign: "left" }}>
        update
      </td>

      <td style={{ textAlign: "left" }}>
        The site wide dunning campaign settings are updated. **Admin UI only.**
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        item
      </td>

      <td style={{ textAlign: "left" }}>
        create, update, disable, enable
      </td>

      <td style={{ textAlign: "left" }}>
        An item is created, updated, disabled or re-enabled on a site. **Admin UI only.**
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        entitlement
      </td>

      <td style={{ textAlign: "left" }}>
        create, update, delete
      </td>

      <td style={{ textAlign: "left" }}>
        An entitlement configuration is created, updated or removed from a site.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        business\_entity
      </td>

      <td style={{ textAlign: "left" }}>
        create, update, delete
      </td>

      <td style={{ textAlign: "left" }}>
        A business entity is created, updated or removed from a site. **Admin UI only.**\
        Schema notes: Does not include auditing the creation of new Recurly revenue recognition GL accounting codes.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        site\_settings
      </td>

      <td style={{ textAlign: "left" }}>
        update
      </td>

      <td style={{ textAlign: "left" }}>
        General Site configuration settings are updated.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        invoice\_template
      </td>

      <td style={{ textAlign: "left" }}>
        create, update
      </td>

      <td style={{ textAlign: "left" }}>
        An invoice template is created or updated.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        webhook\_endpoint
      </td>

      <td style={{ textAlign: "left" }}>
        create, update, delete, pause, resume
      </td>

      <td style={{ textAlign: "left" }}>
        A Webhooks notification endpoint was created, updated, deleted, paused or resumed on a site.\
        Schema notes: Excludes changing pre-renewal webhook settings.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        api\_key
      </td>

      <td style={{ textAlign: "left" }}>
        create, view, update, regenerate, delete
      </td>

      <td style={{ textAlign: "left" }}>
        A private API key is added, details are updated, it is regenerated or deleted on a site.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        public\_key
      </td>

      <td style={{ textAlign: "left" }}>
        regenerate
      </td>

      <td style={{ textAlign: "left" }}>
        The public key has been regenerated on a site.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        shipping\_method
      </td>

      <td style={{ textAlign: "left" }}>
        create, update, delete
      </td>

      <td style={{ textAlign: "left" }}>
        A shipping method is created, updated or deleted on a site **Admin UI only**,  Schema notes: excludes Recurly revenue recognition fields
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        apple\_pay\_settings
      </td>

      <td style={{ textAlign: "left" }}>
        update
      </td>

      <td style={{ textAlign: "left" }}>
        Apple Pay configuration settings are updated on a site.\
        Schema notes: Excludes managed Apple Pay domains
      </td>
    </tr>
  </tbody>
</Table>

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
