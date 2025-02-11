---
title: Beta Program Docs
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
##Welcome to Bring Your Own Gateway, Beta Program!##

In the current phase of BYOG our Beta Partners will be able to define their gateway configuration, define templates and test purchase requests (Updated July 22, 2021)



## Getting a Recurly Site

Partner gateways will use a Recurly site to develop and test your BYOG integration. 

1) Sign up for a free account here: https://app.recurly.com/signup

2) Work with your beta partnership contact to put site in development mode



## Authentication

Generate a Basic Authentication header with the credentials from the API Credentials page [API Credentials page](https://app.recurly.com/go/developer/api_keys). 
Also, pass the header `Accept: application/vnd.recurly.v2021-02-25`


## Configuration API




[block:tutorial-tile]
{
  "title": "Configuration",
  "id": "60c938250a6d9b0069c20436",
  "slug": "configuration",
  "backgroundColor": "#018FF4",
  "emoji": "🦉",
  "link": "https://docs.recurly.com/v1.0/recipes/configuration",
  "align": "default",
  "_id": "60c938250a6d9b0069c20436"
}
[/block]

## **Configuration Request**

This is where you will define what fields your merchants should configure when adding your payment gateway to Recurly. Additionally, this will instruct how your gateway operates, and any specific parameters that would need to be configured, such as `single_currency_per_account`. 
The fields defined here will appear in the Recurly UI under Gateway Configuration

`POST https://app.recurly.com/payment_gateway_partners/`



[block:parameters]
{
  "data": {
    "h-0": "Field",
    "h-1": "Type",
    "7-0": "For each field, define:",
    "8-0": "secret",
    "8-1": "Boolean",
    "8-2": "Sets value as a secret, please use True for your password/API Key field",
    "11-0": "label",
    "11-1": "String",
    "11-2": "Field name merchant should see when configuring payment gateway in Recurly",
    "12-0": "field_name_in_template",
    "12-1": "String",
    "12-2": "field name you'll use when including this field in a template (can be same as label)",
    "9-0": "required",
    "9-1": "Boolean",
    "9-2": "Is field required for your gateway configuration",
    "10-0": "order",
    "10-1": "Number",
    "10-2": "Order of field when displayed in Recurly's gateway configuration UI",
    "h-2": "Notes",
    "6-0": "fields",
    "6-1": "Object",
    "0-0": "single_currency_per_account",
    "0-2": "Defines if merchant account can have multiple currencies. Defaults to False",
    "0-1": "Boolean",
    "4-0": "zero_dollar_auth",
    "4-2": "Required. Does the gateway accept 0 dollar authorizations? If False, verifications will default to 1.",
    "4-1": "Boolean",
    "5-0": "zero_dollar_auth_without_address",
    "5-2": "Required. Does the gateway allow 0 dollar authorization without a billing address present?",
    "5-1": "Boolean",
    "3-0": "merchant_countries",
    "3-2": "Required. Comma delimited list of acceptable merchant countries. Must be ISO code.",
    "3-1": "Array",
    "6-2": "",
    "1-0": "name",
    "1-1": "String",
    "2-0": "logo",
    "2-1": "String",
    "2-2": "Fully qualified URL path to a hosted image for your gateway's logo",
    "1-2": "Your gateway's name"
  },
  "cols": 3,
  "rows": 13
}
[/block]

## **Configuration Response**

In addition to a reflection of the applied fields above, you will also receive an `id` field which will need to be used in later API calls as the "gateway_id" in the route.


[block:parameters]
{
  "data": {
    "0-0": "id",
    "1-0": "name",
    "2-0": "logo",
    "3-0": "single_currency_per_account",
    "4-0": "zero_dollar_auth",
    "5-0": "zero_dollar_auth_without_address",
    "6-0": "merchant_countries",
    "7-0": "fields",
    "8-0": "created_at",
    "9-0": "updated_at",
    "h-0": "Field",
    "h-1": "Type",
    "h-2": "Notes",
    "0-1": "String",
    "1-1": "String",
    "2-1": "String",
    "3-1": "Boolean",
    "4-1": "Boolean",
    "5-1": "Boolean",
    "6-1": "Array",
    "7-1": "Object",
    "8-1": "String",
    "9-1": "String",
    "8-2": "date-time formatted string of when the template was created",
    "9-2": "date-time formatted string of when the template was last updated",
    "7-2": "Reflection of created fields in the template",
    "6-2": "Array of merchant country codes",
    "0-2": "Recurly-generated UUID that will be used to select this configuration in future API calls",
    "1-2": "Your gateway's name",
    "2-2": "Fully qualified URL path to a hosted image for your gateway's logo",
    "3-2": "Defines if merchant account can have multiple currencies. Defaults to False",
    "4-2": "Indicates if the gateway accept 0 dollar authorizations? If False, verifications will default to 1.",
    "5-2": "Indicates if the gateway allow 0 dollar authorization without a billing address present?"
  },
  "cols": 3,
  "rows": 10
}
[/block]




## Template API: Requests




[block:tutorial-tile]
{
  "title": "Define Request Templates",
  "emoji": "🦉",
  "backgroundColor": "#018FF4",
  "slug": "define-request-templates",
  "_id": "60e4cfe451cb9900497aa104",
  "id": "60e4cfe451cb9900497aa104",
  "link": "https://docs.recurly.com/v1.0/recipes/define-request-templates"
}
[/block]

The Template API defines how to map Recurly fields to partner gateway fields. Templates will be triggered based on actions from merchants. For example, a template with the action: purchase will be applied each time an applicable purchase

`POST /payment_gateway_partners/{gateway_id}/request_templates`
`GET /payment_gateway_partners/{gateway_id}/request_templates`
`PATCH /payment_gateway_partners/{gateway_id}/request_templates/{template_id}`


[block:parameters]
{
  "data": {
    "h-0": "Field",
    "h-1": "Type",
    "h-2": "Notes",
    "0-0": "url",
    "0-1": "String",
    "0-2": "Required. The liquid template for the URL that will be used to perform the requests to your gateway when the merchant's site is in productction mode.",
    "2-0": "payment_action",
    "2-1": "String",
    "2-2": "Required. Supported values: verification, purchase, refund, renewal, void",
    "4-0": "body",
    "4-1": "String",
    "4-2": "Required. String that defines your liquid template for the action.",
    "5-0": "headers",
    "5-2": "Optional. Use it to add custom headers, if needed. Provide them in the form\n{\"Header1\": \"HeaderValueLiquidTemplate1\", \"Header2\": \"HeaderValueLiquidTemplate2\"}",
    "5-1": "Object",
    "6-0": "content_type",
    "6-1": "String",
    "6-2": "Optional. The liquid template for the Content-Type header that will be used in the request.",
    "7-0": "accept",
    "7-1": "String",
    "7-2": "Optional. The liquid template for  the Accept header that will be used in the request.",
    "8-0": "authorization",
    "8-1": "String",
    "8-2": "Optional. The liquid template for the Authorization header that will be used in the request.",
    "3-0": "template_name",
    "3-1": "String",
    "3-2": "Optional: if not provided, name we default to the template ID",
    "1-0": "test_url",
    "1-1": "String",
    "1-2": "Required. The liquid template for the URL that will be used to perform the requests to your gateway when the merchant's site is in development or sandbox mode."
  },
  "cols": 3,
  "rows": 9
}
[/block]




## Recurly Fields: Requests

Our templating leverages [Liquid templating language](https://liquidjs.com/tutorials/intro-to-liquid.html). For each field defined in your template you'll follow the format `{"your_gateway_parameter" : "{{ recurly.field }}"`


Below are the Recurly fields available for inclusion in your template


[block:parameters]
{
  "data": {
    "0-0": "transaction.amount",
    "1-0": "transaction.currency",
    "2-0": "transaction.country",
    "3-0": "transaction.description",
    "4-0": "transaction.invoice_number",
    "9-0": "billing_info.number",
    "10-0": "billing_info.first_name",
    "11-0": "billing_info.last_name",
    "12-0": "billing_info.year",
    "13-0": "billing_info.month",
    "14-0": "billing_info.cvv",
    "15-0": "billing_info.address.address1",
    "16-0": "billing_info.address.address2",
    "17-0": "billing_info.address.city",
    "18-0": "billing_info.address.state",
    "19-0": "billing_info.address.zip",
    "20-0": "billing_info.phone",
    "21-0": "billing_info.ip_address",
    "h-0": "Recurly Field",
    "h-1": "Format",
    "h-2": "Description",
    "0-1": "minor units. Formatted String",
    "1-1": "String. 3 letters",
    "1-2": "ISO Code. Currency of transaction.",
    "2-1": "String. 2 letters",
    "2-2": "ISO Code. \n\nRecurly V2: determined by the billing address of shopper or issuing country of billing info on file. \n\nRecurly V3: Submitted by merchant, or determined by shopper IP if no value submitted.",
    "3-1": "String. Max length 50.",
    "4-1": "Number",
    "4-2": "Invoice number, generated by Recurly upon invoice generation.",
    "3-2": "Submitted by merchant.",
    "9-1": "Number, 16 digits",
    "9-2": "Credit Card PAN",
    "10-1": "String",
    "10-2": "",
    "11-1": "String",
    "12-1": "String. 4 characters.",
    "12-2": "Expiration Year",
    "13-1": "String. 2 characters",
    "13-2": "Expiration Month",
    "14-1": "String",
    "14-2": "CVV of card",
    "15-1": "string",
    "16-1": "string",
    "17-1": "string",
    "18-1": "string. 2 letters",
    "20-1": "string",
    "21-1": "string. 20 characters.",
    "24-0": "config",
    "24-1": "object",
    "24-2": "This will contain all the configuration field values defined by the merchant in the gateway configuration page.",
    "25-0": "live",
    "25-1": "boolean",
    "25-2": "This variable indicates if the merchant site is configured for production/live mode or not.",
    "5-0": "transaction.original_reference",
    "5-1": "String",
    "5-2": "Partner identification of the original transaction that is being refunded. \nIt is provided only in refunds.",
    "22-0": "billing_info.tax_identifier",
    "22-1": "string",
    "22-2": "tax id for the shopper. CPF for Brazil, CUIT for Argentina",
    "23-0": "billing_info.tax_identifier_type",
    "23-1": "string",
    "23-2": "type of tax identifier passed. CPF for Brazil, CUIT for Argentina",
    "6-0": "transaction.shopper_in_session",
    "6-1": "Boolean",
    "6-2": "Indicates that this is a CIT (Customer-Initiated Transaction).\nIt is true when the transaction is created via Hosted Pages, RecurlyJS or API (this one with IPAddress informed by the merchant).",
    "7-0": "transaction.stored_billing_info",
    "7-1": "Boolean",
    "7-2": "Indicates that the current transaction uses a previously stored billing info. It is true when an account code is referenced or in renewal transactions.",
    "8-0": "transaction.uuid",
    "8-1": "String",
    "8-2": "The transaction's unique identifier in Recurly",
    "26-0": "shopper_in_session",
    "26-1": "boolean",
    "26-2": "Indicates that this is a CIT (Customer-Initiated Transaction). It is true when the transaction is created via Hosted Pages, RecurlyJS or API (this one with IPAddress informed by the merchant).",
    "27-0": "stored_billing_info",
    "27-1": "boolean",
    "27-2": "Indicates that the current transaction uses a previously stored billing info. It is true when an account code is referenced or in renewal transactions."
  },
  "cols": 3,
  "rows": 28
}
[/block]


Beyond those variables, we provide the function `hmac_sha256` for generating **HMAC hashes**. For example, this template generates a HMAC for the value of the variable `billing_info.number`, using the `config.secret` as key:
`{% hmac_sha256 config.secret : billing_info.number %}`

Additionally, liquid provides several filters for formatting the content. The complete list can be found [here](https://liquidjs.com/filters/overview.html). 

For **date formatting**, you need to just pass the format in [Ruby Time Format syntax](https://apidock.com/ruby/Time/strftime). 
Additionally, you can use the `now` special variable that is replaced by the current time.
For example:
`{"transaction_date": "{{ now | date: "%Y-%m-%dT%H:%M:%S.%L%z" }}"}`

For **number formatting**, you can use some filters that manipulate the value. For example, given the transaction amount in dollars and you need to transform it to cents, it can be done in this way:
`{"amount_in_cents": {{ transaction.amount | times: 100 | round  }} }`


## Template API: Responses




[block:tutorial-tile]
{
  "title": "Define Response Templates",
  "emoji": "🦉",
  "backgroundColor": "#018FF4",
  "slug": "define-response-templates",
  "_id": "60e4d6636bb0a60454b1cd9a",
  "id": "60e4d6636bb0a60454b1cd9a",
  "link": "https://docs.recurly.com/v1.0/recipes/define-response-templates"
}
[/block]

Response templates define how to map your gateway's response parameters to relevant parameters in Recurly.  

`POST /payment_gateway_partners/{gateway_id}/response_templates`
`GET /payment_gateway_partners/{gateway_id}/response_templates`
`PATCH /payment_gateway_partners/{gateway_id}/response_templates/{template_id}`


[block:parameters]
{
  "data": {
    "h-0": "Field",
    "h-1": "Type",
    "h-2": "Notes",
    "0-0": "action",
    "0-1": "Enum",
    "0-2": "Enum. Accepted values: purchase_response,\nverification_response,\nvoid_response,\nrefund_response",
    "1-0": "body",
    "1-1": "String",
    "1-2": "Liquid template that will be used to format the response that will be returned to Recurly Application. This template must return the fields defined in the next section."
  },
  "cols": 3,
  "rows": 2
}
[/block]




## Recury Fields: Responses




[block:parameters]
{
  "data": {
    "h-0": "Recurly Field",
    "h-1": "Format",
    "h-2": "Description",
    "0-0": "status",
    "2-0": "reference",
    "3-0": "message",
    "3-1": "String",
    "2-1": "String",
    "0-1": "Enum",
    "2-2": "This is the transaction identification by the partner. It will be passed as `original_reference` on a future refund of this same transaction.",
    "3-2": "Message to surface to merchant",
    "0-2": "Enum. Accepted values `authorized` or `declined`. \n\nThis is the status of the transaction.",
    "1-0": "decline_code",
    "1-1": "String",
    "1-2": "This is the decline error code that will be used to lookup the Recurly error in the partner error mapping when the transaction is not authorized."
  },
  "cols": 3,
  "rows": 4
}
[/block]




## Payment Methods




[block:tutorial-tile]
{
  "title": "Define Payment Methods",
  "emoji": "🦉",
  "backgroundColor": "#018FF4",
  "slug": "define-payment-methods",
  "_id": "60f9c09fa8b93900456c8051",
  "id": "60f9c09fa8b93900456c8051",
  "link": "https://docs.recurly.com/v1.0/recipes/define-payment-methods"
}
[/block]


This endpoint defines the payment methods accepted by the gateway.

`POST /payment_gateway_partners/{gateway_id}/payment_methods`
`GET /payment_gateway_partners/{gateway_id}/payment_methods`
`PATCH /payment_gateway_partners/{gateway_id}/payment_methods/{payment_method}`


[block:parameters]
{
  "data": {
    "h-0": "Field",
    "h-1": "Type",
    "h-2": "Notes",
    "0-0": "payment_method",
    "0-1": "String",
    "0-2": "Required. Accepted values: `credit_card`",
    "1-0": "currencies",
    "1-1": "Array of Strings",
    "1-2": "Required"
  },
  "cols": 3,
  "rows": 2
}
[/block]




## Error Mapping

This endpoint allows you to upload your error codes and descriptions to Recurly.

`POST /payment_gateway_partners/{configuration_id}/error_codes`
`GET /payment_gateway_partners/{configuration_id}/error_codes/{error_code_id}`
`PUT /payment_gateway_partners/{configuration_id}/error_codes/{error_code_id}`
`DELETE /payment_gateway_partners/{configuration_id}/error_codes/{error_code_id}`


[block:parameters]
{
  "data": {
    "h-0": "Field",
    "h-1": "Type",
    "h-2": "Notes",
    "0-0": "gateway_decline_code",
    "0-2": "**Required**\nYour error code",
    "1-0": "gateway_description",
    "2-0": "recurly_error_code",
    "0-1": "String",
    "1-1": "String",
    "2-1": "String",
    "1-2": "A description accompanying your error code.",
    "2-2": "The Recurly error code which maps to your error code."
  },
  "cols": 3,
  "rows": 3
}
[/block]

Additionally, you can pull a full list of uploaded error codes with the following endpoint:

`GET /payment_gateway_partners/{configuration_id}/response_templates`

To map these decline codes, you can optionally utilize the UI within the Partner Management section of your site. 

**Error Mapping UI**

To navigate to your Error Mapping UI, do the following:
  * Navigate to "Integrations -> Payment Gateway Partners
  * Click on "Options" and then "Error Mapping"

From there, you should be able to map all of your uploaded error codes to a corresponding Recurly error code. To do this, simply check each error code you're ready to map, and start typing in the Recurly error code you'd like it mapped to.
Once you're ready to map them, click "Save Changes"
  * You can also edit multiple to the same Recurly error code by selecting all of the applicable error codes and click "Bulk Edit". 
  
For a list of Recurly error codes, see the following page: 
[Recurly Transaction Error Codes](https://developers.recurly.com/pages/api-transaction-errors.html#configuration)