---
title: Copy of Pix Automático Integration guide
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

This guide shows you how to use the [Purchase endpoint](https://developers.recurly.com/api/latest/#tag/purchase) to create new subscriptions using the PIX Automático payment method. We’ll also illustrate how to work with the Ebanx sandbox simulator.

### Prerequisites & limitations

* Familiarity with Recurly’s API, Webhooks, and basic REST concepts
* [Completed the Quickstart Guide](https://docs.recurly.com/v1.1/docs/quick-start-guide#/)
* Familiarity with Base64 value rendering
* An Ebanx gateway account with Pix Automático is enabled

***

# Definition

**Creating Purchases** refers to the process of generating new customer accounts alongside subscriptions in a single, consolidated call to the Recurly Purchase endpoint. This streamlines checkout experiences by bundling all required resources into one request.

***

# Creating Purchases

## Step 1: Generate a Pix Payment Request

Use a supported client library or our  `type`  payment field in your front-end code. Our client libraries help you build out our APIs easily and process transactions faster. To specify Pix Automático, set your `type` enum to `pix_automatico`and ensure you are passing a `tax_identifier` and `tax_identifier_type` for Brazil.

See our [Pix Automático documentation](https://docs.recurly.com/recurly-subscriptions/docs/pix-automatico#/) for details on all required fields.

Send a request to the `create_purchase` method on Recurly’s API, including:

* **Customer account data** (e.g., code, name, billing info, phone number, email address, tax ID/tax type)
* **Subscriptions** (with plan codes)
* **Type** of payment method. In this case, `pix_automatico`.

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
      street1: "Avenida Nipo-brasileira 1007",
      city: "Braganca Paulista",
      region: "BR",
      postal_code: "123456",
      country: "BR",
      phone: "1234679099"
    },
    type: "pix_automatico",
    tax_identifier: "brazilian-cpf-value",
    tax_identifier_type: "cpf"
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
      street1: "Avenida Nipo-brasileira 1007",
      city: "Braganca Paulista",
      region: "BR",
      postal_code: "123456",
      country: "BR",
      phone: "1234679099"
    },
    type: "pix_automatico",
    tax_identifier: "brazilian-cpf-value",
    tax_identifier_type: "cpf"
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
            "street1": "Avenida Nipo-brasileira 1007",
            "city": "Braganca Paulista",
            "region": "BR",
            "postal_code": "123456",
            "country": "BR",
            "phone": "1234679099"
        },
        "type": "pix_automatico",
        "tax_identifier": "brazilian-cpf-value",
        "tax_identifier_type": "cpf"
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
account.setType("pix_automatico");
account.setTaxIdentifier("brazilian-cpf-value");
account.setTaxIdentifierType("cpf");

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
        Type = "pix_automatico",
        TaxIdentifier = "brazilian-cpf-value",
        TaxIdentifierType = "cpf"
    },
    Subscriptions = new List<SubscriptionPurchase>()
    {
        new SubscriptionPurchase() { PlanCode = "coffee-monthly" }
    }
};

InvoiceCollection collection = client.CreatePurchase(purchaseReq);
```

> **Tip:** Many more parameters are available. See the [Create Purchase](https://developers.recurly.com/api/latest/#operation/create_purchase) reference to learn more.

***

## Step 2: Process the purchase response

A successful purchase returns an **InvoiceCollection**, which contains any charge or credit invoices generated by the request. If the purchase fails, you’ll receive an error response indicating what went wrong. **Pix Automatico** transactions will be in a **Scheduled** state, and the Invoice will be **Pending**.

Pix Automático uses QR Codes to allow consumers to authenticate their identity and authorize payments in their mobile apps. You will need to render the Base64 QR code value in your checkout page.

This initial call will return different behavior in production than in sandbox.

In **Production**: (`next_action.type`and `next_action.value`) represent the QR code value that you will need to render on your checkout page for the consumer to scan and continue authorizing the payment.

In **Sandbox**: (`next_action.type`and `next_action.value`) will be present, but you will need to load the `return_url` value that represent the gateway's simulated Pix QR Code interaction with the consumer's App. You may render this in a modal for testing purposes.

```ruby
invoice = invoice_collection.charge_invoice
puts "Created Invoice #{invoice}"
```
```js
let invoice = invoiceCollection.chargeInvoice
console.log('Created Invoice:', invoice)
```
```python
invoice = invoice_collection.charge_invoice
print("Created Invoice %s" % invoice)
```
```java
Invoice invoice = collection.getChargeInvoice();
System.out.println("Created Charge Invoice with Id: " + invoice.getId());
```
```csharp
Invoice invoice = collection.ChargeInvoice;
Console.WriteLine($"Created Invoice with Number: {invoice.Number}");
```

***

## Step 3: Verify and finish

After a successful purchase, you can confirm the details via the Recurly Admin UI or by calling Recurly’s API to list your new account, subscription, or invoice.

***

## Step 4: Listen for Webhooks

After a successful signup, there will be several webhooks you should listen to in order to ensure you are enabling access to features on in your environment, and disabling access should a consumer decide to cancel their subscription from within their mobile banking applicaiton.

## Sandbox Behavior

In Step 2, Sandbox return_url behavior is outlined, but requires a bit more explanation. You may render this URL in whatever way you wish (modal, full redirect, etc.) however it is not recommended to put an immense amount of effort into it as this is not a production workflow.

To help with simulating a consumer's bank app, the gateway has provided a simulation site which can "pretend" to ferry along an enrollment signup and transaction authorization.

**Step 1:** Upon visiting the return URL, immediately navigate to **Go to enrollment simulator.**

**Step 2:** Approve the enrollment (for a success use case) by choosing 'Accept Agreement'. You may also deny the use case to test a consumer declining the enrollment request. This will result in a 404 page.

**Step 3:** Return to the original simulator URL and click **Authorized = YES** on page, to simulate a successful initial authorization for payment. This will result in a mostly blank page with a confusing response. Unfortunately, this is the limitation of the third party simulator.

**Step 4:** You're done!

***

## Next steps

Now that you can create new  [subscriptions](https://app.recurly.com/go/subscriptions), explore payment method guide to explore other use cases and limitations related to the [Pix Automatico payment method](https://docs.recurly.com/recurly-subscriptions/docs/pix-automatico#/).

<br />