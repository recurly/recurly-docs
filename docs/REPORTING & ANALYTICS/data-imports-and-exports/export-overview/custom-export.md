---
title: Custom Export
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

![](https://files.readme.io/e59e3dc29896b828bf0ea350f116c1b8475b6b71d9ffb54487614f9874057c8a-image.png)

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