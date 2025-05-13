---
title: Event stage details report
excerpt: >-
  Explore the detailed guide on Event Stage Report in Recurly's Revenue
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

The Event Stage Report displays custom event-related data that are currently stuck in the event stage of Recurly Revenue Recognition. By default, the report includes the **Error Message** column. This guide explains how to access, customize, and download the report, as well as how to save custom layouts for future use.

# Guide

## Accessing and configuring the report

To access and configure the Event Stage Report:

1. **Navigate to the Report:**

   * Go to **Reports** and select **Event Stage Details Report** from the menu.

   <br />

   <Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/1038ef47de692fceeb07fcf8d243359601608ca4a4a73bf7e979b9fd0a9c4f79-1.Introduction.png" />

   <br />

2. **Access the Mapper:**
   * Locate and open the report's **Mapper** tool.

3. **Add Required Columns:**

   * Within the Mapper, select and add the specific attributes you wish to include in the report. Available attributes include doc-level fields (in addition to the contract ID, subscription, and order line) such as **Subscription Number**, **Subscription Line**, **Event Name**, **Event Action**, **Amount &/ Percent**, and more.

   <br />

   <Image align="center" className="border" border={true} width="70% " src="https://files.readme.io/26212da7626e8b5c4e81a19185fd1e41e664852afe2836a8e6ced46d0e88f57e-4._Event_Stage_Report_Mapper.png" />

   <br />

4. **Run the Report:**
   * Click the **Run** button to generate the report.
   * Optionally, click the **Download** button to save the report locally.

## Report columns

* **Processed Flag:** Indicates whether a transaction has been successfully completed. A flag of **"E"** means the transaction has encountered an error, while **"N"** means it has not been processed.
* **Error Message:** Provides details about any errors encountered during processing.
* **Subscription Number:** The unique identifier for the subscription.
* **Subscription Line:** Details the specific subscription line involved in the event.
* **Event Name:** Specifies the name of the event that triggered the transaction.
* **Event Action:** Indicates the action taken in response to the event.
* **Amount &/ Percent:** Displays the transaction's monetary value or the percentage impact.