---
title: UPI AutoPay integration guide
excerpt: >-
  Create subscriptions via Purchase API using UPI AutoPay with a VPA and Ebanx
  sandbox simulation.
deprecated: false
hidden: false
metadata:
  title: Recurly | UPI AutoPay Integration Guide
  robots: index
---
# Overview

This guide shows you how to use the [Purchase endpoint](https://developers.recurly.com/api/latest/#tag/purchase) to create new subscriptions using the UPI AutoPay payment method. We’ll also illustrate how to work with the Ebanx sandbox simulator.

### Prerequisites & limitations

* Familiarity with Recurly’s V3 API, Webhooks, and basic REST concepts
* [Completed the Quickstart Guide](https://docs.recurly.com/recurly-subscriptions/docs/quick-start-guide#/)
* An [Ebanx](https://docs.recurly.com/recurly-subscriptions/docs/ebanx-gateway#/) gateway account with [UPI AutoPay](https://docs.recurly.com/recurly-subscriptions/docs/upi-autopay#/) is enabled

***

# Definition

**Creating Purchases** refers to the process of generating new customer accounts alongside subscriptions in a single, consolidated call to the Recurly Purchase endpoint. This streamlines checkout experiences by bundling all required resources into one request.

***

# Creating Purchases

## Step 1: Generate a UPI AutoPay Payment Request

**Use** a supported client library or our  `payment_gateway_references`  payment object in your API implementation. Our client libraries help you build out our APIs easily and process transactions faster. To specify UPI AutoPay, you will send  set your `reference_type` enum to `upi_vpa`and ensure you are passing the customer's VPA as the `token` value.

See our <Anchor label="UPI AutoPay documentation" target="_blank" href="https://docs.recurly.com/recurly-subscriptions/docs/upi-autopay#/">UPI AutoPay documentation</Anchor> for details on all required fields.

**Send** a request to the create `purchase` endpoint on Recurly’s API, including:

* **Customer account data** (e.g., code, name, billing info, phone number, email address, VPA)
* **Subscriptions** (with plan codes)
* **Customer VPA** (example: customerid@bankname)

Example payload:

```json
“billing_info“: {
“payment_gateway_references“: [
	{
	“token”: “upi-vpa-value”,
	“reference_type“: “upi_vpa“
	}
],

```

<br />

Below are example calls in different languages:

```ruby
purchase = {
  currency: "INR",
  account: {
    code: "bdumonde",
    first_name: "Benjamin",
    last_name: "Du Monde",
    email: "bdumonde@example.com",
    billing_info: {
      first_name: "Benjamin",
			last_name: "Du Monde",
			address: {
        street1: "44/1 Bharat Apartment 4C 5th Main Road",
        city: "Bengaluru",
        region: "KA",
        postal_code: "560041",
        country: "IN",
        phone: "1234679099"
      },
			gateway_code: "gateway-code",
      payment_gateway_references: [{
				token: "vpa-value",
				reference_type: "upi_vpa"
				}]
    }
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
			first_name: "Benjamin",
      last_name: "Du Monde",
			address: {
        street1: "44/1 Bharat Apartment 4C 5th Main Road",
        city: "Bengaluru",
        region: "KA",
        postal_code: "560041",
        country: "IN",
        phone: "1234679099"
      },
			gateway_code: "gateway-code",
      payment_gateway_references: [{
				token: "vpa-value",
				reference_type: "upi_vpa"
				}]
    }
  },
  subscriptions: [
    { plan_code: "coffee-monthly" }
  ]
};
let invoiceCollection = await client.createPurchase(purchaseReq)
```
```python
purchase = {
    "currency": "INR",
    "account": {
        "code": "bdumonde",
        "first_name": "Benjamin",
        "last_name": "Du Monde",
        "email": "bdumonde@example.com",
        "billing_info": {
            "address":{
						"street1": "44/1 Bharat Apartment 4C 5th Main Road",
            "city": "Bengaluru",
            "region": "KA",
            "postal_code": "560041",
            "country": "IN",
            "phone": "1234679099"
           },
          "gateway_code":"gateway-code-value",
          "payment_gateway_references": [{
            "token":"customer-vpa-value",
						"reference_type":"upi_vpa"
				}]
    },
    "subscriptions": [
        {"plan_code": "coffee-monthly"}
    ]
}
invoice_collection = client.create_purchase(purchase)
```
```java
// ... (assuming all other POJO classes like Address, BillingInfo, etc., are defined)

// 1. Create the innermost objects
Address address = new Address();
address.setStreet1("44/1 Bharat Apartment 4C 5th Main Road");
address.setCity("Bengaluru");
// ... set all other address fields

PaymentGatewayReference paymentRef = new PaymentGatewayReference();
paymentRef.setToken("customer-vpa-value");
paymentRef.setReferenceType("upi_vpa");

// 2. Create the Account
Account account = new Account();
account.setCode("bdumonde");
account.setFirstName("Benjamin");
account.setLastName("Du Monde");
account.setEmail("bdumonde@example.com");
// ... etc.

// 3. Create the final Purchase
Purchase purchase = new Purchase();
purchase.setCurrency("INR");
purchase.setAccount(account);
purchase.setSubscriptions(List.of(new Subscription(...)));

InvoiceCollection collection = client.createPurchase(purchase);
```
```csharp
var purchaseReq = new PurchaseCreate()
{
    Currency = "INR",
    Account = new AccountPurchase()
    {
        Code = "bdumonde",
        Email = "bdumonde@example.com",
        BillingInfo = new BillingInfoCreate()
        {
            FirstName = "Benjamin",
            LastName = "Du Monde",
            Address = new AddressInfo()
            {
                Phone = "1234679099",
                Street1 = "44/1 Bharat Apartment 4C 5th Main Road",
                City = "Bengaluru",
                PostalCode = "400008",
                Region = "KA",
                Country = "1234679099"
            },
            GatewayCode = "gateway-code-here",
            PaymentGatewayReferences = new List<PaymentGatewayReferenceInfo>()
            {
                new PaymentGatewayReferenceInfo() 
                { 
                    Token = "vpa@bankname", 
                    ReferenceType = "upi_vpa" 
                }
            }
        }
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

## Step 2: Process the purchase response

A successful purchase returns an **InvoiceCollection**, which contains any charge or credit invoices generated by the request. If the purchase fails, you’ll receive an error response indicating what went wrong. **UPI AutoPay** transactions will be in a **Scheduled** state, and the Invoice will be **Pending**.

UPI AutoPay uses enrollment with the consumer's bank to allow consumers to authenticate their identity and authorize payments in their mobile apps. This process usually takes only a few minutes, and will auto-cancel if the consumer does not respond to the push notification on their phone.

This initial call will return different behavior in production than in sandbox.

In **Production**: You will receive confirmation of a pending transaction, or an error message if a required field was missing.

In **Sandbox**: You will need to load the `return_url` value that represent the gateway's simulated UPI Enrollment process with the consumer's App. You may render this in a modal for testing purposes or redirect to your liking.

* Once within the simulator, you can simulate approvals, cancellations, and declines of the enrollment itself.
* If you choose to simulate an enrollment, ensure you have all proper webhooks set up at Ebanx. See the [Ebanx Gateway](https://docs.recurly.com/recurly-subscriptions/docs/ebanx-gateway#/) setup page for more information.

***

## Step 3: Verify and finish

After a successful purchase, you can confirm the details via the Recurly Admin UI or by calling Recurly’s API to list your new account, subscription, or invoice.

***

## Step 4: Listen for webhooks

After a successful signup, there will be several webhooks you should listen to in order to ensure you are enabling access to features on in your environment, and disabling access should a consumer decide to cancel their subscription from within their mobile banking application.

It is recommended that you listen for at least the three webhooks below, and additional context is available on the [Ebanx gateway](https://docs.recurly.com/docs/ebanx-gateway#/) and [UPI AutoPay](https://docs.recurly.com/docs/upi-autopay#/) pages respectively. Since consumers can cancel, pause, and resume subscriptions within the UPI App, it is extremely important to listen for these events.

* [Subscription Cancellation Event](https://recurly.com/developers/reference/webhooks/#canceled-subscription)
* [Subscription Pause Event](https://recurly.com/developers/reference/webhooks/#paused-subscription)
* [Subscription Resume Event](https://recurly.com/developers/reference/webhooks/#resumed-subscription)

# Sandbox behavior

In Step 2, Sandbox `return_url` behavior is outlined, but requires a bit more explanation. You may render this URL in whatever way you wish (modal, full redirect, etc.) however it is not recommended to put an immense amount of effort into it as this is not a production workflow.

To help with simulating a consumer's bank app, the gateway has provided a simulation site which can "pretend" to ferry along an enrollment signup and transaction authorization.

**Step 1:** Upon visiting the return URL, you can click **Accept Agreement** or choose another option.

**Step 2:** You're done!

## Confirming High Amount Renewals in Sandbox

When processing with UPI, any amount over 15K INR, a push notification would go to the consumer in a Production environment. In Sandbox, you will need to follow these instructions:

* Search for the Pending Payment in the Ebanx dashboard (Navigate to 'Payments' and choose the Pending Payment), click on the associated payment (or search via the Reference/ Hash), and choose the action you wish to take (Cancel or Confirm).
  * _Confirming_ the payment will create a Approval in Recurly.
  * _Cancelling_ will cause the payment to decline and the invoice to enter dunning.

***

## Next steps

Now that you can create new  <Anchor label="subscriptions" target="_blank" href="https://app.recurly.com/go/subscriptions">subscriptions</Anchor>, explore payment method guide to explore other use cases and limitations related to the <Anchor label="UPI AutoPay payment method" target="_blank" href="https://docs.recurly.com/docs/upi-autopay#/">UPI AutoPay payment method</Anchor>.

<br />
