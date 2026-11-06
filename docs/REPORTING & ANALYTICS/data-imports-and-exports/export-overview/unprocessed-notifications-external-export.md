---
title: Unprocessed notifications - external - export
excerpt: >-
  Use this export to find external subscriptions that need attention so future
  notifications for them can be processed.
deprecated: false
hidden: true
metadata:
  title: Unprocessed notifications - external - export
  robots: index
---
# Overview

### Required plan

This feature or setting is available to all customers on any Recurly subscription plan.

### Prerequisites and limitations

You must have enabled connections to app stores to view this export. Please reach out to your Recurly account manager or [support@recurly.com](mailto:support@recurly.com) to have this feature activated in your account.

# Definition

The Unprocessed notifications export lists App Management external subscriptions with notifications from Apple and Google that Recurly was unable to process. Use it to find subscriptions that need attention so future notifications for them can be processed.

- Notifications end up in this export when the subscriber purchased before a customer unique identifier was added to their app store purchase.

## Filters


<Image src="https://files.readme.io/369c7a78d70f9e1b72fa84ba4cffad6ab484d84dbcb2977bf513a08513cc0751-image.png" align="center" width="70%" border={true} />

Use these filters to narrow down the users displayed in your export:

* **Versions**: Select the export version that best fits your needs. Versions are based on the changelog at the bottom of this page
* **Origin**: Defaults to All but Apple App Store or Google Play Store can be selected as well
* **Time range**: Defaults to yesterday, capturing all users created on that day in your site's default time zone

# Exports table

<HTMLBlock>{`
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Download Button</title>
    <style>
        .download-button {
            display: inline-block;
            padding: 5px 10px;
            text-align: center;
            text-decoration: none;
            color: #1C2833FF;
            background-color: #F8F8F8FF;
            border-radius: 5px;
            font-weight: normal;
            transition: background-color 0.5s ease, transform 0.3s ease;
            transition: 0.4s !important;
            font-family: 'Proxima-nova', Arial, sans-serif;
            max-width: 100%;
        }

        .download-button:hover {
            background-color: #FFFFFFFF;
            transform: scale(1.02);
        }
        a:hover {
            color: #1C2833FF;
            text-decoration: underline !important;
        }
    </style>
</head>
<body>
    <a href="https://docs.google.com/spreadsheets/d/1U0_Wl_NMScJqKBZoBKMmQnybmLEr0gFi6r7dfNiP9Qc/export?format=xlsx" class="download-button">Download our complete export schema</a>
</body>
</html>
`}</HTMLBlock>

| Id                                      | Example                            | Description                                                                                                          | Data type |
| :-------------------------------------- | :--------------------------------- | :------------------------------------------------------------------------------------------------------------------- | :-------- |
| <span id="store_id">store_id</span>     | 9256vAC430                         | The external store identifier (e.g. Apple or Google subscriber ID)<br />associated with the unprocessed notification | string    |
| <span id="origin">origin</span>         | Apple App Store, Google Play Store | The origin platform of the notification                                                                              | string    |
| <span id="created_on">created_on</span> | 2026-11-13 10:00:00 PST            | The most recent timestamp at which this external subscription was  unprocessed                                       | timestamp |

# Version changelog

###