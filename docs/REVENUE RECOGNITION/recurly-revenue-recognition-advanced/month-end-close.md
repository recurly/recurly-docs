---
title: Month end close
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

To properly close a month in RevRec, follow these steps in order. Avoid opening the next period until each step is completed.

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
* Go to **Reports → Documents Stage Report** for the open period.
* Verify there are no unprocessed transactions or errors for the current period.
  * Resolve errors before proceeding, or they won’t be included in the closed period’s numbers.
  * For large datasets, download the reports to assist with troubleshooting.

### 2. Verification of exception reports

<a name="2-verification-of-exception-reports" />

1. **SSP Exception Report**
   * Go to **Reports → Exception Reports** and select **SSP Exception**.
   * Ensure no contracts that require SSP allocation are listed. If a contract needs allocation, create a new SSP with an active date preceding the contract date and then re-run allocation using the Revenue Workbench.
2. **Hold Exception Report**
   * Go to **Reports → Exception Reports** and select **Hold Exception**.
   * Confirm that any items on hold are meant to be on hold. If you need to remove a hold so revenue is recognized, open the contract in Revenue Workbench and manually release the appropriate amount.

### 3) Reconciliation of reports

<a name="3-reconciliation-of-reports" />

* Run the **Asset Report**, **Liability Report**, and **Revenue Waterfall Report** for the period.
  * The sum of the scheduled columns in the Asset and Liability Reports should match the total in the Revenue Waterfall for the period.
* Run the **Revenue Insight Report**.
  * The scheduled balance in Revenue Insight should also match the Revenue Waterfall total.
* Confirm these reports are aligned before proceeding.

### 4. Transferring journal entry

<a name="4-transferring-journal-entry" />

* Go to **Import/Export → Transfer JE**.
* Select the journal card for the primary book, review entries, and click **Approve for Transfer**.
* If you’re pulling data via API, confirm it populates in your accounting system.
  * If manual, download the Journal Entry and upload it based on your internal process.
* Wait for the reports to refresh (it may take up to an hour for large datasets).
  * Re-run **Asset** and **Liability** Reports. The **Unaccounted** columns should be zero before proceeding.

### 5. Closing the period

<a name="5-closing-the-period" />

* Go to **Import/Export → Period Close**.
* Click **Open New Period** (top right). Follow the prompts until the next period is open.
* Once closed, the system will trigger new-period transactions to flow into RevRec.

**Note:** Before opening the next period, ensure all unaccounted balances are zero. If you see any remaining items, investigate and resolve them first.