---
title: Transfer accounting details report
excerpt: >-
  Explore the detailed guide on the Transfer Account Details report in Recurly's
  Revenue Recognition user guide.
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

The **Transfer Account Details Report** allows for a detailed monthly view of your journal entries, offering flexibility to customize the format according to your needs. This guide will explain the steps to access, configure, and interpret the Transfer Account Details Report effectively.

# Guide

## Accessing and Configuring the Report

To access and configure the Transfer Account Details Report:

1. **Navigate to the Report:**
   * Go to **Reports** and select **Transfer Account Details** from the menu.

2. **Configure the Report:**
   * Click on the **Mapper icon** to open a dialogue box.
   * Here you can determine which columns appear in the report, as well as what you want to use as a search field.
   * Under the **Results** column, ensure that **Account**, **Dr Amount**, and **Cr Amount** are checked to display these details in the report:
     * **Account:** The name of the General Ledger account.
     * **Dr Amount:** The amount of the debit.
     * **Cr Amount:** The amount of the credit.
   * You can add more columns to the report or as search fields if needed. Simply check the columns you want to add in the mapper.
   * Click **Save** to confirm your selections.

3. **Run the Report:**
   * Once the columns and search fields are set, enter any specific search criteria in the provided fields, or leave them blank to include all data.
   * Click the **Run** button to generate the report. All transactions for the period chosen will be displayed based on the selected columns.

## About the report features

1. **Viewing Transactions:**
   * The generated report will display all transactions for the selected period with the specified columns.
   * Totals for the debits and credits are visible at the bottom of the report, making it easier to analyze the accounts.

2. **Searching for Specific Contracts:**
   * To find transfer accounting details for a specific contract, enter the contract ID in the search field (e.g., **Contract 77376**).
   * The report will display lines representing the different accounts affected by the contract. Each line shows the debited or credited amount and the account number for that amount.
   * Example:
     * **Batch ID:** 10049 (Matches the JE card in Transfer JE)
     * **Period ID:** 24 03 (Indicates March 2024)

3. **Total Balances:**
   * The report allows you to see the total balances in one or all accounts, similar to the Transfer JE card, by aggregating the debits and credits. This feature simplifies the process of analyzing and comparing accounts.

## Report columns

The **Transfer Account Details Report** includes several key columns, which can be customized to display the most relevant information for your needs:

* **Account**: Displays the General Ledger account name associated with each transaction. This column helps you identify which accounts are involved in the entries.

* **Dr Amount**: Shows the amount of the debit for each entry. Debits are transactions that either increase an asset or expense account, or decrease a liability or equity account.

* **Cr Amount**: Shows the amount of the credit for each entry. Credits are transactions that either decrease an asset or expense account, or increase a liability or equity account.

You can add more columns to the report or use them as search fields by selecting additional options in the mapper. This flexibility allows you to tailor the report to meet your specific analysis requirements.

**Other available columns might include:**

* **Batch ID**: The unique identifier for a group of transactions processed together. Useful for tracing back the entries to a specific batch.
* **Period ID**: Indicates the accounting period (e.g., "24 03" for March 2024). Helps in filtering or segmenting the data by specific periods.
* **Contract ID**: The unique identifier for contracts. Helps you quickly locate transactions related to specific contracts.