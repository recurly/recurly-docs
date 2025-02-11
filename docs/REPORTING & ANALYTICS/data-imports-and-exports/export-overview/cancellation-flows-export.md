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

An entry is created each time the *Create a new survey session* API call is made. When using the *Update a survey session* API to record the customer's response the response\_text, response\_number, and position fields are updated.

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

To help you identify and organize information effectively, the export provides a structured table that contains the following columns:

| Column Name        | Example                                | Description                                                                                                                                                                                                                                                  |
| :----------------- | :------------------------------------- | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| session\_id        | 3767797751318006536                    | The customer's session ID.                                                                                                                                                                                                                                   |
| session\_date      | 02/10/2023 15:25 UTC                   | The date and time the new session was generated (aka the time customer began the cancellation workflow).                                                                                                                                                     |
| subscription\_uuid | 654705570182ff58cd8fb949b6b6f957       | Unique internal identifier for the subscription. Even if a subscription is modified, this identifier is maintained.                                                                                                                                          |
| account\_code      | 10142022                               | Account\_code uniquely identifies your customers inside of Recurly. This field defaults to email address, if no specific value is provided. Account\_code cannot be modified. This is the main Recurly identifier, and can be used to join multiple exports. |
| plan\_code         | eph57                                  | The code associated with the Plan the customer is thinking of canceling.                                                                                                                                                                                     |
| response\_text     | My free trial or special offer expired | The text of the response presented to the customer.                                                                                                                                                                                                          |
| response\_number   | 004                                    | The auto-generated, friendly ID, associated with the response. For Recurly provided default responses the value is 001-016.                                                                                                                                  |
| position           | 2                                      | Where, in the order of the responses presented, this specific response was located.                                                                                                                                                                          |
