---
title: Manual month end close
excerpt: >-
  Use Recurly’s Revenue Recognition Advanced to finalize each billing period
  with accuracy. By following a structured close process, you can ensure all
  transactions are accounted for and properly reflected in your General Ledger.
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

### Required plan

This feature is included in Recurly Revenue Recognition Advanced. [Learn more here](https://docs.recurly.com/docs/recurly-revenue-recognition-advanced).

### Additional cost

This feature or setting requires an additional cost. Please reach out to your Recurly account manager or [support](mailto:support@recurly.com) for more pricing details.

# Definition

Month End Close is a formal process that ensures all revenue-related transactions are accurately captured and reconciled before closing one period and opening the next. It involves verifying data, checking for exceptions, reconciling reports, and transferring journal entries.

# Key benefits

* **Accurate financial reporting**: Ensures your data is complete and consistent for each period.
* **Reduced errors**: Identifies and resolves exceptions (e.g., holds, missing allocations) before closing.
* **Streamlined workflows**: Simplifies the process of reconciling revenue and transferring journal entries.

## How to do Month End Close

To properly close a month in Recurly Revenue Recognition, follow these steps in order. Avoid opening the next period until each step is completed.

<Cards columns={4}>
  <Card title="Stage data verification" href="#1-stage-data-verification" icon="fa-check-circle">
    Make sure there are no unprocessed transactions or errors in the Contract Stage and Documents Stage Reports.
  </Card>

  <Card title="Verification of exception reports" href="#2-verification-of-exception-reports" icon="fa-exclamation-triangle">
    Review SSP and Hold Exception Reports and address any issues requiring allocation or hold removal.
  </Card>

  <Card title="Reconciliation of reports" href="#3-reconciliation-of-reports" icon="fa-list-alt">
    Compare Asset, Liability, Revenue Waterfall, and Revenue Insight Reports to ensure they match.
  </Card>

  <Card title="Transferring journal entry" href="#4-transferring-journal-entry" icon="fa-file-invoice-dollar">
    Approve and transfer journal entries to your GL, making sure unaccounted balances are zero.
  </Card>

  <Card title="Closing the period" href="#5-closing-the-period" icon="fa-door-closed">
    Finalize the current period, open the next, and allow new transactions to flow into RevRec.
  </Card>
</Cards>

### 1. Stage data verification

<a name="1-stage-data-verification" />

* Go to **Reports → Contract Stage Report** for the open period.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/87e66112d016da85db1425dac2c0ac9fcb7cf30aba6a396f5d3e5c3765ef624a-1.Contract_Stage_Details.png" />

* Go to **Reports → Documents Stage Report** for the open period.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/97117ef674d798eb66dfa6342a439d17d6b9d176f69c3c08a652e4823df1d48a-2.Doc_Stage_details.png" />

* Verify there are no unprocessed transactions or errors for the current period.
  * Resolve errors before proceeding, or they won’t be included in the closed period’s numbers.
  * For large datasets, download the reports to assist with troubleshooting.

### 2. Verification of exception reports

<a name="2-verification-of-exception-reports" />

1. **SSP Exception Report**

   * Go to **Reports → Exception Reports** and select **SSP Exception**.

   <br />

   <Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/ba90fdebf651af6f1bf6d75801de58cff58900bd70993d0b9de65ad51dabf11a-3.SSP_Exception_Report.png" />

   * Ensure no contracts that require SSP allocation are listed. If a contract needs allocation, create a new SSP with an active date preceding the contract date and then re-run allocation using the Revenue Workbench.
2. **Hold Exception Report**

   * Go to **Reports → Exception Reports** and select **Hold Exception**.

   <Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/f678cd64d5f85d4a1de45f5e816b37fad181a38f93261eff64862dd640ec9556-4.Hold_Exception_Report.png" />

   * Confirm that any items on hold are meant to be on hold. If you need to remove a hold so revenue is recognized, open the contract in Revenue Workbench and manually release the appropriate amount.

### 3) Reconciliation of reports

<a name="3-reconciliation-of-reports" />

* Run the **Asset Report**, **Liability Report**, and **Revenue Waterfall Report** for the period.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/21a29e5ad17413c5553ef71524026df005eda591edc6fe001255f589f92a4c78-5.Scheduled_Reconcillation.png" />

* The sum of the scheduled columns in the Asset and Liability Reports should match the total in the Revenue Waterfall for the period.
* Run the **Revenue Insight Report**.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/2c2b5e7d9af9cb5e852dbdd3468716ca1a03b33b390e819e05e616e88187de1f-9.Revenue_Insight_Report.png" />

* The scheduled balance in Revenue Insight should also match the Revenue Waterfall total.
* Confirm these reports are aligned before proceeding.

### 4. Transferring journal entry

<a name="4-transferring-journal-entry" />

* Go to **Import/Export → Transfer JE**.

<Image align="center" className="border" border={true} width="40% " src="https://files.readme.io/ed967fb23929f3f05476e069c06f13d53ba90ebab399153bd527a37fd50d50f3-11.Transfer_JE.png" />

* Select the journal card for the primary book, review entries, and click **Approve for Transfer**.

<Image align="center" border={true} caption="Select the journal" src="https://files.readme.io/299a36179bef07272c8ad2e76b4f1598154c44af4fbac4c32f53fc7d1610ca69-12.Primary_book_-_trasnfer_JE.png" width="40% " />

<Image align="center" border={false} caption="Approve for Transfer" src="https://files.readme.io/292913e82c3ece3bca035d243f90a9437e71563e31eb00bc0cc8e85bed1a9b4c-13.Transfer_JE_-_Approve_for_Transfer.png" />

<Image align="center" border={false} caption="Mark as Trasnferred" src="https://files.readme.io/6c9fe2bee1f74a222221b94f45a536046c836ff8afc943465fc4772e0b5a7418-14.Transfer_JE_-_Mark_as_Transferred.png" />

<br />

* If you’re pulling data via API, confirm it populates in your accounting system.
  * If manual, download the Journal Entry and upload it based on your internal process.
* Wait for the reports to refresh (it may take up to an hour for large datasets).

  * Re-run **Asset** and **Liability** Reports. The **Unaccounted** columns should be zero before proceeding.

  <br />

  <Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/03ac05643b3584c4fe203f6adaac605ce04560660685bf0d21b6d4d483ee64ad-15.Unaccounted_Total.png" />

  <br />

### 5. Closing the period

<a name="5-closing-the-period" />

* Go to **Import/Export → Period Close**.

<Image align="center" className="border" border={true} width="40% " src="https://files.readme.io/dcae5e6085c4bcc3e5c6bcac59e09bdfb2b2e36336411b18f570a8601888adb2-16.Period_Close_-_Imp_Export.png" />

* Click **Open New Period** (top right). Follow the prompts until the next period is open.

<Image align="center" className="border" border={true} src="https://files.readme.io/6c29367a76fc2e663832c620697cf4c29664ccf10c630c9b44bc8872a253521c-17.Period_close_-_Open_next.png" />

* Once closed, the system will trigger new-period transactions to flow into RevRec.

**Note:** Before opening the next period, ensure all unaccounted balances are zero. If you see any remaining items, investigate and resolve them first.