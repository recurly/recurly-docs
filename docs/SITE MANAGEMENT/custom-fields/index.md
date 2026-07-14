---
title: Custom fields
excerpt: >-
  Create custom fields in Recurly to capture and store business-specific data on
  accounts, subscriptions, plans, charges, and items — accessible via the Admin
  Console or API.
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
<div class="rp-page">
  <div class="rp-overview">Custom fields let you track data that's specific to your business on accounts, subscriptions, plans, charges, and items — subscriber IDs from external systems, sales rep names, acquisition channels, partner IDs, and more. Each field is configurable for API-only access, read-only in the UI, or fully editable in both.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on Pro and Elite plans — field limits vary by plan</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
    <a class="rp-toc-pill" href="#create-a-custom-field"><span class="rp-toc-num">4</span>Create a custom field</a>
    <a class="rp-toc-pill" href="#delete-a-custom-field"><span class="rp-toc-num">5</span>Delete a custom field</a>
  </div>
</div>

### Prerequisites

<ul class="rp-list">
  <li>Configuration permission within your Recurly role is required to create, edit, or delete custom field definitions</li>
</ul>

### Limitations

<ul class="rp-list">
  <li>Custom fields are text fields only, with a 255-character limit</li>
  <li>Picklist, boolean, true/false, and radio button data types are not supported</li>
  <li>Deleting a custom field definition permanently removes all associated data across every object it was applied to — this action is irreversible</li>
</ul>

# Definition

<div class="rp-definition">Custom fields in Recurly let you capture and store additional information on accounts, charges, items, plans, and subscriptions. Define each field's properties in the Admin Console, then assign and manage field values via the UI or API depending on the access level you configure.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-pen-ruler" aria-hidden="true"></i></div>
    <strong>Flexible data capture</strong>
    <span>Track business-specific information on any supported object without needing workarounds or external data stores.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-sliders" aria-hidden="true"></i></div>
    <strong>API and UI access control</strong>
    <span>Choose whether each field is API-only, read-only in the UI, or fully editable in both — per field, per object.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-plug" aria-hidden="true"></i></div>
    <strong>Richer integrations</strong>
    <span>Pass custom field values to external systems like NetSuite, or use them to conditionally tailor email communications.</span>
  </div>
</div>

# Key details

## Plan limits

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Plan</td><td>Custom fields allowed</td></tr>
  <tr><td>Sandbox / Developer</td><td>Up to 5 (for testing only)</td></tr>
  <tr><td>Starter</td><td>Not supported — remove any sandbox custom fields before upgrading to Starter</td></tr>
  <tr><td>Pro</td><td>Up to 5</td></tr>
  <tr><td>Elite</td><td>Up to 10</td></tr>
</table>

***

## Custom field definition settings

When creating or editing a custom field definition, the following settings are available:

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Field</td><td>Description</td></tr>
  <tr><td><strong>API Field Name</strong></td><td>The ID used to reference this field in the API. No spaces — only letters, numbers, dashes, and underscores.</td></tr>
  <tr><td><strong>Recurly Object</strong></td><td>The object this field applies to: Account, Charge, Item, Plan, or Subscription.</td></tr>
  <tr><td><strong>Admin Console Access</strong></td><td>Controls how the field appears in the UI. See options below.</td></tr>
  <tr><td><strong>Admin Console Field Name</strong></td><td>Required if the field is visible or editable in the UI — becomes the field's display label.</td></tr>
  <tr><td><strong>Tooltip Description</strong></td><td>Optional. When populated, a question mark icon appears next to the field name in the UI to provide context.</td></tr>
</table>

**Admin Console Access options:**

- **Hidden in the Admin Console** — field is only accessible via API
- **Read-only in the Admin Console** — field is viewable in the UI but only editable via API
- **Editable in the Admin Console** — field can be viewed and edited in both the UI and API
- **Able to set in the Admin Console** _(Charge only)_ — field can be set in the UI but not viewed there; data is accessible via API

***

## Custom fields by object

### Account

Account custom fields add context to the Account object. Common uses: subscriber IDs from external systems, sales rep names, channel partner names, subscriber segments, and regions.

To set a value, open the account, click **Edit**, scroll to the **Custom Fields** section, and enter the value. The value is displayed on the account record once saved.


<Image src="https://files.readme.io/05191e02073030d8e2412389810a487df5d9394da03583c5a82f0de3eb44375b-image.png" align="center" width="75%" border={true} />



<Image src="https://files.readme.io/c37ad4d08d4d1f60049cca81755c16cb07d38ebf1887bb0556e050fc81a1e554-image.png" align="center" width="75%" border={true} />


### Charge

Charge custom fields attach additional context to non-subscription line item charges or credits. Field values can also be used to conditionally tailor email communications.

To set a value, scroll to the **Custom Fields** section at the bottom of the Create Charge or Create Credit page and enter the value. Custom field data on charges is viewable via API.

<div class="rp-callout rp-callout-note">
  <div><strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> Note</strong>The Admin Console Access for Charge custom fields is <strong>Able to set in the Admin Console</strong> — values can be entered in the UI but are not displayed there. All data is accessible via API.</div>
</div>

### Subscription

Subscription custom fields capture subscription-specific information. Common uses: customer device IDs, acquisition channels, customer segments, subscription IDs from external systems, and partner IDs.

To set a value, navigate to the subscription details, find the **Custom Fields** section, and enter the relevant data.

### Plan

Plan custom fields attach metadata to individual plans. Use cases include highlighting upgrade or downgrade paths, passing plan attributes to external systems like NetSuite, grouping plans, or surfacing exclusive offers such as professional support.

To set a value, open the plan in create or edit mode — the custom field section appears if the field is set to editable. If the field is set to read-only, values are visible when viewing the plan but can't be edited from the edit screen.

***

## Editing a custom field definition

Edit any custom field definition at any time via **Configuration → Custom Fields**. All settings — API Field Name, Recurly Object, Admin Console Access, Admin Console Field Name, and Tooltip Description — are editable after creation.

# Create a custom field

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Open Custom Fields</h4><p>Go to <strong>Configuration → Custom Fields → Create Custom Field</strong>.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/f221aaf77e7c1f22b9da254478a1ecb2b23aeb88f1d217d24b0987f2c4bbe22d-image.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Fill in the field details</h4><p>Enter the API Field Name, select the Recurly Object, choose the Admin Console Access level, add a display name if the field will be visible in the UI, and optionally add a tooltip description.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Save the definition</h4><p>Click <strong>Save</strong> to create the custom field. You can edit it at any time from <strong>Configuration → Custom Fields</strong>.</p></div>
  </div>
</div>

# Delete a custom field

<div class="rp-callout rp-callout-important">
  <div><strong><i class="fa-solid fa-circle-exclamation" aria-hidden="true"></i> This action is irreversible</strong>Deleting a custom field definition permanently removes all associated data across every object it was applied to. For example, deleting a "Sales Rep" field populated on 100 accounts erases that data from all 100 accounts immediately. There is no undo.</div>
</div>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Open Custom Fields</h4><p>Navigate to <strong>Configuration → Custom Fields</strong>.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Note the API field name</h4><p>Find the field you want to delete and note the value in the <strong>Field Name (API)</strong> column — you'll need it to confirm deletion.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Select Delete</h4><p>Hover over the row and click <strong>Delete</strong> on the right side of the table.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/60caf227146a440b832099f6f35c4886462090f8bd49351ecfcd877564177971-image.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">4</div>
    <div><h4>Confirm deletion</h4><p>Enter the API field name to confirm, then click <strong>Confirm</strong>. The button activates once the correct name is entered.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/b783cc09ee4ec551fa2749851dfcf5cfa4cff3b0ac0e1557b184db98b97f2e37-image.png" align="center" width="75%" border={true} />


<br />
