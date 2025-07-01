---
title: Datasets - Revenue Recognition Standalone
excerpt: >-
  Unlock powerful analytics by defining and updating custom data tables that
  feed all reports and dashboards automatically.
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

Datasets in Recurly Revenue Recognition Advanced are dynamic, user-defined tables of attributes—such as item, account, region, or customer—that drive every report and analysis. Once created, datasets refresh nightly to keep your insights up to date.

# Definition

A **Dataset** is a custom collection of fields (attributes) from your sales orders and contracts, organized into a reusable table for reporting and analysis. Datasets cannot be deleted, only inactivated, preserving historical integrity while preventing future use.

# Key benefits

* **Tailored analytics**: Pick exactly the attributes you need—item, liability account, region, customer—and build bespoke data tables.
* **Always current**: Datasets auto-refresh daily, so your dashboards and reports reflect yesterday’s latest sales and revenue.
* **Safe versioning**: Inactivate outdated datasets rather than delete, ensuring audit trails remain intact while retiring superseded configurations.

# Key details

## Creating a dataset

1. **Navigate** to **Transformation → Dataset**.

<Image align="center" className="border" border={true} src="https://files.readme.io/bb61372-image.png" />

2. **Enter** a unique **Dataset Name**.
3. **Select** the **Books** (ledgers) this dataset applies to.
4. **Choose** the desired **Attributes** and mark your **Primary Attribute(s)**.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/04cf460-image.png" />

5. **Click** **Save** to finalize the configuration.

Once saved, any uploaded sales order with matching identifiers will populate your new dataset. You’ll see the data reflected in the Revenue Workbench and across all analytics reports, ensuring consistent, accurate insights.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/9cdca79-image.png" />

> **Note:** Datasets cannot be permanently deleted; you can only toggle a dataset to **Inactive** to retire it from future use while retaining historical records.