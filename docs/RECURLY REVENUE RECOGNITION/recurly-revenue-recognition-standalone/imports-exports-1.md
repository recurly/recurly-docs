---
title: Imports & exports - Revenue Recognition Standalone
excerpt: >-
  Supercharge your data management with Recurly Revenue Recognition’s
  Import/Export feature! Effortlessly import and export crucial information to
  enhance efficiency, drive accurate revenue recognition, and optimize your
  financial operations.
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

This feature is part of our product, Recurly Revenue Recognition Standalone. [<a href="https://docs.recurly.com/docs/recurly-revenue-recognition-standalone" target="_blank">Learn more here</a>].

### Required plan

The Standalone Revenue Recognition module is available to merchants who need a Revenue tool to automate their ASC 606 / IFRS 15 accounting but do not, at this time, need the Recurly billing platform. 

### Cost

Please reach out to [support@recurly.com](mailto:support@recurly.com) for more pricing details.

### Prerequisites

* A valid Recurly account with appropriate permissions.
* Basic understanding of Recurly's revenue recognition processes.
* Familiarity with contract terms and conditions.

### Limitations

* Any changes that are made will be applied for future transactions only.
* Recurly Revenue Recognition Standalone may have file restriction to ensure efficient uploads.
* Changes that are done to configurations are applied only for the future transactions
* Recurly Revenue Recognition Standalone  may require specific file format or specific API calls for successful data import.

# Key benefits

* **Data consistency:** Ensure that your Recurly data remains consistent with other platforms or databases you might be using.
* **Enhanced reporting:** By importing all necessary data, generate comprehensive reports that provide deeper insights into your business operations.
* **Flexibility:** Export your data whenever needed, ensuring you always have access to your information, regardless of the platform.
* **Streamlined operations:** With regular data synchronization, maintain a smooth flow of operations, ensuring all departments have access to the latest data.

# Utilizing the import/export tool

The import/export feature in Recurly Revenue Recognition is designed to optimize the management of your data. It provides a structured platform to either import or export various data types, including but not limited to sales orders, billings, and cost files. By using this tool, users can meticulously review transactions, process them with precision, and ensure that journals are correctly posted to the GL. The primary objective is to guarantee a smooth data transfer process, which is pivotal for accurate financial analysis and informed decision-making.

## Transactions

**Note:** For a successful upload, it's imperative that the column headings in your file are consistent with the upload names specified in the attribute mapper of Recurly revenue recognition Standalone.

In Standalone revenue recognition, users are equipped with the capability to upload pivotal sales orders, billings, and cost files. These files serve as the backbone for revenue recognition and are integral components in the financial reporting mechanism.

It is essential to load sales orders and invoices into Recurly's Revenue Recognition Standalone. If there are any manual events associated with the contracts, these can also be loaded into the system. Additionally, the cost can be either loaded through files or configured in the system. 

Any data import can be done manually or through APIs. Here is a brief explanation

### How to import transactions manually

1. **Access** the Import/Export section and select "Transactions."
2. **Utilize** the "+" icon to introduce your transaction file into the system. After uploading, always ensure the file is saved.

   <Image align="center" className="border" width="80% " border={true} src="https://files.readme.io/d9290f3-image.png" />
3. It's crucial to ensure that the column headings in your file align with the system's attribute labels. Any discrepancies can hinder the file loading process.
4. Once saved, transaction files are conveniently displayed as cards on the left side of the transaction import window.

   <Image align="center" className="border" border={true} src="https://files.readme.io/98ebb91-image.png" />
5. After the successful upload of transaction files, they can be accessed and examined in the Revenue Workbench, providing a comprehensive overview of your revenue data.

### How to import transactions via API

#### Order Lines:

The Recurly's Revenue Recognition Contract API is used to post a contract to the system. This Recurly's Revenue Recognition API will accept contract lines in a normalized format for the following purposes:

* New contract lines to be published in Recurly's Revenue Recognition.
* Updated contract lines to be re-published in Recurly's Revenue Recognition to capture any changes

```json
Supported POST Call:  
/{baseurl}/api/stage/saveOrderLines

Sample Contract POST Request:  
https\://hostname:port/api/stage/saveOrderLines" 

\[  
{  
        "OrdNumber": "200",  
        "OrdLine": "1",  
        "ConfirmDate": "2022-10-10T00:00:00Z",  
        "SellPrice": 1900,  
        "ListPrice": 2000,  
        "Currency": "USD",  
        "CompanyCurrency": "USD",  
        "CExRate": 1,  
        "GExRate": 1,  
        "StartDate": "2022-10-01T00:00:00Z",  
        "EndDate": "2022-10-30T00:00:00Z",  
        "DeliveryDate": "2022-10-10T00:00:00Z",  
        "Quantity": 1,  
        "Term": 1,  
        "Duration": 1,  
        "SSP": 0,  
        "CV": 0,  
        "Item": "Abc",  
        "Customer": "ABC123",  
        "DRAccount": "11",  
        "CRAccount": "22",  
        "BaseAmount": 0,  
        "ExpectedRnwl": 0,  
        "FINPct": 0,  
        "Company": "abc",  
        "ObjectType": 0,  
        "clientId": 10,  
        "companyId": 0,  
        "createdBy": 0,  
        "updatedBy": 0,  
        "creationDate": "2024-09-04T00:00:00Z",  
        "updateDate": "2024-08-04T12:46:30Z",  
        "f1":"2022-10-01T00:00:00Z",  
        "Allocation":false,  
        "RightToBill":true 

}  
]
```

#### Document lines:

Billing lines must be associated with sales order/contract lines so that the system can calculate billed and unbilled amounts. 

Recurly's Revenue Recognition supports multiple bill line types (“docType”) to support different use cases:

* Invoice bill line types:
  * INV (invoice)
  * IVC (invoice cancellation)
* Credit memo bill line types:
  * CM (Credit Memo)
  * CMR (Credit Memo Return Type)
  * CMC (indicates the line is a credit memo cancellation)  

Additionally, Recurly Revenue Recognition supports multiple credit rules (“creditRule”) to indicate how the system should treat a credit memo type bill line:

* **LIFO**—the credit memo will reduce the deferred revenue balance of the associated distributed bill lines on a “Last in, First Out” basis, otherwise it will reduce the unscheduled deferred revenue balance of the associated bill lines.
* **PRORATE**—the credit memo will reverse the revenue in the same pattern as revenue recognized on the associated bill line. Deferred revenue balance will be reduced if the bill line is not distributed or recognized
* **DOWNGRADE**—the credit memo will reverse the revenue of the associated bill lines based on the start and end date included on the CM

```
Supported POST Call:  
/{baseurl}/api/stage/saveDocLines
```

#### Cost Lines:

The Recurly's Revenue Recognition Cost API is used to post a cost line (e.g. commissions) and its additional attributes required for cost accounting. Each cost is associated with a sales order/contract line and must be published with a soLine + soNumber reference.

```
Supported POST Call:  
/{baseurl}/api/stage/saveCostLines
```

#### Uploading transaction files through API:

Recurly's Revenue Recognition Standlone allows customers to upload transaction files in the Excel format (.xlsx). These uploads can be manual via Import Export -> Transaction UI page or by calling the following end point.

```
Supported POST Call:  
/{baseurl}/api/upload/uploadTranFile

Sample Upload Transaction Request:  
<https://revrec.recurly.com/> api/upload/uploadTranFile?name=SO Demo&fileName=So Demo.xlsx

attachment file as a multipart/form-data

sample successful response will be as under:

{  
    "uploadId": 10691,  
    "name": "SO file 1",  
    "fileName": "SO file 1.xlsx",  
    "errors": null  
}
```

**Notes:**

* Partial credit memos are allowed, but partial invoice cancellations or partial credit memo cancellations are not permitted.
* The system collects transactions that belong to the current open period and previous periods. Transactions associated with future periods are placed in the stage area and are processed once the corresponding period is opened. This ensures accurate and timely processing of transactions in alignment with the period schedule.

## Events

Before initiating an event file upload in Standalone revenue recognition, it's essential to ensure that the file has been meticulously linked with a POB (Performance Obligation) template. This linkage is paramount for the proper mapping of events, ensuring that revenue recognition is both accurate and aligned with contractual obligations.

### How to upload event files

1. Navigate to the Import/Export section and select "Events."
2. Initiate the upload process for a new event file by clicking on the "+" button.

   <Image align="center" className="border" border={true} src="https://files.readme.io/b5d085e-image.png" />
3. Assign a name to the event file. By default, the system will adopt the name of the uploaded file. Subsequently, select the relevant event from the dropdown menu. These events are essentially predefined templates established in the system.
4. Once all the necessary details are populated, save the file. The system will then process the uploaded event file in accordance with the configurations set for that specific event, ensuring that revenue recognition is both accurate and compliant with established rules.

#### How to upload event files using API

The Recurly's Revenue Recognition Event API allows users to input business events, which are individual revenue triggers on one or more sales order/contract lines (e.g. Shipping Date, Customer Acceptance, Percentage Completion).

These business events must be configured in Recurly's Revenue Recognition before using this API. Business Event configuration is found under Policies > Business Events.

```
Supported POST Call:  
/{baseurl}/api/stage/saveEvents
```

## Stage area

The Stage Area in Recurly revenue recognition Standalone contains four tabs: Contracts, Documents, Cost, and Events. Unprocessed files related to each tab will be displayed under their respective tabs. There are several reasons why files may remain unprocessed in the Stage Area:

* **Error in the file:** If there are any errors encountered during the upload of Contracts, Documents, Cost, or Event files, those files will be placed in the Stage Area. The system usually displays error messages corresponding to each transaction, indicating the issue that needs to be addressed.
* **Future transactions:** If any transactions have a future date or period assigned to them and they are uploaded into the system during the current period, these transactions will be held in the Stage Area until the applicable period for those transactions is opened in the system. This ensures that transactions are processed accurately based on their respective periods.
* **Scheduled processing:** If the scheduled jobs for transaction import or event import are not run or are inactive, it can cause transactions to remain stuck in the Stage Area. It is important to ensure that the scheduled jobs are active and properly configured to process the transactions as intended.

### How to view and delete data in the stage area

1. To access the Stage Area, navigate to Import/Export.
2. The "Status" tab provides a structured view of the files, allowing users to filter and view files based on specific criteria.
3. To delete specific data in contract stage, document stage or cost stage, select the transaction under the respective tab, click the Delete icon, and confirm the deletion. Always remember to save changes to finalize the removal. Please note the deletion of event lines in the stage area is not allowed. 

## Journal accounting and period close

## Transfer JE

**Note:** The month-end close process is a structured two-step approach. The initial step involves the meticulous transfer and verification of journal entries, laying the foundation for a confident period closure.

1. Navigation: Go to Import / Export → Transfer JE.
2. Click on the journal card of the primary book to access the journal entries.
3. To double-check and ensure that all entries created are accurate and reflect the correct financial transactions for the period, follow these steps:
   1. **Run the Asset Report:** Generate the Asset Report for the period. Verify that the total of the scheduled column in the asset account matches the total amount displayed in the revenue waterfall report.
   2. **Run the Liability Report:** Generate the Liability Report for the period. Confirm that the total of the scheduled column in the liability account matches the total amount shown in the revenue waterfall report.
   3. **Run the Revenue Waterfall Report:** Generate the Revenue Waterfall Report for the period. Validate that the total amount displayed in the waterfall matches the combined total of the scheduled columns in both the asset and liability accounts.
   4. **Run the Revenue Insight Report:** Generate the Revenue Insight Report. Verify that the scheduled balance in the report matches the total amount displayed in the revenue waterfall report for the period.
4. After completing the reconciliation process, follow these steps to finalize the transfer of journal entries:

   1. Click on   "Approve for Transfer" for the Journal card of the Primary book. This action indicates that the journal entries have been reviewed and approved for transfer.
   2. Once the entries have been approved, click on "Mark as transferred" . This step confirms that the journal entries have been successfully transferred and recorded.
   3. Before proceeding to the next step, ensure that the journal card is "summarized." This summarization consolidates the entries and ensures accurate reporting. Please note that it is crucial to wait until the journal card is summarized before moving forward.

      <Image align="center" className="border" border={true} src="https://files.readme.io/250214f-image.png" />

## Period Close

After transferring journal entries and reconciling your reports as suggested in the step above, the final step is to close the period:

1. **Access** the Period Close option via Import/Export.
2. **Initiate** the next period by selecting "Open New Period."
3. **Confirm** the action and proceed.

   <Image align="center" className="border" border={true} src="https://files.readme.io/993b248-image.png" />
4. **Allow** the system to seamlessly transition to the next period, ensuring continuity in your financial operations.
