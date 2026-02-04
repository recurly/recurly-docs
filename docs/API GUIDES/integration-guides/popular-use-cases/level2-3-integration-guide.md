---
title: Level II / III Data integration guide
excerpt: >-
  Create subscriptions or one time charges via Purchase API with Level II and
  III data for commercial cards.
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

This guide shows you how to use the <Anchor label="Purchase endpoint" target="_blank" href="https://developers.recurly.com/api/latest/#tag/purchase">Purchase endpoint</Anchor> to create new subscriptions or one-time charge using the commercial card Level 2/3 Data with credit card payment method. 

## Prerequisites & limitations

* Familiarity with Recurly’s API, Webhooks, and basic REST concepts
* <Anchor label="Completed the Quickstart Guide" target="_blank" href="https://docs.recurly.com/recurly-subscriptions/docs/quick-start-guide#/">Completed the Quickstart Guide</Anchor>
* Familiarity with Recurly.js or APIs

## Supported Gateways 

### Level 2 Data 

* Adyen, Auth.net, Braintree, Stripe, Cybersource, WorldPay, Vantiv, CommerceHub, Nuvei, Checkout.com, FreedomPay, and TSYS. 

### Level 3 Data 

* Adyen

***

# Definition

**Creating Purchases** refers to the process of generating new customer accounts in a single, consolidated call to the Recurly Purchase endpoint. You may create subscriptions or one time purchases through this endpoint. This streamlines checkout experiences by bundling all required resources into one request.

**One Time Purchases** refers to a stand-alone transaction unrelated to a subscription. You may include line items in these transactions, but they will not include plan codes. 

***

# Creating purchases

## Step 1: Generate a Card Payment Request

Use a supported client library, our API, and/or Recurly.js in your front-end code. Our client libraries help you build out our APIs easily and process transactions faster. To specify Level 2 data, ensure you are passing the required fields.

**Level 2/II**: 

* `po_number`
* Tax details -- you may use Avalara, Vertex, or enable taxes in Recurly natively. _Level 2 cannot be tax exempt_.

**Level 3/III**:

* Everything from Level 2. Level 3/III transactions _can_ be marked as tax exempt however. 
* Harmonized / HS Commodity Code in your item catalog, or use the `harmonized_system_code` parameter 
* All line item fields including: `unit_amount`, `quantity`, `description`, `type`, `product_code` **or** ensure you are filling out all applicable fields when creating items in your Recurly item catalog.
* If you are shipping physical product, ensure you are sending the shipping address, and shipping method/fees by creating a Shipping Method, and specifying it via api along side the `shipping.amount` parameter in the `subscriptions` object. If you are creating one time purchases, use the top level `shipping.fees` object to pass in shipping / freight costs.
* If you are discounting your products, use Coupons to pass in a discount amount, and specify via the `coupon_codes` parameter.

**Send** a request to the `create_purchase` method on Recurly’s API, including:

* Level 1 Data, which includes**Customer account data** (e.g., code, name, billing info, phone number, email address), and Level 2 or 3 data depending on your intent.
* **Subscriptions** (with plan codes)
* **Shipping and Tax data**
* **Discount data** if applicable

### Code / Payload examples 

**Below is an example JSON payload for a Level 2/II purchase request:** 

```json
Pending
```

**Below is an example JSON payload for a Level 3/III purchase request:**

```json
{
  "currency": "USD",
  "account": {
    "code": "{{customer-account-code}}" // Account with Billing Information + Card on File
  },
  "line_items": [ // You may also supply Recurly item codes
    {
      "unit_amount": "10.00",
      "quantity": 2,
      "description": "Custom 4x4 Art Print",
      "type": "charge",
      "tax_code": "physical",
      "product_code": "100B",
      "tax_exempt": false,
      "harmonized_system_code": "456789" // HS Code, Commodity Code
    }
  ],
  "shipping": {
    "address": {
      "first_name": "John",
      "last_name": "Doe",
      "phone": "1234567890",
      "street1": "201 main St",
      "city": "Los Angeles",
      "region": "CA",
      "postal_code": "12345",
      "country": "US"
    },
    "fees": {
      "method_code": "{{method-code}}",
      "amount": "5.00" // Shipping Freight Amount
    }
  },
  "po_number": "123456", // Purchase Order Number 
  "coupon_codes": [
    "15percent"
  ],
  "gateway_code": "{{gateway-code}}"
}
```

Below are example calls in different languages:

```ruby
purchase = {
  currency: "BRL",
  account: {
    code: "bdumonde",
    first_name: "Benjamin",
    last_name: "Du Monde",
    email: "bdumonde@example.com",
    billing_info: {
      address: {
      street1: "Avenida Nipo-brasileira 1007",
      city: "Braganca Paulista",
      region: "BR",
      postal_code: "123456",
      country: "BR",
      phone: "1234679099"
			}
    },
    type: "mercadopago"
  },
  subscriptions: [
    { plan_code: "coffee-monthly" }
  ]
}
invoice_collection = @client.create_purchase(body: purchase)
```
```javascript
let purchaseReq = {
  currency: "BRL",
  account: {
    code: "bdumonde",
    first_name: "Benjamin",
    last_name: "Du Monde",
    email: "bdumonde@example.com",
    billing_info: {
			address: {
        street1: "Avenida Nipo-brasileira 1007",
        city: "Braganca Paulista",
        region: "BR",
        postal_code: "123456",
        country: "BR",
        phone: "1234679099"
			}
    },
    type: "mercadopago"
  },
  subscriptions: [
    { plan_code: "coffee-monthly" }
  ]
};
let invoiceCollection = await client.createPurchase(purchaseReq)
```
```python
purchase = {
    "currency": "BRL",
    "account": {
        "code": "bdumonde",
        "first_name": "Benjamin",
        "last_name": "Du Monde",
        "email": "bdumonde@example.com",
        "billing_info": {
						"address":{
              "street1": "Avenida Nipo-brasileira 1007",
              "city": "Braganca Paulista",
              "region": "BR",
              "postal_code": "123456",
              "country": "BR",
              "phone": "1234679099"
						}
        },
        "type": "mercadopago"
    },
    "subscriptions": [
        {"plan_code": "coffee-monthly"}
    ]
}
invoice_collection = client.create_purchase(purchase)
```
```java
PurchaseCreate purchase = new PurchaseCreate();
purchase.setCurrency("BRL");

AccountPurchase account = new AccountPurchase();
account.setCode("bdumonde");
account.setFirstName("Benjamin");
account.setLastName("Du Monde");
account.setEmail("bdumonde@example.com");
account.setType("mercadopago");

BillingInfoCreate billing = new BillingInfoCreate();
billing.setStreet1("Avenida Nipo-brasileira 1007");
billing.setCity("Braganca Paulista");
billing.setRegion("BR");
billing.setPostalCode("123456");
billing.setCountry("BR");
billing.setPhone("1234679099");

List<SubscriptionPurchase> subs = new ArrayList<>();
SubscriptionPurchase sub = new SubscriptionPurchase();
sub.setPlanCode("coffee-monthly");
subs.add(sub);
purchase.setSubscriptions(subs);

InvoiceCollection collection = client.createPurchase(purchase);
```
```csharp
var purchaseReq = new PurchaseCreate()
{
    Currency = "BRL",
    Account = new AccountPurchase()
    {
        Code = "bdumonde",
        FirstName = "Benjamin",
        LastName = "Du Monde",
        Email = "bdumonde@example.com",
        BillingInfo = new BillingInfoCreate()
        {
            Street1 = "Avenida Nipo-brasileira 1007",
            City = "Braganca Paulista",
            Region = "BR",
            PostalCode = "123456",
            Country = "BR",
            Phone = "1234679099"
        },
        Type = "mercadopago"
    },
    Subscriptions = new List<SubscriptionPurchase>()
    {
        new SubscriptionPurchase() { PlanCode = "coffee-monthly" }
    }
};

InvoiceCollection collection = client.CreatePurchase(purchaseReq);
```

> **Tip:** Many more parameters are available. See the <Anchor label="Create Purchase" target="_blank" href="https://developers.recurly.com/api/latest/#operation/create_purchase">Create Purchase</Anchor> reference to learn more.

***

## Step 2: Interact with Recurly.js if applicable

You can follow along in our 3DS Redirect Guide, starting at **Step 3**: [Recurly.js Token-ID Redirect Guide]([https://docs.recurly.com/recurly-subscriptions/docs/3d-secure-20-integration-guide#/step-3-process-the-response](https://docs.recurly.com/recurly-subscriptions/docs/3d-secure-20-integration-guide#/step-3-process-the-responsew).

***

## Step 4: Submit a new Purchase request

Once the user has interacted with the modal, and you have a `three_d_secure_action_result_token_id`from Recurly.js, you must resubmit your original request with the results token ID.

Use the `three_d_secure_action_result_token_id` from **Step 3** in a new API call (e.g., Create Purchase) to finalize authentication. The account/billing info must match the original request. Changing these details may cause a token mismatch error.

You JSON payload may look like this:

```json
{
    "subscriptions": [
		{
			"plan_code": "monthly-plan" 

		}
	],
    "account": {
        "code": "maddams",
        "email":"maddams@recurly.com",
        "billing_info": {
            "first_name":"M",
            "last_name":"Addams",
            "address":{
                "street1":"Avenida Nipo-brasileira 1007",
                "city":"Braganca Paulista",
                "region":"BR",
                "postal_code":"12902-020",
                "country":"BR",
                "phone":"123456790"
            },
            "type":"mercadopago",
            "three_d_secure_action_result_token_id":"action-result-id"
        }
    },
    "currency": "BRL"
}
```

***

## Step 4: Verify and finish

After a successful purchase, you can confirm the details via the Recurly Admin UI or by calling Recurly’s API to list your new account, subscription, or invoice.

***

## Step 5: Listen for webhooks

After a successful signup, there will be several webhooks you should listen to in order to ensure you are enabling access to features on in your environment, and disabling access should a consumer decide to cancel their subscription from within their mobile banking applicaiton.

***

## Next steps

Now that you can create new  [subscriptions](https://app.recurly.com/go/subscriptions), explore payment method guide to explore other use cases and limitations related to the [Mercado Pago payment method](https://docs.recurly.com/recurly-subscriptions/docs/mercadopago#/).

<br />
