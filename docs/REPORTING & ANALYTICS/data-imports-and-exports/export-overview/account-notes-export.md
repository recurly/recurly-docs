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

<Table align={["left","left","left","left"]}>
  <thead>
    <tr>
      <th style={{ textAlign: "left" }}>
        Id
      </th>

      <th style={{ textAlign: "left" }}>
        Example
      </th>

      <th style={{ textAlign: "left" }}>
        Description
      </th>

      <th style={{ textAlign: "left" }}>
        Data type (max size)
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="account_code">account\_code</span>
      </td>

      <td style={{ textAlign: "left" }}>
        123456789, [janedoe@gmail.com](mailto:janedoe@gmail.com)
      </td>

      <td style={{ textAlign: "left" }}>
        Account\_code is a unique identifier for your customers within Recurly. It defaults to the email address if no specific value is provided. This unmodifiable code is Recurly's primary identifier used to link multiple exports.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(50)
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="author_email">author\_email</span>
      </td>

      <td style={{ textAlign: "left" }}>
        [test@example.com](mailto:test@example.com)
      </td>

      <td style={{ textAlign: "left" }}>
        The email address of the company user who is the author of the note.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(100)
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="message">message</span>
      </td>

      <td style={{ textAlign: "left" }}>
        Customer answered survey in exchange for $5 account credit.
      </td>

      <td style={{ textAlign: "left" }}>
        Describes the content of the account note.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="created_at">created\_at</span>
      </td>

      <td style={{ textAlign: "left" }}>
        2014-01-01 10:00:00 PST
      </td>

      <td style={{ textAlign: "left" }}>
        The date and time when the account note was created. This field is utilized in the time range filter to sort notes based on their creation dates.
      </td>

      <td style={{ textAlign: "left" }}>
        timestamp
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="modified_at">modified\_at</span>
      </td>

      <td style={{ textAlign: "left" }}>
        2014-01-01 10:00:00 PST
      </td>

      <td style={{ textAlign: "left" }}>
        Indicates the last date and time the account note was updated, helping in tracking the recent modifications.
      </td>

      <td style={{ textAlign: "left" }}>
        timestamp
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        account\_note\_api\_id
      </td>

      <td style={{ textAlign: "left" }}>
        e28zov4fw0v2
      </td>

      <td style={{ textAlign: "left" }}>
        Account note API ID
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>
  </tbody>
</Table>

# Version Changelog

### Version 2 - 02/05/25

* Addition of `account_note_api_id`.
