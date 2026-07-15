---
title: Custom fields
excerpt: >-
  Extend Recurly objects like accounts, subscriptions, plans, and charges with
  custom fields to capture the data that matters most to your business.
deprecated: false
hidden: false
metadata:
  title: Custom Fields
  description: >-
    Dive into Recurly's Custom Fields to personalize your data, enhancing
    account, charge, item, plan, and subscription details for a tailored
    experience.
  robots: index
next:
  description: ''
---
# Overview

### Required plan

| Plan                | Custom fields allowed                                                        |
| :------------------ | :--------------------------------------------------------------------------- |
| Sandbox / Developer | Up to 5 (for testing only)                                                   |
| Starter             | Not supported — remove any sandbox custom fields before upgrading to Starter |
| Pro                 | Up to 5                                                                      |
| Elite               | Up to 10                                                                     |

### Prerequisites

* Configuration permission within your Recurly role is required to create, edit, or delete custom field definitions

### Limitations

* Custom fields are text fields only, with a 255-character limit
* Picklist, boolean, true/false, and radio button data types are not supported
* Deleting a custom field definition permanently removes all associated data across every object it was applied to — this action is irreversible

***

# Definition

Custom Fields in Recurly let you capture and store additional information on the following objects: Account, Charge, Item, Plan, and Subscription. Use them to track data that's specific to your business — such as subscriber IDs from other systems, sales rep names, acquisition channels, or partner IDs.

Custom field definitions are created in the Recurly Admin UI, where you define each field's properties. Once created, field values can be assigned, edited, and viewed via the Admin UI or API, depending on the access level you configure.

***

# Key benefits

* **Flexible data capture:** Track business-specific information on accounts, subscriptions, plans, charges, and items without workarounds.
* **API and UI access:** Choose whether each field is accessible only via API, read-only in the UI, or fully editable in both.
* **Richer integrations:** Pass custom field values to external systems like NetSuite, or use them to conditionally tailor email communications.

***

# Key details

## Creating a custom field definition

1. Navigate to **Configuration → Custom Fields → Create Custom Field**

<Image align="center" border={true} width="70%" src="https://files.readme.io/f221aaf77e7c1f22b9da254478a1ecb2b23aeb88f1d217d24b0987f2c4bbe22d-image.png" className="border" />

2. Fill in the following fields:

| Field                        | Description                                                                                                           |
| :--------------------------- | :-------------------------------------------------------------------------------------------------------------------- |
| **API Field Name**           | The ID used to reference this field in the API. No spaces — only letters, numbers, dashes, and underscores            |
| **Recurly Object**           | The object this field applies to: Account, Charge, Item, Plan, or Subscription                                        |
| **Admin Console Access**     | Controls how the field behaves in the UI (see options below)                                                          |
| **Admin Console Field Name** | Required if the field is visible or editable in the UI — becomes the field's display name                             |
| **Tooltip Description**      | Optional. When populated, a question mark icon appears next to the field name in the UI to provide additional context |

**Admin Console Access options:**

* **Hidden in the admin console** — field is only accessible via API
* **Read-only in the admin console** — field is viewable in the UI but only editable via API
* **Editable in the admin console** — field can be viewed and edited in both the UI and API
* **Able to set in the admin console** _(Charge only)_ — field can be set in the UI but not viewed there; data is accessible via API

***

## Editing a custom field definition

After creation, you can edit a custom field definition at any time via **Configuration → Custom Fields**. The same fields available during creation — API Field Name, Recurly Object, Admin Console Access, Admin Console Field Name, and Tooltip Description — are all editable.

***

## Deleting a custom field definition

> **Warning:** Deleting a custom field definition permanently removes all associated data across every object it was applied to. For example, deleting a "Sales Rep" field that's populated on 100 accounts will erase that data from all 100 accounts. This action is irreversible and takes effect immediately.

To delete a custom field definition:

1. Navigate to **Configuration → Custom Fields**
2. Note the value in the **Field Name (API)** column for the field you want to delete
3. Hover over that row and select **Delete** from the right side of the table

<Image align="center" border={true} width="75%" src="https://files.readme.io/60caf227146a440b832099f6f35c4886462090f8bd49351ecfcd877564177971-image.png" className="border" />

4. Enter the API field name to confirm
5. Click **Confirm** — the button activates once the correct name is entered

![](https://files.readme.io/b783cc09ee4ec551fa2749851dfcf5cfa4cff3b0ac0e1557b184db98b97f2e37-image.png)

***

## Custom fields by object

### Account

Account custom fields capture customer-specific information and add context to the Account object. Common uses include subscriber IDs from other systems, sales rep names, channel partner names, subscriber segments, and regions.

**To set a value in the UI:**

1. Open the account and click **Edit**

![](https://files.readme.io/05191e02073030d8e2412389810a487df5d9394da03583c5a82f0de3eb44375b-image.png)

2. Scroll to the **Custom Fields** section and enter the value

![](https://files.readme.io/c37ad4d08d4d1f60049cca81755c16cb07d38ebf1887bb0556e050fc81a1e554-image.png)

The value will be displayed on the account record once saved.

***

### Charge

Charge custom fields let you attach additional context to non-subscription line item charges or credits. Field values can also be used to conditionally tailor email communications.

**To set a value in the UI:** While creating a charge or credit, scroll to the **Custom Fields** section at the bottom of the page and enter the value. Custom field data on charges is viewable via API.

> **Note:** The Admin Console Access option for Charge custom fields is **Able to set in the admin console** — values can be set in the UI but are not displayed there.

***

### Subscription

Subscription custom fields capture subscription-specific information. Common uses include customer device IDs, acquisition channels, customer segments, subscription IDs from other systems, and partner IDs.

**To set a value in the UI:** Navigate to the subscription details, locate the **Custom Fields** section, and enter the relevant data.

***

### Plan

Plan custom fields let you attach metadata to individual plans. Use cases include highlighting available upgrade or downgrade paths, passing plan attributes to external systems like NetSuite, grouping plans, or surfacing exclusive offers like professional support.

**To set a value in the UI:** When creating or editing a plan, the custom field section appears if the field is set to editable. If the field is set to read-only, values are visible when viewing the plan but cannot be edited on the edit screen.