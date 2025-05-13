---
title: Config audit report
excerpt: >-
  Explore the detailed guide on Config Audit Report in Recurly's Revenue
  Recognition user guide.
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

### Required plan

This feature or setting is available to all customers on any Recurly subscription plan.

# Definition

The Configuration Audit Report provides a comprehensive record of all configuration changes made within Revenue Recognition during a specified period. This report serves as a detailed history, enabling users to track and understand modifications.

* The report provides a detailed history of configuration changes within Revenue Recognition.
* It allows tracking modifications based on period, entity, and user.
* The report columns offer insights into the nature of the changes, whether they are new additions or updates, and who performed them.

# Guide

## Accessing and configuring the report

To extract the Config Audit Report:

1. **Navigate to the Report:**

* Go to **Reports** → **Audit Reports** → **Config Audit Report**.

<br />

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/821f5f467a72f5b760ee3a7bef49e106e0e8105477596f04a316aacc10bd9dd3-1._Config_Audit_Report.png" />

2. **Set the Parameters:**

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/906776130c0d964b3a78693ecd42e47c83f7f993cd29f840d9d576057f81166d-2._Step_1.png" />

* **Period:** Select the period for which you need to see the configuration audit.
* **Entity:** Choose the specific configuration entity. Options include Contract Grouping, POBs, SSP, Dataset, Data Rule, Product Bundle, and other configuration settings.
* **User:** Select the user to view the changes performed by that specific individual.

3. **Run the Report:**

* Click the **Run** button to generate the report.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/eee2faf3b443fdb12e7984e6ffe4335f0d86d266d3b85038686c44d02f6c4169-3._Step_3.png" />

* Optionally, click the **Download** button to save the report locally.

## Report columns

* **Entity:** Represents the major configuration type.
* **Sub Entity:** Represents the sub-type under the entity.
* **Action:** Displays either **Create** (indicating the addition of a new configuration) or **Update** (indicating modifications to an existing configuration).
* **Value:** Details the actual changes made.
* **Changed by:** Shows the user ID of the individual who performed the action.
* **Changed date:** Indicates the date on which the changes were made.