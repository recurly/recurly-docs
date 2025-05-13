---
title: Doc stage details report
excerpt: >-
  Explore the detailed guide on Docs Stage Report in Recurly's Revenue
  Recognition user guide.
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

This feature or setting is available to all customers on any Recurly subscription plan.

# Definition

The Doc Stage Report displays billing transactions that are currently stuck in the doc stage of Recurly Revenue Recognition. By default, the report includes the **Processed Flag** and **Error Message** columns. This guide explains the steps to access, customize, and download the report to help diagnose and resolve issues with billing transactions in the doc stage.

# Guide

## Accessing and configuring the report

To access and configure the Doc Stage Report:

1. **Navigate to the Report:**

   * Go to **Reports** and select **Doc Stage Details Report** from the menu.

   <br />

   <Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/51a3f800e0db6092eae7f5f93f8b6134d94c1405a640db3f09a79f2acdbdcf27-1.Introduction.png" />

   <br />

2. **Access the Mapper:**
   * Locate and open the report's **Mapper** tool.

3. **Add Required Columns:**

   * Within the Mapper, select and add the specific attributes you wish to include. Note that only doc level attributes are available in the mapper, in addition to the contract ID, subscription, and order line.

   <br />

   <Image align="center" className="border" border={true} width="70% " src="https://files.readme.io/a43bc945c949d4568003f9af5a8cd3f4f51acbbad7316f9a6df2fe0d8ced1e2d-3._Doc_Stage_Report_Mapper.png" />

   <br />

4. **Run the Report:**
   * Click the **Run** button to generate the report.
   * Optionally, click the **Download** button to save the report locally.

## Report columns

* **Processed Flag:** Indicates whether a transaction has been successfully completed. A flag of **"E"** indicates that the transaction has encountered an error, while **"N"** indicates that it has not been processed.
* **Error Message:** Provides details about any errors encountered during processing.

## Doc stage errors

The following table outlines the possible error messages and their potential causes within the Doc Stage Report:

| Error Message                                            | Possible Reason                                                                                                                                                                                                       |
| -------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Invalid References on INV                                | Please correct the invalid references in the invoice to process these lines.                                                                                                                                          |
| Invalid INV. INV belongs to Material Right Contract      | The invoice is invalid as it belongs to the material right contract. This cannot be collected.                                                                                                                        |
| Bill Amount is incorrect                                 | The bill amount mentioned in the file is incorrect.                                                                                                                                                                   |
| Original Credit Memo does not exist or already Cancelled | When a credit memo cancellation is uploaded with incorrect reference invoice details that do not exist in the system, this error occurs. The solution is to reupload the file with correct reference invoice details. |
| Original Invoice does not exist or already Cancelled     | When a credit memo is uploaded with incorrect reference invoice details that do not exist in the system, this error occurs. The solution is to reupload the file with correct reference invoice details.              |
| Original Invoice does not exist                          | When a credit memo is uploaded with incorrect reference invoice details that do not exist in the system, this error occurs. The solution is to reupload the file with correct reference invoice details.              |
| Invalid INV. SO not present in System                    | When the invoice is loaded for a sales order that does not exist in the system, this error occurs.                                                                                                                    |
| CM cannot be processed as INV is in error                | This will occur when the original invoice is in error status in the stage area. The solution is to review the reason for the invoice error.                                                                           |
| Cumulative bill amount is over sell price                | This error occurs when overage is not allowed under profiles and the sum of invoice values for the subscription exceeds the sell price. The solution is to navigate to **profiles → Overage** and enable overage.     |