---
title: Data rules
excerpt: >-
  Apply custom logic and formulas to your sales orders during import for precise
  revenue recognition, contract handling, and cost allocation.
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

### Definition

A **Data Rule** is a configurable set of conditions, formulas, and effective dates that you apply to Contracts, Order Lines, Document Lines, or Cost records when importing sales orders. Rather than manually adjusting data post-upload, Data Rules automate transformation and enrichment at import time.

# Key benefits

* **Automated data enrichment**: Apply formulas and value overrides automatically, eliminating manual updates.
* **Granular control**: Target rules to Contracts, Order Lines, Doc Lines, or Cost entries for maximum precision.
* **Configurable activation**: Schedule rules to activate only during specific date windows, then retire or adjust as your business evolves.

# Key details

## Configuring data rules

1. **Navigate** to **Transformation → Data Rules**.

<Image align="center" className="border" border={true} src="https://files.readme.io/bb61372-image.png" />

2. **Enter** a **Rule Name**.
3. **Select** the **Object** level: Contract, Order Line, Doc Line, or Cost.
4. **Choose** the **Book** that the rule applies to.

<Image align="center" className="border" border={true} src="https://files.readme.io/34685d1-image.png" />

5. **Set** **Effective Start** and **End Dates**.
6. **Click** the **Save** icon.

> **Note:** Data Rules cannot be deleted once created, but you can toggle them to **Inactive** under the Status column and save changes. To edit, modify fields and click **Save**.

## Defining Rule Logic

1. In your Data Rule, **open** the **Rules** tab and click the **Add** icon.
2. **Select** an **Application** attribute (fields vary by object).

<Image align="center" className="border" border={true} src="https://files.readme.io/aa3f447-image.png" />

3. **Enter** a **Formula** or static value to assign to that attribute.
4. (Optional) **Click** **Add** under **Sub Criteria** to refine when this rule fires: choose a field, operator, and value.

<Image align="center" className="border" border={true} src="https://files.readme.io/2bebae0-image.png" />

5. **Click** **Save**.
6. **Repeat** to add multiple rules or sub-criteria.

<Image align="center" className="border" border={true} src="https://files.readme.io/bda0b72-image.png" />

5. To delete a rule or sub-criteria, select its row and click the **Delete** icon, then save.

## Configuring criteria

1. In the **Criteria** section, **click** the **Add** icon.

<Image align="center" className="border" border={true} src="https://files.readme.io/2f8bfa0-image.png" />

2. **Choose** a **Field** from the dropdown.
3. **Select** an **Operator**.
4. **Enter** the matching **Value**.
5. **Add** multiple rows as needed.

<Image align="center" className="border" border={true} src="https://files.readme.io/9e698ad-image.png" />

6. **Edit** any row inline and click **Save**, or remove it via the **Delete** icon.

> **Tip:** Carefully review and test your Data Rules after configuration to confirm they behave as expected before running large imports.