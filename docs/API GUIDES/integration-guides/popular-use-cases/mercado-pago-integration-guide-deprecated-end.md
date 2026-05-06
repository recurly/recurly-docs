---
title: Mercado Pago integration guide
excerpt: >-
  Create subscriptions via Purchase API with Mercado Pago, Recurly.js, and Ebanx
  sandbox flow.
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

This guide shows you how to use the <Anchor label="Purchase endpoint" target="_blank" href="https://developers.recurly.com/api/latest/#tag/purchase">Purchase endpoint</Anchor> to create new subscriptions using the Mercado Pago payment method. We’ll also illustrate how to work with the Ebanx sandbox simulator.

### Prerequisites & limitations

* Familiarity with Recurly’s API, Webhooks, and basic REST concepts
* <Anchor label="Completed the Quickstart Guide" target="_blank" href="https://docs.recurly.com/recurly-subscriptions/docs/quick-start-guide#/">Completed the Quickstart Guide</Anchor>
* Familiarity with Recurly.js
* An Ebanx gateway account with Mercado Pago enabled

***

# Definition

**Creating Purchases** refers to the process of generating new customer accounts alongside subscriptions in a single, consolidated call to the Recurly Purchase endpoint. This streamlines checkout experiences by bundling all required resources into one request.

***

# Creating purchases

## Step 1: Generate a Mercado Pago Payment Request

Use a supported client library or our  `type`  payment field in your front-end code. Our client libraries help you build out our APIs easily and process transactions faster. To specify Mercado Pago, set your `type` enum to `mercadopago`and ensure you are passing the required fields.

See our <Anchor label="Mercado Pago documentation" target="_blank" href="https://docs.recurly.com/recurly-subscriptions/docs/mercadopago#/">Mercado Pago documentation</Anchor> for details on all required fields.

**Send** a request to the `create_purchase` method on Recurly’s API, including:

* **Customer account data** (e.g., code, name, billing info, phone number, email address)
* **Subscriptions** (with plan codes)
* **Type** of payment method. In this case, `mercadopago`.

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

## Step 2: Obtain the token from the response

Upon submitting your API request you will receive a response that looks like this:

```json
{
    "error": {
        "type": "transaction",
        "message": "Your card must be authenticated with 3-D Secure before continuing.",
        "transaction_error": {
            "object": "transaction_error",
            "transaction_id": "xt43lgkyc7s4",
            "category": "three_d_secure_action_required",
            "code": "three_d_secure_action_required",
            "decline_code": null,
            "message": "Your card must be authenticated with 3-D Secure before continuing.",
            "merchant_advice": "Your payment gateway is requesting that the transaction be completed with 3-D Secure.",
            "three_d_secure_action_token_id": "kFzyWEnvBZ82pccJwGiMag",
            "fraud_info": null
        }
    }
}
```

Mercado Pago requires consumer authentication, and so interacting with Recurly.js is necessary to allow consumers to authenticate their identity and authorize payments in their mobile apps. You will need to use the   `three_d_secure_action_token_id`value to render the modal for this process.

This initial call will return different behavior in production than in sandbox.

***

## Step 3: Interact with Recurly.js

You can follow along in our 3DS Redirect Guide, starting at **Step 3**: [Recurly.js Token-ID Redirect Guide]([https://docs.recurly.com/recurly-subscriptions/docs/3d-secure-20-integration-guide#/step-3-process-the-responsew](https://docs.recurly.com/recurly-subscriptions/docs/3d-secure-20-integration-guide#/step-3-process-the-responsew).

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

## Sandbox behavior

In Sandbox, the modal will display the Ebanx specific sandbox UI, and manually pressing buttons to simulate proper enrollments is required. You can submit accepted enrollments as well as deny or decline enrollments in sandbox.

***

## Next steps

Now that you can create new  [subscriptions](https://app.recurly.com/go/subscriptions), explore payment method guide to explore other use cases and limitations related to the [Mercado Pago payment method](https://docs.recurly.com/recurly-subscriptions/docs/mercadopago#/).

<br />
