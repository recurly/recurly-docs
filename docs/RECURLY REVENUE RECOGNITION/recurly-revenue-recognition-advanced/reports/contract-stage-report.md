---
title: Contract stage details report
excerpt: >-
  Explore the detailed guide on Contract Stage Report in Recurly's Revenue
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

The Contract Stage Report displays sales order transactions that are currently stuck in the order stage. By default, the report includes the **Processed Flag** and **Error Message** columns. This guide details the steps to access, customize, and download the report to help diagnose and resolve transaction processing issues.

# Guide

## Accessing and configuring the report

To access and configure the Contract Stage Report:

1. **Navigate to the Report:**

* Go to **Reports** and select **Contract Stage Details Report** from the menu.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/be81036fc19601f9bcfd024114dbeff55387bff825f1f5a500f0e5fc0700623f-1.Introduction.png" />

2. **Access the Mapper:**

* Locate and open the report's **Mapper** tool.

3. **Add Required Columns:**

* Within the Mapper, select and add the specific columns (attributes) you wish to include. By default, the report includes the **Processed Flag** and **Error Message** columns.

<Image align="center" className="border" border={true} width="60% " src="https://files.readme.io/1cc1ed3d34d9bcb7d464cf21124c7572f73d2c9e362c7eac5331d4874879a8b3-2._Contract_Stage_Report_Mapper.png" />

4. **Run the Report:**

* Click the **Run** button to generate the report.
* Optionally, click the **Download** button to save the report locally.

## Report columns

* **Processed Flag:** Indicates whether a transaction has been successfully processed. A flag of **"E"** means the transaction has encountered an error, while **"N"** means it has not been processed.
* **Error Message:** Provides detailed information about any errors encountered during processing.

# Contract stage errors

The following table outlines the possible error messages and their potential causes within the Contract Stage Report:

| Error Message                                                      | Possible Reason                                                                                                                                                      |
| ------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Credit Account is Blank                                            | The line stuck has no credit account assigned. Please check the configurations to add in the credit account.                                                         |
| Updated SO Amount is in different sign than previous Billed Amount | The line stuck is an SO update line that has the SO amount in a different sign than the original SO. Positive SO amount cannot be updated with a negative SO amount. |
| Error Processing So update                                         | In case of CMR, when the SO update flows in if the SO update is less than the billed amount, we can get this error.                                                  |
| Updated SO Amount is less than Billed Amount                       | This error indicates that the billed amount is greater than the SO amount. Hence, until we update the SO amount or allow overage, we cannot process this line.       |
| Bundle child updates are not allowed                               | Revenue Recognition does not allow bundle child line updates.                                                                                                        |
| Error Loading SO Line                                              | There could be many reasons for this error.                                                                                                                          |
| Debit Account is Blank                                             | The line stuck has no debit account assigned. Please check the configurations to add in the debit account.                                                           |
| Pob Rule setup is missing in book                                  | The line has no POB rules configured. Please check the POB rules section and configure the POB rules to process this line.                                           |
| Pob setup missing for some lines in this contract in book          | One or more of the lines in the contract are missing POB Rule configuration. Please check and update the POB rules for the concerned lines to process this line.     |