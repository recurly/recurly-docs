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
## Welcome to Bring Your Own Gateway, Beta Program!#\#

In the current phase of BYOG our Beta Partners will be able to define their gateway configuration, define templates and test purchase requests (Updated July 22, 2021)

## Getting a Recurly Site

Partner gateways will use a Recurly site to develop and test your BYOG integration. 

1. Sign up for a free account here: [https://app.recurly.com/signup](https://app.recurly.com/signup)

2. Work with your beta partnership contact to put site in development mode

## Authentication

Generate a Basic Authentication header with the credentials from the API Credentials page [API Credentials page](https://app.recurly.com/go/developer/api_keys).\
Also, pass the header `Accept: application/vnd.recurly.v2021-02-25`

## Configuration API

<TutorialTile title="Configuration" id="60c938250a6d9b0069c20436" slug="configuration" backgroundColor="#018FF4" emoji="🦉" link="https://docs.recurly.com/v1.0/recipes/configuration" />

## **Configuration Request**

This is where you will define what fields your merchants should configure when adding your payment gateway to Recurly. Additionally, this will instruct how your gateway operates, and any specific parameters that would need to be configured, such as `single_currency_per_account`.\
The fields defined here will appear in the Recurly UI under Gateway Configuration

`POST https://app.recurly.com/payment_gateway_partners/`

<Table align={["left","left","left"]}>
  <thead>
    <tr>
      <th style={{ textAlign: "left" }}>
        Field
      </th>

      <th style={{ textAlign: "left" }}>
        Type
      </th>

      <th style={{ textAlign: "left" }}>
        Notes
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td style={{ textAlign: "left" }}>
        single\_currency\_per\_account
      </td>

      <td style={{ textAlign: "left" }}>
        Boolean
      </td>

      <td style={{ textAlign: "left" }}>
        Defines if merchant account can have multiple currencies. Defaults to False
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        name
      </td>

      <td style={{ textAlign: "left" }}>
        String
      </td>

      <td style={{ textAlign: "left" }}>
        Your gateway's name
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        logo
      </td>

      <td style={{ textAlign: "left" }}>
        String
      </td>

      <td style={{ textAlign: "left" }}>
        Fully qualified URL path to a hosted image for your gateway's logo
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        merchant\_countries
      </td>

      <td style={{ textAlign: "left" }}>
        Array
      </td>

      <td style={{ textAlign: "left" }}>
        Required. Comma delimited list of acceptable merchant countries. Must be ISO code.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        zero\_dollar\_auth
      </td>

      <td style={{ textAlign: "left" }}>
        Boolean
      </td>

      <td style={{ textAlign: "left" }}>
        Required. Does the gateway accept 0 dollar authorizations? If False, verifications will default to 1.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        zero\_dollar\_auth\_without\_address
      </td>

      <td style={{ textAlign: "left" }}>
        Boolean
      </td>

      <td style={{ textAlign: "left" }}>
        Required. Does the gateway allow 0 dollar authorization without a billing address present?
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        fields
      </td>

      <td style={{ textAlign: "left" }}>
        Object
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        For each field, define:
      </td>

      <td style={{ textAlign: "left" }}>

      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        secret
      </td>

      <td style={{ textAlign: "left" }}>
        Boolean
      </td>

      <td style={{ textAlign: "left" }}>
        Sets value as a secret, please use True for your password/API Key field
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        required
      </td>

      <td style={{ textAlign: "left" }}>
        Boolean
      </td>

      <td style={{ textAlign: "left" }}>
        Is field required for your gateway configuration
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        order
      </td>

      <td style={{ textAlign: "left" }}>
        Number
      </td>

      <td style={{ textAlign: "left" }}>
        Order of field when displayed in Recurly's gateway configuration UI
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        label
      </td>

      <td style={{ textAlign: "left" }}>
        String
      </td>

      <td style={{ textAlign: "left" }}>
        Field name merchant should see when configuring payment gateway in Recurly
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        field\_name\_in\_template
      </td>

      <td style={{ textAlign: "left" }}>
        String
      </td>

      <td style={{ textAlign: "left" }}>
        field name you'll use when including this field in a template (can be same as label)
      </td>
    </tr>
  </tbody>
</Table>

## **Configuration Response**

In addition to a reflection of the applied fields above, you will also receive an `id` field which will need to be used in later API calls as the "gateway\_id" in the route.

<Table align={["left","left","left"]}>
  <thead>
    <tr>
      <th style={{ textAlign: "left" }}>
        Field
      </th>

      <th style={{ textAlign: "left" }}>
        Type
      </th>

      <th style={{ textAlign: "left" }}>
        Notes
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td style={{ textAlign: "left" }}>
        id
      </td>

      <td style={{ textAlign: "left" }}>
        String
      </td>

      <td style={{ textAlign: "left" }}>
        Recurly-generated UUID that will be used to select this configuration in future API calls
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        name
      </td>

      <td style={{ textAlign: "left" }}>
        String
      </td>

      <td style={{ textAlign: "left" }}>
        Your gateway's name
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        logo
      </td>

      <td style={{ textAlign: "left" }}>
        String
      </td>

      <td style={{ textAlign: "left" }}>
        Fully qualified URL path to a hosted image for your gateway's logo
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        single\_currency\_per\_account
      </td>

      <td style={{ textAlign: "left" }}>
        Boolean
      </td>

      <td style={{ textAlign: "left" }}>
        Defines if merchant account can have multiple currencies. Defaults to False
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        zero\_dollar\_auth
      </td>

      <td style={{ textAlign: "left" }}>
        Boolean
      </td>

      <td style={{ textAlign: "left" }}>
        Indicates if the gateway accept 0 dollar authorizations? If False, verifications will default to 1.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        zero\_dollar\_auth\_without\_address
      </td>

      <td style={{ textAlign: "left" }}>
        Boolean
      </td>

      <td style={{ textAlign: "left" }}>
        Indicates if the gateway allow 0 dollar authorization without a billing address present?
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        merchant\_countries
      </td>

      <td style={{ textAlign: "left" }}>
        Array
      </td>

      <td style={{ textAlign: "left" }}>
        Array of merchant country codes
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        fields
      </td>

      <td style={{ textAlign: "left" }}>
        Object
      </td>

      <td style={{ textAlign: "left" }}>
        Reflection of created fields in the template
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        created\_at
      </td>

      <td style={{ textAlign: "left" }}>
        String
      </td>

      <td style={{ textAlign: "left" }}>
        date-time formatted string of when the template was created
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        updated\_at
      </td>

      <td style={{ textAlign: "left" }}>
        String
      </td>

      <td style={{ textAlign: "left" }}>
        date-time formatted string of when the template was last updated
      </td>
    </tr>
  </tbody>
</Table>

## Template API: Requests

<TutorialTile title="Define Request Templates" emoji="🦉" backgroundColor="#018FF4" slug="define-request-templates" id="60e4cfe451cb9900497aa104" link="https://docs.recurly.com/v1.0/recipes/define-request-templates" />

The Template API defines how to map Recurly fields to partner gateway fields. Templates will be triggered based on actions from merchants. For example, a template with the action: purchase will be applied each time an applicable purchase

`POST /payment_gateway_partners/{gateway_id}/request_templates`\
`GET /payment_gateway_partners/{gateway_id}/request_templates`\
`PATCH /payment_gateway_partners/{gateway_id}/request_templates/{template_id}`

<Table align={["left","left","left"]}>
  <thead>
    <tr>
      <th style={{ textAlign: "left" }}>
        Field
      </th>

      <th style={{ textAlign: "left" }}>
        Type
      </th>

      <th style={{ textAlign: "left" }}>
        Notes
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td style={{ textAlign: "left" }}>
        url
      </td>

      <td style={{ textAlign: "left" }}>
        String
      </td>

      <td style={{ textAlign: "left" }}>
        Required. The liquid template for the URL that will be used to perform the requests to your gateway when the merchant's site is in productction mode.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        test\_url
      </td>

      <td style={{ textAlign: "left" }}>
        String
      </td>

      <td style={{ textAlign: "left" }}>
        Required. The liquid template for the URL that will be used to perform the requests to your gateway when the merchant's site is in development or sandbox mode.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        payment\_action
      </td>

      <td style={{ textAlign: "left" }}>
        String
      </td>

      <td style={{ textAlign: "left" }}>
        Required. Supported values: verification, purchase, refund, renewal, void
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        template\_name
      </td>

      <td style={{ textAlign: "left" }}>
        String
      </td>

      <td style={{ textAlign: "left" }}>
        Optional: if not provided, name we default to the template ID
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        body
      </td>

      <td style={{ textAlign: "left" }}>
        String
      </td>

      <td style={{ textAlign: "left" }}>
        Required. String that defines your liquid template for the action.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        headers
      </td>

      <td style={{ textAlign: "left" }}>
        Object
      </td>

      <td style={{ textAlign: "left" }}>
        Optional. Use it to add custom headers, if needed. Provide them in the form\
        \{"Header1": "HeaderValueLiquidTemplate1", "Header2": "HeaderValueLiquidTemplate2"}
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        content\_type
      </td>

      <td style={{ textAlign: "left" }}>
        String
      </td>

      <td style={{ textAlign: "left" }}>
        Optional. The liquid template for the Content-Type header that will be used in the request.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        accept
      </td>

      <td style={{ textAlign: "left" }}>
        String
      </td>

      <td style={{ textAlign: "left" }}>
        Optional. The liquid template for  the Accept header that will be used in the request.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        authorization
      </td>

      <td style={{ textAlign: "left" }}>
        String
      </td>

      <td style={{ textAlign: "left" }}>
        Optional. The liquid template for the Authorization header that will be used in the request.
      </td>
    </tr>
  </tbody>
</Table>

## Recurly Fields: Requests

Our templating leverages [Liquid templating language](https://liquidjs.com/tutorials/intro-to-liquid.html). For each field defined in your template you'll follow the format `{"your_gateway_parameter" : "{{ recurly.field }}"`

Below are the Recurly fields available for inclusion in your template

<Table align={["left","left","left"]}>
  <thead>
    <tr>
      <th style={{ textAlign: "left" }}>
        Recurly Field
      </th>

      <th style={{ textAlign: "left" }}>
        Format
      </th>

      <th style={{ textAlign: "left" }}>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td style={{ textAlign: "left" }}>
        transaction.amount
      </td>

      <td style={{ textAlign: "left" }}>
        minor units. Formatted String
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        transaction.currency
      </td>

      <td style={{ textAlign: "left" }}>
        String. 3 letters
      </td>

      <td style={{ textAlign: "left" }}>
        ISO Code. Currency of transaction.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        transaction.country
      </td>

      <td style={{ textAlign: "left" }}>
        String. 2 letters
      </td>

      <td style={{ textAlign: "left" }}>
        ISO Code. 

        Recurly V2: determined by the billing address of shopper or issuing country of billing info on file. 

        Recurly V3: Submitted by merchant, or determined by shopper IP if no value submitted.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        transaction.description
      </td>

      <td style={{ textAlign: "left" }}>
        String. Max length 50.
      </td>

      <td style={{ textAlign: "left" }}>
        Submitted by merchant.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        transaction.invoice\_number
      </td>

      <td style={{ textAlign: "left" }}>
        Number
      </td>

      <td style={{ textAlign: "left" }}>
        Invoice number, generated by Recurly upon invoice generation.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        transaction.original\_reference
      </td>

      <td style={{ textAlign: "left" }}>
        String
      </td>

      <td style={{ textAlign: "left" }}>
        Partner identification of the original transaction that is being refunded.\
        It is provided only in refunds.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        transaction.shopper\_in\_session
      </td>

      <td style={{ textAlign: "left" }}>
        Boolean
      </td>

      <td style={{ textAlign: "left" }}>
        Indicates that this is a CIT (Customer-Initiated Transaction).\
        It is true when the transaction is created via Hosted Pages, RecurlyJS or API (this one with IPAddress informed by the merchant).
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        transaction.stored\_billing\_info
      </td>

      <td style={{ textAlign: "left" }}>
        Boolean
      </td>

      <td style={{ textAlign: "left" }}>
        Indicates that the current transaction uses a previously stored billing info. It is true when an account code is referenced or in renewal transactions.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        transaction.uuid
      </td>

      <td style={{ textAlign: "left" }}>
        String
      </td>

      <td style={{ textAlign: "left" }}>
        The transaction's unique identifier in Recurly
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        billing\_info.number
      </td>

      <td style={{ textAlign: "left" }}>
        Number, 16 digits
      </td>

      <td style={{ textAlign: "left" }}>
        Credit Card PAN
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        billing\_info.first\_name
      </td>

      <td style={{ textAlign: "left" }}>
        String
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        billing\_info.last\_name
      </td>

      <td style={{ textAlign: "left" }}>
        String
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        billing\_info.year
      </td>

      <td style={{ textAlign: "left" }}>
        String. 4 characters.
      </td>

      <td style={{ textAlign: "left" }}>
        Expiration Year
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        billing\_info.month
      </td>

      <td style={{ textAlign: "left" }}>
        String. 2 characters
      </td>

      <td style={{ textAlign: "left" }}>
        Expiration Month
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        billing\_info.cvv
      </td>

      <td style={{ textAlign: "left" }}>
        String
      </td>

      <td style={{ textAlign: "left" }}>
        CVV of card
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        billing\_info.address.address1
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        billing\_info.address.address2
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        billing\_info.address.city
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        billing\_info.address.state
      </td>

      <td style={{ textAlign: "left" }}>
        string. 2 letters
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        billing\_info.address.zip
      </td>

      <td style={{ textAlign: "left" }}>

      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        billing\_info.phone
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        billing\_info.ip\_address
      </td>

      <td style={{ textAlign: "left" }}>
        string. 20 characters.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        billing\_info.tax\_identifier
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>

      <td style={{ textAlign: "left" }}>
        tax id for the shopper. CPF for Brazil, CUIT for Argentina
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        billing\_info.tax\_identifier\_type
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>

      <td style={{ textAlign: "left" }}>
        type of tax identifier passed. CPF for Brazil, CUIT for Argentina
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        config
      </td>

      <td style={{ textAlign: "left" }}>
        object
      </td>

      <td style={{ textAlign: "left" }}>
        This will contain all the configuration field values defined by the merchant in the gateway configuration page.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        live
      </td>

      <td style={{ textAlign: "left" }}>
        boolean
      </td>

      <td style={{ textAlign: "left" }}>
        This variable indicates if the merchant site is configured for production/live mode or not.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        shopper\_in\_session
      </td>

      <td style={{ textAlign: "left" }}>
        boolean
      </td>

      <td style={{ textAlign: "left" }}>
        Indicates that this is a CIT (Customer-Initiated Transaction). It is true when the transaction is created via Hosted Pages, RecurlyJS or API (this one with IPAddress informed by the merchant).
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        stored\_billing\_info
      </td>

      <td style={{ textAlign: "left" }}>
        boolean
      </td>

      <td style={{ textAlign: "left" }}>
        Indicates that the current transaction uses a previously stored billing info. It is true when an account code is referenced or in renewal transactions.
      </td>
    </tr>
  </tbody>
</Table>

Beyond those variables, we provide the function `hmac_sha256` for generating **HMAC hashes**. For example, this template generates a HMAC for the value of the variable `billing_info.number`, using the `config.secret` as key:\
`{% hmac_sha256 config.secret : billing_info.number %}`

Additionally, liquid provides several filters for formatting the content. The complete list can be found [here](https://liquidjs.com/filters/overview.html). 

For **date formatting**, you need to just pass the format in [Ruby Time Format syntax](https://apidock.com/ruby/Time/strftime).\
Additionally, you can use the `now` special variable that is replaced by the current time.\
For example:\
`{"transaction_date": "{{ now | date: "%Y-%m-%dT%H:%M:%S.%L%z" }}"}`

For **number formatting**, you can use some filters that manipulate the value. For example, given the transaction amount in dollars and you need to transform it to cents, it can be done in this way:\
`{"amount_in_cents": {{ transaction.amount | times: 100 | round  }} }`

## Template API: Responses

<TutorialTile title="Define Response Templates" emoji="🦉" backgroundColor="#018FF4" slug="define-response-templates" id="60e4d6636bb0a60454b1cd9a" link="https://docs.recurly.com/v1.0/recipes/define-response-templates" />

Response templates define how to map your gateway's response parameters to relevant parameters in Recurly.  

`POST /payment_gateway_partners/{gateway_id}/response_templates`\
`GET /payment_gateway_partners/{gateway_id}/response_templates`\
`PATCH /payment_gateway_partners/{gateway_id}/response_templates/{template_id}`

<Table align={["left","left","left"]}>
  <thead>
    <tr>
      <th style={{ textAlign: "left" }}>
        Field
      </th>

      <th style={{ textAlign: "left" }}>
        Type
      </th>

      <th style={{ textAlign: "left" }}>
        Notes
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td style={{ textAlign: "left" }}>
        action
      </td>

      <td style={{ textAlign: "left" }}>
        Enum
      </td>

      <td style={{ textAlign: "left" }}>
        Enum. Accepted values: purchase\_response,\
        verification\_response,\
        void\_response,\
        refund\_response
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        body
      </td>

      <td style={{ textAlign: "left" }}>
        String
      </td>

      <td style={{ textAlign: "left" }}>
        Liquid template that will be used to format the response that will be returned to Recurly Application. This template must return the fields defined in the next section.
      </td>
    </tr>
  </tbody>
</Table>

## Recury Fields: Responses

<Table align={["left","left","left"]}>
  <thead>
    <tr>
      <th style={{ textAlign: "left" }}>
        Recurly Field
      </th>

      <th style={{ textAlign: "left" }}>
        Format
      </th>

      <th style={{ textAlign: "left" }}>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td style={{ textAlign: "left" }}>
        status
      </td>

      <td style={{ textAlign: "left" }}>
        Enum
      </td>

      <td style={{ textAlign: "left" }}>
        Enum. Accepted values `authorized` or `declined`. 

        This is the status of the transaction.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        decline\_code
      </td>

      <td style={{ textAlign: "left" }}>
        String
      </td>

      <td style={{ textAlign: "left" }}>
        This is the decline error code that will be used to lookup the Recurly error in the partner error mapping when the transaction is not authorized.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        reference
      </td>

      <td style={{ textAlign: "left" }}>
        String
      </td>

      <td style={{ textAlign: "left" }}>
        This is the transaction identification by the partner. It will be passed as `original_reference` on a future refund of this same transaction.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        message
      </td>

      <td style={{ textAlign: "left" }}>
        String
      </td>

      <td style={{ textAlign: "left" }}>
        Message to surface to merchant
      </td>
    </tr>
  </tbody>
</Table>

## Payment Methods

<TutorialTile title="Define Payment Methods" emoji="🦉" backgroundColor="#018FF4" slug="define-payment-methods" id="60f9c09fa8b93900456c8051" link="https://docs.recurly.com/v1.0/recipes/define-payment-methods" />

This endpoint defines the payment methods accepted by the gateway.

`POST /payment_gateway_partners/{gateway_id}/payment_methods`\
`GET /payment_gateway_partners/{gateway_id}/payment_methods`\
`PATCH /payment_gateway_partners/{gateway_id}/payment_methods/{payment_method}`

<Table align={["left","left","left"]}>
  <thead>
    <tr>
      <th style={{ textAlign: "left" }}>
        Field
      </th>

      <th style={{ textAlign: "left" }}>
        Type
      </th>

      <th style={{ textAlign: "left" }}>
        Notes
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td style={{ textAlign: "left" }}>
        payment\_method
      </td>

      <td style={{ textAlign: "left" }}>
        String
      </td>

      <td style={{ textAlign: "left" }}>
        Required. Accepted values: `credit_card`
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        currencies
      </td>

      <td style={{ textAlign: "left" }}>
        Array of Strings
      </td>

      <td style={{ textAlign: "left" }}>
        Required
      </td>
    </tr>
  </tbody>
</Table>

## Error Mapping

This endpoint allows you to upload your error codes and descriptions to Recurly.

`POST /payment_gateway_partners/{configuration_id}/error_codes`\
`GET /payment_gateway_partners/{configuration_id}/error_codes/{error_code_id}`\
`PUT /payment_gateway_partners/{configuration_id}/error_codes/{error_code_id}`\
`DELETE /payment_gateway_partners/{configuration_id}/error_codes/{error_code_id}`

<Table align={["left","left","left"]}>
  <thead>
    <tr>
      <th style={{ textAlign: "left" }}>
        Field
      </th>

      <th style={{ textAlign: "left" }}>
        Type
      </th>

      <th style={{ textAlign: "left" }}>
        Notes
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td style={{ textAlign: "left" }}>
        gateway\_decline\_code
      </td>

      <td style={{ textAlign: "left" }}>
        String
      </td>

      <td style={{ textAlign: "left" }}>
        **Required**\
        Your error code
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        gateway\_description
      </td>

      <td style={{ textAlign: "left" }}>
        String
      </td>

      <td style={{ textAlign: "left" }}>
        A description accompanying your error code.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        recurly\_error\_code
      </td>

      <td style={{ textAlign: "left" }}>
        String
      </td>

      <td style={{ textAlign: "left" }}>
        The Recurly error code which maps to your error code.
      </td>
    </tr>
  </tbody>
</Table>

Additionally, you can pull a full list of uploaded error codes with the following endpoint:

`GET /payment_gateway_partners/{configuration_id}/response_templates`

To map these decline codes, you can optionally utilize the UI within the Partner Management section of your site. 

**Error Mapping UI**

To navigate to your Error Mapping UI, do the following:

* Navigate to "Integrations -> Payment Gateway Partners
* Click on "Options" and then "Error Mapping"

From there, you should be able to map all of your uploaded error codes to a corresponding Recurly error code. To do this, simply check each error code you're ready to map, and start typing in the Recurly error code you'd like it mapped to.\
Once you're ready to map them, click "Save Changes"

* You can also edit multiple to the same Recurly error code by selecting all of the applicable error codes and click "Bulk Edit". 

For a list of Recurly error codes, see the following page:\
[Recurly Transaction Error Codes](https://developers.recurly.com/pages/api-transaction-errors.html#configuration)
