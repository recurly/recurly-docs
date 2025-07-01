---
title: '- Autobill for external data - Revenue Recognition Standalone'
excerpt: >-
  Automatically generate invoice lines from imported sales orders—no separate
  billing imports needed.
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

Recurly Revenue Recognition Advanced can auto–populate billing records by generating invoice lines directly from your uploaded sales orders. This streamlines end-to-end revenue recognition and ensures your billing and recognition stay perfectly in sync.

### Prerequisites & limitations

* **Upfront billing only:** Auto Bill requires that the sales order reflects the full contract value at upload—billing cadence must match subscription term.
* **No post-generation edits:** Invoices created via Auto Bill cannot be updated or canceled; any revisions require manual invoice imports.

# Definition

**Auto Bill Generation** is a feature that reads your imported subscription or contract records and automatically creates the corresponding invoice lines—eliminating the need to upload separate billing files when subscription and billing terms align.

# Key benefits

* **Simplified imports**: Upload only your subscription records; the system crafts the matching invoices.
* **Unified revenue flow**: Keep recognition and billing together in one process for cleaner financial reporting.
* **Reduced operational overhead**: No more maintaining parallel invoice uploads—let Auto Bill handle it.

# Key details

## Enabling auto bill

**Navigation**: **Setup → Attribute labels**

<Image align="center" className="border" border={true} src="https://files.readme.io/a33ed901139845e5312c3b10eda7ba3b0335d36167f672e5aaff62f9d3aa2804-image.png" />

You can turn on Auto Bill either in your upload file or via a Data Rule:

#### Method 1: “Auto Bill” Attribute in your upload file

1. **Include** a column named `Auto Bill` in your sales order upload.
2. **Enter** `Yes` or `Y` for each line you want the system to generate an invoice for.

Once flagged, you don’t need to import any separate invoice records for those lines—Auto Bill will create them automatically.

#### Method 2: Configuring a data rule

1. **Go to** **Transformation → Data Rules**.
2. **Create** a new rule:

   * **Name** your rule.
   * **Select** **Order Line** as the object.
3. Under **Application Attributes**, choose `Auto Bill` and set **Value** to `Yes`.
4. **Save** the rule.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/31abf4fc4251a0d1934f82f1bfe679415d11294178022045e07b78f2581ca654-image.png" />

With this rule active, every uploaded line defaults to Auto Bill = `Y`, so the system will generate invoices without any file-level flags.

> **Note:** Auto Bill only works for full-term, upfront-billed subscriptions. If your billing cadence diverges from the subscription term, continue importing billing records manually.