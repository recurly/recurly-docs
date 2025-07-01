---
title: Data transformation
excerpt: >-
  Recurly Revenue Recognition Advanced: Transforming data for accurate financial
  reporting.
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

These Data Transformation features are part of **Recurly Revenue Recognition Advanced**. \[<a href="https://docs.recurly.com/docs/recurly-revenue-recognition-advanced" target="_blank">Learn more here</a>].

<Image align="center" className="border" border={true} width="75% " src="https://files.readme.io/6cb0c82-image.png" />

<br />

### Prerequisites

* Familiarity with your organization’s revenue recognition standards.
* Understanding of product bundling and data rule logic.
* Knowledge of which attributes you need in your analysis datasets.

### Limitations

* **Datasets** cannot be deleted once created—only inactivated.
* **Data Rules** cannot be deleted—only toggled inactive.

# Definition

Data Transformation in Recurly Revenue Recognition Advanced lets you:

* **Bundle products** into single units with inherited pricing and cost rules.
* **Apply Data Rules** to transactions via formulas, criteria, or attributes.
* **Auto-generate billing** for external subscription data without separate invoice imports.
* **Derive exchange rates** automatically based on contract or invoice dates.
* **Build Datasets** for analytics—updated daily and locked once created.

# Key benefits

* **Streamlined workflow**: Eliminate manual splits, invoice uploads, and rate lookups.
* **Accurate recognition**: Enforce consistent rules and formulas for revenue, cost, and commission.
* **Robust analytics**: Leverage custom datasets to power your executive reports and dashboards.

# Key details

* **Product bundle**: Group multiple SKUs into a single “Parent” unit; define child lines with pricing, cost, and commission formulas. [Learn more](product-bundle)
* **Data rules**: Create transaction-level logic—apply formulas, sub-criteria, and attributes to orders or contract lines. [Learn more](data-rules)
* **Auto Bill for external data**: Automatically generate invoices from imported sales orders when billing terms match subscription terms. [Learn more](autobill-for-external-data)
* **Derive ExRate for external data**: Automatically fetch and apply correct exchange rates for off-platform contracts and invoices. [Learn more](derive-exrate-for-external-data)
* **Datasets**: Define analysis tables with primary attributes; updated daily and inactivated when no longer needed. [Learn more](datasets)