---
title: Using a token (4.10.3)
excerpt: Learn how to use a token using Recurly.js version 4.10.3.
deprecated: false
hidden: false
metadata:
  robots: index
---
## Using a Token

Create a new purchase with a token using one of our [client libraries](https://recurly.com/developers/api/#client-libraries) or [API v3](https://recurly.com/developers/api/v2021-02-25/index.html)

```ruby
purchase = {
  currency: "USD",
  account: {
    code: account_code,
    billing_info: {
      token_id: rjs_token_id
    },
  },
  subscriptions: [
    { plan_code: plan_code }
  ]
}

invoice_collection = @client.create_purchase(body: purchase)
```
```javascript
let purchaseReq = {
  currency: 'USD',
  account: {
    code: accountCode,
    billingInfo: {
      tokenId: rjsTokenId
    }
  },
  subscriptions: [
    { planCode: planCode },
  ]
}

let invoiceCollection = await client.createPurchase(purchaseReq)
```
```python
purchase = {
    "currency": "USD",
    "account": {
        "code": account_code,
        "billing_info": {"token_id": rjs_token_id},
    },
    "subscriptions": [{"plan_code": plan_code}],
}
invoice_collection = client.create_purchase(purchase)
```
```java
PurchaseCreate purchase = new PurchaseCreate();
purchase.setCurrency("USD");

AccountPurchase account = new AccountPurchase();
account.setCode(accountCode);
purchase.setAccount(account);

BillingInfoCreate billing = new BillingInfoCreate();
billing.setTokenId(rjsTokenId);
account.setBillingInfo(billing);

List<SubscriptionPurchase> subscriptions = new ArrayList<SubscriptionPurchase>();
SubscriptionPurchase sub = new SubscriptionPurchase();
sub.setPlanCode(planCode);
subscriptions.add(sub);
purchase.setSubscriptions(subscriptions);

InvoiceCollection collection = client.createPurchase(purchase);
```
```csharp
var purchaseReq = new PurchaseCreate()
{
    Currency = "USD",
    Account = new AccountPurchase()
    {
        Code = accountCode,
        BillingInfo = new BillingInfoCreate()
        {
            TokenId = rjsTokenId
        }
    },
    Subscriptions = new List<SubscriptionPurchase>()
    {
        new SubscriptionPurchase() { PlanCode = planCode }
    }
};

InvoiceCollection collection = client.CreatePurchase(purchaseReq);
```

Once Recurly.js has stored your customer's sensitive data and given you a token reference, you will have 20 minutes to use it in our [API](https://recurly.com/developers/api/). Expired tokens are permanently removed from the Recurly servers. Since tokens may be used to create charges in Recurly, be sure to keep them safe and only transmit them over a secure connection. Note that tokens do not expire after their first use. They can be reused as many times as you need during that 20 minute period.

> **Note**: Tokens expire after 20 minutes.

Tokens can be used to populate any account Billing Info data through our API. Simply assign it to the Billing Info's `token_id` property and we'll do the rest.

### These endpoints accept tokens within billing info

* Subscription [create](https://recurly.com/developers/api/v2021-02-25/index.html#operation/create_subscription)
* Account [create](https://recurly.com/developers/api/v2021-02-25/index.html#operation/create_account), [update](https://recurly.com/developers/api/v2021-02-25/index.html#operation/update_account)
* Billing Info [update](http://recurly.com/developers/api/v2021-02-25/index.html#operation/update_billing_info)
* Transaction [create](https://recurly.com/developers/api/v2021-02-25/index.html#operation/list_account_transactions)

> **Note**: If you use a token, no other attributes will be allowed on that Billing Info for that request.