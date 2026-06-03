---
title: Custom exports
excerpt: >-
  Get a tailored data extract with exactly which information you need to meet
  your business needs
deprecated: false
hidden: true
metadata:
  title: custom export
  robots: index
---
# Overview

The Custom Exports feature gives you direct visibility into the tailored and automated data exports configured for your merchant account. These are not standardized reports but configured with specific data fields, filters based on your business needs. From the Custom Exports page, you can see every active export at a glance — including where your data is going, how often it runs, and where to access.

### Required plan

This export is available as an optional add-on for customers on all Recurly's plans. Reach out to Support or your CSM for more information.

<br />

> 🚧 Please Note: Merchant Read-Only Access
>
> * Merchants can view export configurations but cannot create or edit exports.
> * All custom export setup and scheduling is managed by the Recurly team.
> * To request a new export, modify an existing one, or troubleshoot an error, contact Recurly Support.

# Key benefits

* **Data tailored to your specific needs**: Unlike standard Exports (which offer a fixed set of reports), Custom Exports are built by Recurly to match a merchant's exact reporting requirements — specific fields, combinations of data, or outputs their standard systems can't produce.
* **Flexible scheduling**: Custom exports can run daily, monthly or on fully custom cron schedules, which is important for merchants with non-standard billing cycles or reporting windows.
* **Fits into existing infrastructure**:  Files land directly in the merchant's own storage (S3, GDrive, SFTP), so they slot into existing data pipelines and warehouses without any API work on the merchant's side.
* **Visibility into export health (new)**: The merchant-facing UI page is actually a new feature. Previously merchants had no visibility into their custom exports. Now they can see status, destination, and frequency at a glance — and take action when something errors (update a secret, verify, etc.).

<br />

## Accessing Your Custom Exports

To view your custom exports:

1. From the Recurly Admin UI, in the left navigation panel, click Integrations.
2. Click Custom Exports from the Integrations sub-menu.
3. The Custom Exports list will display all exports configured for your account.
4. Files are delivered to your configured destination (AWS S3, Google Drive, or SFTP). The Custom Exports page shows configuration and status only — it does not host file downloads.
5. Depending on the export target (AWS S3, SFTP, etc.), you may need to update your secret key and/or verify in order to access your custom export from your configured destination.

<br />

## Reading the Custom Exports Table

Each row in the table represents a single export configuration. The table includes the following columns:

<br />

|                             |                                                                                                                               |   |
| :-------------------------- | :---------------------------------------------------------------------------------------------------------------------------- | - |
| Name                        | A unique identifier for the export job, typically describing the report type and destination.                                 |   |
| Bucket / URL / Folder ID    | The destination where exported files are delivered - an Amazon S3 bucket name, a Google Drive folder ID, or a SFTP host path. |   |
| Path Prefix                 | The sub-path or folder within the destination where files are stored.                                                         |   |
| Target                      | The type of destination system - AWS S3, Google Drive, or SFTP.                                                               |   |
| Frequency                   | How often the export runs. Common values are Daily or Custom, e.g. 15th and 30th of each month.                               |   |
| Update Secret/Verify/Delete |                                                                                                                               |   |

<br />