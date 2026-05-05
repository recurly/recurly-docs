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

# Creating and editing custom field definitions

Users with the Configuration permission within their role have the ability to create and edit custom field definitions on their Recurly site. These definitions allow you to collect custom field values for accounts, charges, items, plans, or subscriptions.

To create a custom field definition, navigate to Configuration → Custom Fields → Create Custom Field.

<Image align="center" src="https://files.readme.io/c6597a7785a4c50599e49efdcd8c7d0913b628cc5450dae8a8d17d7c05ec2b0e-Screenshot_2026-04-06_at_12.48.11_PM.png" />

# Key details

* **API Field Name:** This serves as the ID used in the API to reference the custom field. It should not contain spaces and can only consist of numbers, letters, dashes, and underscores.
* **Recurly Object:** This determines the object on which the custom field is created, such as account, charge, item, plan, or subscription.
* **Allow this field to show up on Invoices:** When enabled, the custom field will appear in a variable picker inside of the invoice template editor.  If chosen, the custom field name and its value will appear on invoices.
* **Allow this field to show up in Exports:** When enabled, the custom field will be pulled into exports associated with the Recurly object it belongs to.
* **Admin Console Access:** This option controls the behavior of the field in the Recurly UI.
  * **Hidden in the admin console:** The field is only editable or viewable via the API.
  * **Read-only in the admin console:** The field is viewable in the UI but only editable through the API.
  * **Editable in the admin console:** The field can be viewed and edited in both the UI and API.
* **Admin Console Field Name:** If you enable the field to be set, edited, or viewed in the Admin Console, this field is required, and its value becomes the field name in the Admin Console.  If _Allow this field to show up on Invoices_ is selected, this console name also because the name that appears on invoices.
* **Tooltip Description:** If populated, a question mark icon will appear next to the Admin Console Field Name, providing additional context for users to understand the purpose of the field.

1. Navigate to **Configuration → Custom Fields → Create Custom Field**

<Image align="center" border={true} width="70%" src="https://files.readme.io/f221aaf77e7c1f22b9da254478a1ecb2b23aeb88f1d217d24b0987f2c4bbe22d-image.png" className="border" />

2. Fill in the following fields:

## Deleting custom field definitions

## Editing a custom field definition

After creation, you can edit a custom field definition at any time via **Configuration → Custom Fields**. The same fields available during creation — API Field Name, Recurly Object, Admin Console Access, Admin Console Field Name, and Tooltip Description — are all editable.

1. Go to Configuration→Custom Fields.
2. Take note of the value in the "Field Name (API)" column for the custom field you want to eliminate.
3. Hover over the row of the custom field you'd like to delete, and on the right side of the table, select "Delete."
4. Enter the value you noted in the previous step.
5. Once entered, the "Confirm" button will become enabled.
6. Review the consequences of deleting the custom field definition:

4. Enter the API field name to confirm
5. Click **Confirm** — the button activates once the correct name is entered

![](https://files.readme.io/b783cc09ee4ec551fa2749851dfcf5cfa4cff3b0ac0e1557b184db98b97f2e37-image.png)

***

When defining an account custom field object, if you selected the **Editable in the admin console** option, you can set the custom field value when creating or editing an account.  Once the account is created or updated, the custom field and its value will appear within Account Information.

# Custom fields on charges

Custom Fields on Charges allow you to set custom values on non-subscription line item charges or credits. This feature enables you to add additional context for charges and even allows you to conditionally tailor your email communications based on these custom field values.

When defining the custom field object, if you selected the **Able to be set in the admin console**option, you can set the custom field value when creating a charge on the Add Charge page.  The custom field and its value can be viewed via an API call.

# Custom fields on a subscription

Custom Fields on a Subscription allow you to capture subscription-specific information and enhance your understanding of your subscribers. You can create custom field values to track data such as customer device ID, acquisition channel, customer segment, subscription ID from other systems, or partner ID. These custom fields provide valuable insights and enable you to personalize your interactions and business processes based on this additional information.

When defining the custom field object, if you selected the **Editable in the admin console** option, you can set the custom field value when creating or editing a subscription. Navigate to the subscription details and locate the custom field section.

# Custom fields on a plan

Plan custom fields offer a versatile means to customize your plans according to precise requirements. For instance, a custom field on a plan could be used to highlight available upgrade or downgrade options. It can also be used to dictate rules for integrations with external systems like NetSuite. Additionally, a custom field can serve as an attribute to link a plan to a specific group of plans, or to showcase exclusive offers for that plan, such as professional support. This adds an extra layer of personalization and flexibility to your offerings.

When defining the custom field object, if you selected the **Editable in the admin console** option, you can set the custom field value when creating or editing a plan.

# Custom fields on invoices

Each type of custom field and its value can be made available to invoices by selecting the **Allow this field to show up on Invoices** option.  This will allow the custom field to be selected when creating or editing an invoice template.    Once saved to an invoice template, any time that custom field is invoked, it will be displayed on an invoice.

<Image align="center" border={true} src="https://files.readme.io/64ccacfcded34a3016dff483661510043cfe6c12df124ada9561176ef8978687-Screenshot_2026-04-28_at_1.30.42_PM.png" className="border" />

Account custom fields will display at the bottom of the "Bill to" section while all other custom fields types (plan, subscription, item, and charge) will be displayed within the invoice line item that it's associated to.

<Image align="center" border={true} src="https://files.readme.io/590d88b26f7efc292f35b3b9c2e4c1da8ea7de7747bacccf78b367eb6797dc87-Screenshot_2026-04-28_at_2.49.36_PM.png" className="border" />

When a custom field is removed from an invoice template, it won't appear on any new invoices going forward — but your existing invoices will continue to display it.

When [account hierarchy](https://docs.recurly.com/recurly-subscriptions/docs/account-hierarchy-1) is enabled and both the parent and child accounts have custom fields, the child account's custom fields will display.

Custom fields will also be returned through the [invoices API](https://recurly.com/developers/api/v2021-02-25/index.html#operation/get_invoice).

**Request:** `/invoices/{1000}`

**Response Snippet:**

```json
    "custom_fields": [
        {
            "name": "csRep",
            "value": "James Hawthorne",
            "source_record_type": "account",
            "source_record_id": "yogj7zapi5y6"
        }
    ]
```

<br />

<br />
