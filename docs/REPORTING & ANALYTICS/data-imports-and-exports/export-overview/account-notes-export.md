---
title: Account notes - export
excerpt: Manage and export your internal Account Notes efficiently.
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

The "Account Notes" section is dedicated to helping Recurly users manage and export internal notes associated with various accounts effectively. The export function in this section will help users identify any internal notes published on their accounts with ease, thus aiding in seamless operations and record-keeping.

# Filters

### Time Range Filter

You can filter the account notes that you wish to view based on a specific date range. By selecting a date range, the export will only display account notes that were created during that period, allowing for targeted retrieval of information.

# Exports table

[block:html]
{
  "html": "<!DOCTYPE html>\n<html lang=\"en\">\n<head>\n    <meta charset=\"UTF-8\">\n    <meta http-equiv=\"X-UA-Compatible\" content=\"IE=edge\">\n    <meta name=\"viewport\" content=\"width=device-width, initial-scale=1.0\">\n    <title>Download Button</title>\n    <style>\n        .download-button {\n            display: inline-block;\n            padding: 5px 10px;\n            text-align: center;\n            text-decoration: none;\n            color: #1C2833FF; \n            background-color: #F8F8F8FF; \n            border-radius: 5px;\n            font-weight: normal;\n            transition: background-color 0.5s ease, transform 0.3s ease;\n          \ttransition: 0.4s !important;\n            font-family: 'Proxima-nova', Arial, sans-serif;\n            max-width: 100%; \n        }\n\n        .download-button:hover {\n            background-color: #FFFFFFFF; \n            transform: scale(1.02); \n        }\n      \ta:hover {\n          \tcolor: #888888FF;\n          \ttext-decoration: underline !important;\n        }\n      </style>\n</head>\n<body>\n    <a href=\"https://docs.google.com/spreadsheets/d/1U0_Wl_NMScJqKBZoBKMmQnybmLEr0gFi6r7dfNiP9Qc/export?format=xlsx\" class=\"download-button\">Download our complete export schema</a>\n</body>\n</html>\n\n"
}
[/block]


To help you identify and organize information effectively, the export provides a structured table that contains the following columns:

[block:parameters]
{
  "data": {
    "h-0": "Id",
    "h-1": "Example",
    "h-2": "Description",
    "h-3": "Data type (max size)",
    "0-0": "<span id=\"account_code\">account_code</span>",
    "0-1": "123456789, [janedoe@gmail.com](mailto:janedoe@gmail.com)",
    "0-2": "Account_code is a unique identifier for your customers within Recurly. It defaults to the email address if no specific value is provided. This unmodifiable code is Recurly's primary identifier used to link multiple exports.",
    "0-3": "varchar(50)",
    "1-0": "<span id=\"author_email\">author_email</span>",
    "1-1": "[test@example.com](mailto:test@example.com)",
    "1-2": "The email address of the company user who is the author of the note.",
    "1-3": "varchar(100)",
    "2-0": "<span id=\"message\">message</span>",
    "2-1": "Customer answered survey in exchange for $5 account credit.",
    "2-2": "Describes the content of the account note.",
    "2-3": "string",
    "3-0": "<span id=\"created_at\">created_at</span>",
    "3-1": "2014-01-01 10:00:00 PST",
    "3-2": "The date and time when the account note was created. This field is utilized in the time range filter to sort notes based on their creation dates.",
    "3-3": "timestamp",
    "4-0": "<span id=\"modified_at\">modified_at</span>",
    "4-1": "2014-01-01 10:00:00 PST",
    "4-2": "Indicates the last date and time the account note was updated, helping in tracking the recent modifications.",
    "4-3": "timestamp",
    "5-0": "account_note_api_id",
    "5-1": "e28zov4fw0v2",
    "5-2": "Account note API ID",
    "5-3": "string"
  },
  "cols": 4,
  "rows": 6,
  "align": [
    "left",
    "left",
    "left",
    "left"
  ]
}
[/block]


# Version Changelog

### Version 2 - 02/05/25

- Addition of `account_note_api_id`.