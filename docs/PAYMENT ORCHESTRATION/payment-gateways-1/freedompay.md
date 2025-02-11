---
title: FreedomPay
excerpt: >-
  FreedomPay Gateway: A secure and innovative payment platform enabling seamless
  transactions, advanced data analytics, and enhanced customer experiences for
  retail, e-commerce, and SaaS businesses.
deprecated: false
hidden: true
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

### Prerequisites

To use a Point of Sale system with FreedomPay and provide POS-derived NTIDs via API, your Recurly account must have the following prerequisites:

- **Feature flag**: Allow NTIDs to be sent via API.
  - Reach out to support to have this enabled.

### Limitations

FreedomPay currencies are managed by credentials. You will need multiple FreedomPay gateway instances to support multiple currencies.

# Definition

FreedomPay is a full-service payment platform. When configured with Recurly, it allows you to securely manage your transactions. You will need a FreedomPay Store ID, Terminal ID, and Enhanced Security Key to enable this integration.

Recurly supports Ecommerce and Recurring transactions with FreedomPay. If you are using a Card Present Point of Sale system with FreedomPay and want to offer subscriptions, reach out to Support for guidance.

# Key details

[block:parameters]
{
  "data": {
    "h-0": "Features",
    "h-1": "Availability",
    "0-0": "Services that work with Recurly",
    "0-1": "Payment Processing",
    "1-0": "Supported integrations",
    "1-1": "Recurly.js, API, Checkout, HPP",
    "2-0": "Supported operations",
    "2-1": "Verify, Purchase, Void, and Refund",
    "3-0": "Supported payment types",
    "3-1": "Credit and Debit Cards, Gateway tokens",
    "4-0": "Supported card brands",
    "4-1": "Visa, MasterCard, Discover, Amex, JCB, Diners, UnionPay",
    "5-0": "Gateway Specific 3DS2 Supported",
    "5-1": "N/A",
    "6-0": "Supported capabilities",
    "6-1": "Card-on-file, Gateway Tokens, ZDA",
    "7-0": "Regions",
    "7-1": "United States",
    "8-0": "Currencies",
    "8-1": "FreedomPay supports all ISO-standard currencies. See <a href=\"https://docs.recurly.com/docs/currency-support-by-gateway\" target=\"_blank\">all available.</a>"
  },
  "cols": 2,
  "rows": 9,
  "align": [
    null,
    null
  ]
}
[/block]


# Configuring FreedomPay gateway in Recurly

Follow the steps below to configure FreedomPay in Recurly. Make sure you use the correct site mode and FreedomPay credentials for a seamless setup. 

> **Please note:** While the URLs are listed below, there is no configuration or specific integration necessary other than Recurly site mode to access these endpoints.

- **Development mode**: Connects to the FreedomPay UAT environment: <https://cs.uat.freedompay.com/Freeway/Service.asmx> 
- **Production mode**: Connects to the FreedomPay production environment: <https://cs12.freedompay.us/Freeway/Service.asmx>  
- **Sandbox mode**: Does not use either environment,, and will hit the internal Recurly Test Gateway. 

### Step 1: Obtain your FreedomPay Store ID and Terminal ID

Log into your FreedomPay Gateway account. If you do not have an account, sign up with FreedomPay first.

### Step 2: Generate your Enhanced Security (ES) Key

1. Navigate to **Administration** → **Enhanced Security Keys**.
2. Click **Create new** under the **All enhanced security keys** section.
3. Enter a description for the key (e.g., _Recurly Configuration Key_).
4. Ensure **Freeway Payments** is checked.
5. **Do not click "Create" yet.** Instead, click the **Freeway Payments** tab and verify the correct Tiers and Stores are associated with the key.
6. Click **Create** at the bottom of the page.
7. Copy the key using the copy icon. You can click to view the masked key, but it's not necessary for configuration.

### Step 3: Enter your FreedomPay credentials in Recurly

1. Log into your Recurly account and navigate to the **Payment Gateways** page.
2. Click **Add a New Gateway**.
3. Select **FreedomPay** from the list of gateways.
4. Enter your **Store ID** and **Terminal ID**.
5. Enter the **Enhanced Security Key (ES Key)** generated in Step 2.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/970cffc46d1a2ea0027cb5a9b88bb9248c4593a8e17a8a511e47207af6db29b6-Credentials_-_FreedomPay.png",
        "",
        ""
      ],
      "align": "center",
      "border": true
    }
  ]
}
[/block]


### Step 4: Configure your gateway settings

1. Under **Accepted Credit Card Types**, select which card types you want to accept. This should match what you have set up in your FreedomPay account.
2. Under **Accepted Currencies**, select the currencies you want to accept.
3. Select the type of goods you plan to sell—Digital, Physical, or a combination of both.
4. Click **Add Payment Gateway** once all sections are complete.

![](https://files.readme.io/08079a1b763dd45fb7bbc6b9bc323ce3d8b653b7b9f198abcdd0c69ef0add7f0-Goods_Selection_-_FreedomPay.png)

### Step 5: Configure your AVS and CVV rules

FreedomPay supports verifying AVS (Address Verification) and CVV codes for customer-initiated transactions. To enable this feature for your Recurly site, go to **Configuration** › **Payment Settings** and enable the following:

- **Credit Card Verification Check**
- **Address Verification Check**

When enabled, mismatches in AVS or CVV will cause customer-initiated transactions to be automatically declined, reducing the risk of fraud.

**Customer-initiated transactions include:**

- Signing up for a subscription
- Making a one-time purchase
- Updating billing information

Recurring and other merchant-initiated transactions are not affected by these rules.

> **For more information, see the [Payments Settings documentation](https://docs.recurly.com/docs/payment-settings).**

Further reading on Recurly functionality can be found elsewhere on this site. Please use the left-menu to discover and troubleshoot other features of our platform

- [Developer Hub: Error Messages](https://recurly.com/developers/pages/api-transaction-errors.html)
- Invoice Management: 
  - [View Invoices: Invoice dashboard](https://docs.recurly.com/docs/invoices#view-invoices) 
  - [Refunds: Refund / Credit invoices](https://docs.recurly.com/docs/credit-invoices)
  - [Voids: Voiding invoices](https://docs.recurly.com/docs/credit-invoices#voiding-credit-invoices-or-balances)
  - [Auth and Capture: Authorization and capture](https://docs.recurly.com/docs/auth-and-capture) 

### Escalating to FreedomPay or Recurly Tech Support

If you need to reach out to FreedomPay directly, ensure you have all appropriate details available to provide when escalating for troubleshooting.

**Details to Collect and Provide**

- Store ID, Terminal ID, Error Code, Request ID

**Contact Details**

- Test Environment help desk (FreedomPay): <https://freedompay.atlassian.net/servicedesk>

- Production **FreedomPay** contacts:
  - Email: [techsupport@freedompay.com](mailto:techsupport@freedompay.com)
  - Phone: 888-495-2446 (US) / +44-2030148966 (UK)
  - Status Page: <https://status.freedompay.com>

**How to Find Details**

**Gateway Store and Terminal IDs** can be found in your Payment Gateway configuration details under **Configuration** › **Payment Gateways** and select the appropriate gateway instance.

**Gateway error codes** will be available at the top of a given transaction that was declined or produced an error. In the example below, the code in question is “431”.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/92f850e81aa3275cd791b2ecb986d23418f6a37e7d3b6cf641f3706edd2ba14d-Screenshot_2024-12-12_at_11.44.34_AM.png",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


The **Reference** below will map to the FreedomPay **Request ID**.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9d127b4c8086b0dc6deb14cab328a7f14dee6e7d03946dbde4f7df80cea13252-Screenshot_2024-12-12_at_11.44.43_AM.png",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


### Payload examples and error documentation

> **FreedomPay Error Code Documentation: [Error Code Guide](https://freedompay.atlassian.net/wiki/spaces/IP/pages/878673921/FreedomPay+Error+Guide?preview=/878673921/3989143571/FreedomPay_Error_Codes_Guide-v6.8.pdf)**

Per FreedomPay request, we are providing examples of a proper request and response to a standard payment.

If you cannot access this PDF, please reach out to FreedomPay directly. Recurly support does not have authority to grant access.

**Request Example **

```Text xml
<SOAP-ENV:Body>  
    <Submit>  
      <request>  
        <storeId>**\*\*\*\***</storeId>  
        <terminalId>**\*\*\*\***</terminalId>  
        <esKey>**\*\*\*\***</esKey>  
        <merchantReferenceCode>{{Recurly-UUID}}</merchantReferenceCode>  
        <brand>VS</brand>  
        \<ccAuthService run=""true"">  
          <transType>purchase</transType>  
          <allowPartial>N</allowPartial>  
          <returnBalance>Y</returnBalance>  
          <cofIndicator>U</cofIndicator>  
          <cofComplianceData>{{NTID}}</cofComplianceData>  
          <enableAVS>Y</enableAVS>  
          <commerceIndicator>internet</commerceIndicator>  
          <recurring>Y</recurring>  
        </ccAuthService>  
        \<ccCaptureService run=""true"">  
          <isSplitTransaction>N</isSplitTransaction>  
        </ccCaptureService>  
        <billTo>  
          <customerID>{{Recurly-Account-Code}}</customerID>  
          <firstName>Jane</firstName>  
          <lastName>Doe</lastName>  
          <street1>123 Main</street1>  
          <city>Chicago</city>  
          <state>IL</state>  
          <postalCode>12345</postalCode>  
          <country>US</country>  
        </billTo>  
        <card>  
          <accountNumber>{{gateway-token}}</accountNumber>  
          <cardType>token</cardType>  
          <cvNumber>{{masked-cvv}}</cvNumber>  
          <nameOnCard>Jane Doe</nameOnCard>  
        </card>  
        <invoiceHeader>  
          <goodsIndicator>physical</goodsIndicator>  
          <invoiceNumber>1000</invoiceNumber>  
          <purchaserCode>12345</purchaserCode>  
        </invoiceHeader>  
        <clientMetadata>  
          <sellingSystemName>merchantdomain.com</sellingSystemName>  
          <sellingSystemVersion>1.0</sellingSystemVersion>  
          <sellingMiddlewareName>Recurly</sellingMiddlewareName>  
          <sellingMiddlewareVersion>1.0</sellingMiddlewareVersion>  
        </clientMetadata>  
        <pos>  
          <entryMode>keyed</entryMode>  
          <cardPresent>N</cardPresent>  
          <paymentDate>2024-12-31T17:22:18Z</paymentDate>  
          <caps>K</caps>  
        </pos>  
        <purchaseTotals>  
          <currency>USD</currency>  
          <chargeAmount>10.00</chargeAmount>  
          <taxTotal>0</taxTotal>  
        </purchaseTotals>  
        <items>  
          <item>  
            <id>0</id>  
            <productName>Product Name</productName>  
            <productDescription>Description of the Product</productDescription>  
            <unitPrice>10.00</unitPrice>  
            <quantity>1</quantity>  
            <totalAmount>10.00</totalAmount>  
            <unitOfMeasure>EA</unitOfMeasure>  
            <saleCode>S</saleCode>  
            <taxAmount>0</taxAmount>  
            <taxIncludedFlag>N</taxIncludedFlag>  
          </item>  
        </items>  
      </request>  
    </Submit>  
  </SOAP-ENV:Body>  
</SOAP-ENV:Envelope>
```

```
\<soap:Envelope xmlns:soap=""<http://schemas.xmlsoap.org/soap/envelope/""> xmlns:xsi=""<http://www.w3.org/2001/XMLSchema-instance""> xmlns:xsd=""<http://www.w3.org/2001/XMLSchema"">>  
  \<soap:Body>  
    \<SubmitResponse xmlns=""<http://freeway.freedompay.com/"">>  
      <SubmitResult>  
        <merchantReferenceCode>{{Recurly-UUID}}</merchantReferenceCode>  
        <ccAuthReply>  
          <amount>10.00</amount>  
          <processorTransactionID>1234567890</processorTransactionID>  
          <enhancedDataEnabled>N</enhancedDataEnabled>  
          <avsCodeRaw>N</avsCodeRaw>  
          <processorResponseCode>100</processorResponseCode>  
          <reasonCode>100</reasonCode>  
          <authorizationCode>123456</authorizationCode>  
          <avsCode>N</avsCode>  
          <partialAmount>N</partialAmount>  
          <cvCode>M</cvCode>  
          <authorizedDateTime>2024-12-01T17:22:18.8622020Z</authorizedDateTime>  
          <processorResponseMessage>APPROVED</processorResponseMessage>  
          <requestDateTime>2024-12-01T17:22:18.7641802Z</requestDateTime>  
          <cvCodeRaw>M</cvCodeRaw>  
          <reconciliationID>252306047</reconciliationID>  
        </ccAuthReply>  
        <requestID>01Z6MGHC2A97U6G5L9DH6JCG10BDCLTD</requestID>  
        <networkData>  
          <network>FREEWAY</network>  
        </networkData>  
        <tokenInformation>  
          <brand>VS</brand>  
          <accountNumberMasked>411111xxxxxx1111</accountNumberMasked>  
          <cardExpirationYear>29</cardExpirationYear>  
          <cardExpirationMonth>12</cardExpirationMonth>  
          <cardType>credit</cardType>  
        </tokenInformation>  
        <decision>ACCEPT</decision>  
        <reasonCode>100</reasonCode>  
        <ccCaptureReply>  
          <processorTransactionID>252306047</processorTransactionID>  
          <amount>55.15</amount>  
          <requestDateTime>2024-12-10T17:22:18.7641802Z</requestDateTime>  
          <processorResponseCode>100</processorResponseCode>  
          <purchasingLevel3Enabled>N</purchasingLevel3Enabled>  
          <enhancedDataEnabled>N</enhancedDataEnabled>  
          <reasonCode>100</reasonCode>  
          <reconciliationID>1234567890</reconciliationID>  
          <partialAmount>N</partialAmount>  
          <processorResponseMessage>APPROVED</processorResponseMessage>  
        </ccCaptureReply>  
      </SubmitResult>  
    </SubmitResponse>  
   </soap:Body>  
 </soap:Envelope>
```

### Security Suggestions

Per FreedomPay request, we are providing their security suggestions. Not all of these will apply to Recurly systems, or your own. If there are any questions on this document, reach out to FreedomPay directly.

> **Please, read: [Ecommerce Integration Requirements for Security](https://drive.google.com/file/d/1yN6GzwmdbxkKL6dtrQDa0vGVcIa4AAMC/view?usp=drive_link).**

# FAQs

### How do I contact Recurly Support?

Please reference this page: <https://docs.recurly.com/docs/do-you-need-help> 

### What if my customer does not provide an address or CVV on the initial transaction and AVS Rejection is enabled?

FreedomPay will still generate AVS and CVV response codes in such cases, which will likely result in a rejection due to the absence of address and CVV information. It's important to capture billing information and CVV codes for all customer-initiated transactions to prevent an increase in declines when these features are enabled.

### I am getting authentication failure or gateway configuration messages when I try to make a purchase. How can I fix this?

Check the following:

- Ensure your ES (Enhanced Security) Key has the correct mappings to your Terminal and Store IDs in the FreedomPay gateway. This action must be taken in your FreedomPay gateway account, not within Recurly.
- Verify which Tiers the ES Key is mapped to in your Enterprise FreedomPay login. If you have set up special mappings, check the **Enterprise Management** tab in FreedomPay to ensure it has the correct access.
- Ensure you are not using a UAT Store ID, Terminal ID, or ES Key in Production Mode (and vice versa).
- Verify that the correct card types are selected in Recurly. If a card brand is selected in Recurly but not enabled at FreedomPay, contact your FreedomPay representative to add this card type or remove it from your Recurly gateway configuration.  
  If you continue to experience issues, please reach out directly to FreedomPay support.

### I am using a Point of Sale card terminal. How can I connect this to Recurly?

Recurly does not directly support EMV or Card Present transactions. To set up a Card Present → Recurring Subscription flow, first integrate and build out your card present solution with FreedomPay. Your card present integration should result in a gateway token and your subscription Network Transaction ID (NTID).  
Once that is complete, follow this [guide](tokens-guide) to create subscriptions in Recurly and provide the external NTID correctly. Learn more about [Card on File](https://docs.recurly.com/docs/card-on-file) in our compliance documentation.

### How does information get from my customer to FreedomPay?

In general, all data gets to our gateway partners in the same way. Data flows from one of our supported front-end solutions, such as our API, Recurly.js, or a Hosted page, into Recurly and through to a gateway partner through their API connection.

There are two types of transactions Recurly supports: CIT (Customer Initiated) and MIT (Merchant Initiated).  Learn more about [Card on File](https://docs.recurly.com/docs/card-on-file) in our compliance documentation.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/23b1a5df529958cb91e9302a1af5673b7c5a426628e395b3702fea8316322395-Screenshot_2024-12-12_at_11.49.56_AM.png",
        null,
        ""
      ],
      "align": "center",
      "border": true
    }
  ]
}
[/block]


For Merchant Initiated Transactions, the customer is no longer in session, but their bank is still approving or declining these transactions.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f101629887765a924175984e6e7c1d7407b72e5d0ef2cdbbc4cd41e3d7b72306-Screenshot_2024-12-12_at_11.49.49_AM.png",
        null,
        ""
      ],
      "align": "center",
      "border": true
    }
  ]
}
[/block]


Recurly does not approve or decline transactions. If you would like more information on a decline, we suggest having the customer reach out directly to their bank. 

# Additional resources

For additional Recurly troubleshooting and how-tos, please search this documentation site, as this FAQ is specific to FreedomPay: [Recurly Documentation](https://docs.recurly.com/) 

Here are some helpful starter pages:

- [Recurly's overview](https://docs.recurly.com/docs/getting-started)
- [Overview: Plans, pricing & promotions](https://docs.recurly.com/docs/overview)
- [Do you need help?](https://docs.recurly.com/docs/do-you-need-help)
- [Subscriptions: Subscription lifecycle](https://docs.recurly.com/docs/subscription-lifecycle)
- [Communications: Lifecycle communications](https://docs.recurly.com/docs/lifecycle-communications)
- [Integrations: Recurly Developer Hub](https://recurly.com/developers/) & [Hosted pages](https://docs.recurly.com/docs/hosted-pages)
- Payments: [Payment orchestration](https://docs.recurly.com/docs/overview-4), [Payment gateway & merchant account overview](https://docs.recurly.com/docs/gateway-merchant-account-overview) & [Payment settings](https://docs.recurly.com/docs/payment-settings)
- Processing specific transaction types:
  - **Note: **Standard Recurly transaction type is a full purchase, rather than separate authorize and capture. Auth and Capture is available only for CIT transactions.
    - [Verify Billing Info](https://docs.recurly.com/docs/verify-stored-billing-info-endpoint)
    - [Auth and Capture](https://docs.recurly.com/docs/auth-and-capture)
    - [Credits and Voids](https://docs.recurly.com/docs/credit-invoices#voiding-credit-invoices-or-balances)
    - [Refund invoices](https://docs.recurly.com/docs/credit-invoices#refund-capabilities)