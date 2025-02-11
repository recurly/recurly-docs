---
title: Cancellation flows - export
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
A Cancellation Flows export is available for configuration as a manual and automated export. The export provides data to enable you to gain an understanding as to why your customers are canceling, monitor trends such as if the position of the response makes a difference, and provides insights into cancel behavior. 

An entry is created each time the _Create a new survey session_ API call is made. When using the _Update a survey session_ API to record the customer's response the response_text, response_number, and position fields are updated.

# Exports table

[block:html]
{
  "html": "<!DOCTYPE html>\n<html lang=\"en\">\n<head>\n    <meta charset=\"UTF-8\">\n    <meta http-equiv=\"X-UA-Compatible\" content=\"IE=edge\">\n    <meta name=\"viewport\" content=\"width=device-width, initial-scale=1.0\">\n    <title>Download Button</title>\n    <style>\n        .download-button {\n            display: inline-block;\n            padding: 5px 10px;\n            text-align: center;\n            text-decoration: none;\n            color: #1C2833FF; \n            background-color: #F8F8F8FF; \n            border-radius: 5px;\n            font-weight: normal;\n            transition: background-color 0.5s ease, transform 0.3s ease;\n          \ttransition: 0.4s !important;\n            font-family: 'Proxima-nova', Arial, sans-serif;\n            max-width: 100%; \n        }\n\n        .download-button:hover {\n            background-color: #FFFFFFFF; \n            transform: scale(1.02); \n        }\n      \ta:hover {\n          \tcolor: #1C2833FF;\n          \ttext-decoration: underline !important;\n        }\n      </style>\n</head>\n<body>\n    <a href=\"https://docs.google.com/spreadsheets/d/1U0_Wl_NMScJqKBZoBKMmQnybmLEr0gFi6r7dfNiP9Qc/export?format=xlsx\" class=\"download-button\">Download our complete export schema</a>\n</body>\n</html>\n\n"
}
[/block]


To help you identify and organize information effectively, the export provides a structured table that contains the following columns:

| Column Name       | Example                                | Description                                                                                                                                                                                                                                                |
| :---------------- | :------------------------------------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| session_id        | 3767797751318006536                    | The customer's session ID.                                                                                                                                                                                                                                 |
| session_date      | 02/10/2023 15:25 UTC                   | The date and time the new session was generated (aka the time customer began the cancellation workflow).                                                                                                                                                   |
| subscription_uuid | 654705570182ff58cd8fb949b6b6f957       | Unique internal identifier for the subscription. Even if a subscription is modified, this identifier is maintained.                                                                                                                                        |
| account_code      | 10142022                               | Account_code uniquely identifies your customers inside of Recurly. This field defaults to email address, if no specific value is provided. Account_code cannot be modified. This is the main Recurly identifier, and can be used to join multiple exports. |
| plan_code         | eph57                                  | The code associated with the Plan the customer is thinking of canceling.                                                                                                                                                                                   |
| response_text     | My free trial or special offer expired | The text of the response presented to the customer.                                                                                                                                                                                                        |
| response_number   | 004                                    | The auto-generated, friendly ID, associated with the response. For Recurly provided default responses the value is 001-016.                                                                                                                                |
| position          | 2                                      | Where, in the order of the responses presented, this specific response was located.                                                                                                                                                                        |