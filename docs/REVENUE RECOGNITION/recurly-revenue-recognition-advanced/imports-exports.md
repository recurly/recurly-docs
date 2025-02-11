---
title: Imports & exports
excerpt: Effortlessly Manage Your Data with Recurly's Import/Export Tool.
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

This feature is part of our product, Recurly Revenue Recognition Advanced. [<a href="https://docs.recurly.com/docs/recurly-revenue-recognition-advanced" target="_blank">Learn more here</a>].

### Prerequisites

1. An active Recurly account with administrative privileges.
2. Familiarity with the data types and structures used in your business operations.
3. Access to the source files intended for import or the destination directories for exports.

### Limitations

1. The import/export tool may have file size restrictions, ensuring that uploads/downloads remain efficient.
2. Any changes that are made will be applied for future transactions only.
3. The system may require specific file formats for successful data import.
4. Real-time synchronization might not be available; data sync may occur at scheduled intervals.

# Key benefits

* **Data consistency:** Ensure that your Recurly data remains consistent with other platforms or databases you might be using.
* **Time eficiency:** Eliminate the manual entry of data, saving time and reducing potential errors.
* **Enhanced reporting:** By importing all necessary data, generate comprehensive reports that provide deeper insights into your business operations.
* **Flexibility:** Export your data whenever needed, ensuring you always have access to your information, irrespective of the platform.
* **Streamlined operations:** With regular data synchronization, maintain a smooth flow of operations, ensuring all departments have access to the latest data.

# Utilizing the Import/Export tool

The Import/Export feature in Recurly Revenue ecognition is designed to optimize the management of your data. It provides a structured platform to either import or export various data types, including but not limited to sales orders, billings, and cost files. By using this tool, users can meticulously review transactions, process them with precision, and ensure that journals are correctly posted to the GL. The primary objective is to guarantee a smooth data transfer process, which is pivotal for accurate financial analysis and informed decision-making.

## Transactions

**Note:** For a successful upload, it's imperative that the column headings in your file are consistent with the upload names specified in the attribute mapper of Recurly Revenue Recognition Advanced.

In Recurly Revenue Recognition Advanced, users are equipped with the capability to upload pivotal sales orders, billings, and cost files. These files serve as the backbone for revenue recognition and are integral components in the financial reporting mechanism.

### How to import transactions

1. Access the Import/Export section and select "Transactions."
2. Utilize the "+" icon to introduce your transaction file into the system. After uploading, always ensure the file is saved.\
   ![](https://files.readme.io/d9290f3-image.png)
3. It's crucial to ensure that the column headings in your file align with the system's attribute labels. Any discrepancies can hinder the file loading process.
4. Once saved, transaction files are conveniently displayed as cards on the left side of the transaction import window.\
   ![](https://files.readme.io/98ebb91-image.png)
5. After the successful upload of transaction files, they can be accessed and scrutinized in the Revenue Workbench, providing a comprehensive overview of your revenue data.

> **Notes:**
>
> * When uploading billing files in Recurly Revenue Recognition Advanced, the supported document types are INV (invoice), IVC (invoice cancellation), CM (credit memo), and CMC (credit memo cancellation). Partial credit memos are allowed, but partial invoice cancellations are not permitted.
> * The system collects transactions that belong to the current open period and previous periods. Transactions associated with future periods are placed in the stage area and are processed once the corresponding period is opened. This ensures accurate and timely processing of transactions in alignment with the period schedule.

## Events

Before initiating an event file upload in Recurly Revenue Recognition Advanced, it's essential to ensure that the file has been meticulously linked with a POB (Performance Obligation) template. This linkage is paramount for the proper mapping of events, ensuring that revenue recognition is both accurate and aligned with contractual obligations.

### How to upload event files

1. Navigate to the Import/Export section and select "Events."
2. Initiate the upload process for a new event file by clicking on the "+" button.\
   ![](https://files.readme.io/b5d085e-image.png)
3. Assign a name to the event file. By default, the system will adopt the name of the uploaded file. Subsequently, select the relevant event from the dropdown menu. These events are essentially predefined templates established in the system.
4. Once all the necessary details are populated, save the file. The system will then process the uploaded event file in accordance with the configurations set for that specific event, ensuring that revenue recognition is both accurate and compliant with established rules.

## Stage area

The Stage Area in Recurly Revenue Recognition Advanced contains four tabs: Contracts, Documents, Cost, and Events. Unprocessed files related to each tab will be displayed under their respective tabs. There are several reasons why files may remain unprocessed in the Stage Area:

* **Error in the file:** If there are any errors encountered during the upload of Contracts, Documents, Cost, or Event files, those files will be placed in the Stage Area. The system usually displays error messages corresponding to each transaction, indicating the issue that needs to be addressed.
* **Future transactions:** If any transactions have a future date or period assigned to them and they are uploaded into the system during the current period, these transactions will be held in the Stage Area until the applicable period for those transactions is opened in the system. This ensures that transactions are processed accurately based on their respective periods.
* **Scheduled processing:** If the scheduled jobs for transaction import or event import are not run or are inactive, it can cause transactions to remain stuck in the Stage Area. It is important to ensure that the scheduled jobs are active and properly configured to process the transactions as intended.

### How to view and delete data in the stage area

1. To access the Stage Area, navigate to Import/Export.
2. The "Status" tab provides a structured view of the files, allowing users to filter and view files based on specific criteria.
3. To delete specific data, select the transaction under the respective tab, click the Delete icon, and confirm the deletion. Always remember to save changes to finalize the removal.

## Transfer JE

**Note:** The month-end close process is a structured two-step approach. The initial step involves the meticulous transfer and verification of journal entries, laying the foundation for a confident period closure.

1. **Navigation:** Go to Import / Export → Transfer JE.
2. **Click** on the journal card of the primary book to access the journal entries.
3. To double-check and ensure that all entries created are accurate and reflect the correct financial transactions for the period, **follow** these steps:
   1. **Run the Asset Report:** Generate the Asset Report for the period. Verify that the total of the scheduled column in the asset account matches the total amount displayed in the revenue waterfall report.
   2. **Run the Liability Report:** Generate the Liability Report for the period. Confirm that the total of the scheduled column in the liability account matches the total amount shown in the revenue waterfall report.
   3. **Run the Revenue Waterfall Report:** Generate the Revenue Waterfall Report for the period. Validate that the total amount displayed in the waterfall matches the combined total of the scheduled columns in both the asset and liability accounts.
   4. **Run the Revenue Insight Report:** Generate the Revenue Insight Report. Verify that the scheduled balance in the report matches the total amount displayed in the revenue waterfall report for the period.
4. After completing the reconciliation process, follow these steps to finalize the transfer of journal entries:

   1. **Click** on   "Approve for Transfer" for the Journal card of the Primary book. This action indicates that the journal entries have been reviewed and approved for transfer.
   2. Once the entries have been approved, **click** on "Mark as trasnfered" . This step confirms that the journal entries have been successfully transferred and recorded.
   3. Before proceeding to the next step, **ensure**that the journal card is "summarized." This summarization consolidates the entries and ensures accurate reporting. Please note that it is crucial to wait until the journal card is summarized before moving forward.

      <Image align="center" className="border" border={true} src="https://files.readme.io/250214f-image.png" />

## Period close

After the meticulous process of transferring journal entries, the final step is to close the period:

1. Access the Period Close option via Import/Export.
2. Initiate the next period by selecting "Open New Period."
3. Confirm the action and proceed.

   <Image align="center" className="border" border={true} src="https://files.readme.io/993b248-image.png" />
4. Allow the system to seamlessly transition to the next period, ensuring continuity in your financial operations.
