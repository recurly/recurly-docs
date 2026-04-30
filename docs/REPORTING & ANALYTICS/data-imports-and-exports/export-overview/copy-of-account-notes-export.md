---
title: Copy of Account notes - export
excerpt: Manage and export your internal Account Notes efficiently.
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

### Required plan

This feature or setting is available to all customers on any Recurly subscription plan.

# Definition

The "Account Notes" section is dedicated to helping Recurly users manage and export internal notes associated with various accounts effectively. The export function in this section will help users identify any internal notes published on their accounts with ease, thus aiding in seamless operations and record-keeping.

<Image border={false} src="https://files.readme.io/7ea101390a61bd2d8d46b7452e08b1a8e97960e69c8fe6a2175b46ce39ac6a3b-image.png" />

<br />

# Filters

### Versions Filter

* The Versions filter allows you to select the version that is most appropriate for your needs. This is based on the version changelog at the bottom of this page.

### Time Range Filter

By selecting a time range, the export will only display account notes that were created during that period, allowing for targeted retrieval of information.

* The Time range filter (dropdown) allows you to view data within a specific period such as last month, year to date or a custom date range. The **Start Date** and **End Date** will automatically update based on the value selected in the Time range filter. You can also choose "Between..." in the dropdown, which will allow you to enter a customized date range.

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
          	color: #888888FF;
          	text-decoration: underline !important;
        }
      </style>
</head>
<body>
    <a href="https://docs.google.com/spreadsheets/d/1U0_Wl_NMScJqKBZoBKMmQnybmLEr0gFi6r7dfNiP9Qc/export?format=xlsx" class="download-button">Download our complete export schema</a>
</body>
</html>
`}</HTMLBlock>

To help you identify and organize information effectively, the export provides a structured table that contains the following columns:

| Id                                          | Example                                                     | Description                                                                                                                                                                                                                     | Data type (max size) |
| :------------------------------------------ | :---------------------------------------------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :------------------- |
| <span id="account_code">account_code</span> | 123456789, [janedoe@gmail.com](mailto:janedoe@gmail.com)    | Account_code is a unique identifier for your customers within Recurly. It defaults to the email address if no specific value is provided. This unmodifiable code is Recurly's primary identifier used to link multiple exports. | varchar(50)          |
| <span id="author_email">author_email</span> | [test@example.com](mailto:test@example.com)                 | The email address of the company user who is the author of the note.                                                                                                                                                            | varchar(100)         |
| <span id="message">message</span>           | Customer answered survey in exchange for $5 account credit. | Describes the content of the account note.                                                                                                                                                                                      | string               |
| <span id="created_at">created_at</span>     | 2014-01-01 10:00:00 PST                                     | The date and time when the account note was created. This field is utilized in the time range filter to sort notes based on their creation dates.                                                                               | timestamp            |
| <span id="modified_at">modified_at</span>   | 2014-01-01 10:00:00 PST                                     | Indicates the last date and time the account note was updated, helping in tracking the recent modifications.                                                                                                                    | timestamp            |
| account_note_api_id                         | e28zov4fw0v2                                                | Account note API ID                                                                                                                                                                                                             | string               |

# Version Changelog

### Version 2 - 02/05/25

* Addition of `account_note_api_id`.