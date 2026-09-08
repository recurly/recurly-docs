---
title: Using a token
excerpt: >-
  Pass a Recurly.js token (token_id) to the Recurly API in place of raw payment
  details — code samples, the endpoints that accept it, and token rules.
deprecated: false
hidden: false
metadata:
  robots: index
---
<div class="rp-page">
  <div class="rp-overview">Once Recurly.js encrypts card data and returns a token (<code>token_id</code>), your server passes that token to the Recurly API in place of raw payment details — so sensitive data never touches your servers and you stay out of PCI scope. This guide covers creating a purchase with a token, the endpoints that accept one, and the token's lifespan, reuse, and security rules.</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#why-use-tokens"><span class="rp-toc-num">1</span>Why use tokens</a>
    <a class="rp-toc-pill" href="#create-a-purchase-with-a-token"><span class="rp-toc-num">2</span>Create a purchase</a>
    <a class="rp-toc-pill" href="#token-rules-and-security"><span class="rp-toc-num">3</span>Token rules & security</a>
    <a class="rp-toc-pill" href="#endpoints-that-accept-a-token"><span class="rp-toc-num">4</span>Accepted endpoints</a>
    <a class="rp-toc-pill" href="#whats-next"><span class="rp-toc-num">5</span>What's next</a>
  </div>
</div>

<div class="rp-callout rp-callout-warning">
  <div><strong><i class="fa-solid fa-triangle-exclamation" aria-hidden="true"></i> Warning</strong> Tokens expire 20 minutes after creation. Move each one from browser to backend to Recurly quickly — once a token expires, it can't be recovered.</div>
</div>

<div class="rp-callout rp-callout-note">
  <div><strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> Note</strong> This guide assumes you've integrated Recurly.js and have a <code>token_id</code> to work with. See the <a href="https://docs.recurly.com/recurly-subscriptions/docs/overview-recurlyjs" target="_blank">Recurly.js overview</a> for how tokens are created.</div>
</div>

# Why use tokens

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-shield-halved" aria-hidden="true"></i></div>
    <strong>Faster PCI compliance</strong>
    <span>SAQ-A level — no sensitive card data touches your servers.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-plug" aria-hidden="true"></i></div>
    <strong>Consistent across endpoints</strong>
    <span>The same <code>token_id</code> works for purchases, subscriptions, or standalone billing-info updates.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-arrows-rotate" aria-hidden="true"></i></div>
    <strong>Safe to retry</strong>
    <span>Tokens can be reused within the 20-minute window, simplifying idempotent flows and error recovery.</span>
  </div>
</div>

# Create a purchase with a token

Pass the token as `billing_info.token_id` on the request. Recurly swaps it for the underlying card or bank details and completes the call.

```ruby Ruby
purchase = {
  currency: "USD",
  account: {
    code: account_code,
    billing_info: { token_id: rjs_token_id }
  },
  subscriptions: [{ plan_code: plan_code }]
}
invoice_collection = @client.create_purchase(body: purchase)
```
```javascript Node.js
const purchaseReq = {
  currency: 'USD',
  account: {
    code: accountCode,
    billingInfo: { tokenId: rjsTokenId }
  },
  subscriptions: [{ planCode }]
};
const invoiceCollection = await client.createPurchase(purchaseReq);
```
```python Python
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
```java Java
PurchaseCreate purchase = new PurchaseCreate()
  .currency("USD")
  .account(new AccountPurchase()
      .code(accountCode)
      .billingInfo(new BillingInfoCreate().tokenId(rjsTokenId)))
  .subscriptions(List.of(new SubscriptionPurchase().planCode(planCode)));

InvoiceCollection collection = client.createPurchase(purchase);
```
```csharp C#
var purchaseReq = new PurchaseCreate {
  Currency = "USD",
  Account = new AccountPurchase {
    Code = accountCode,
    BillingInfo = new BillingInfoCreate { TokenId = rjsTokenId }
  },
  Subscriptions = new List<SubscriptionPurchase> {
    new SubscriptionPurchase { PlanCode = planCode }
  }
};
InvoiceCollection collection = client.CreatePurchase(purchaseReq);
```

# Token rules and security

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Rule</td><td>Detail</td></tr>
  <tr><td>Lifespan</td><td>Valid for 20 minutes from creation.</td></tr>
  <tr><td>Reuse</td><td>Can be used multiple times during that window (for example, account + subscription + one-time charge).</td></tr>
  <tr><td>Storage</td><td>The token lives only in the Recurly vault; once it expires it can't be recovered.</td></tr>
  <tr><td>Transport</td><td>Send it to your server over HTTPS only — treat it like any auth credential.</td></tr>
</table>

<div class="rp-callout rp-callout-tip">
  <div><strong><i class="fa-solid fa-lightbulb" aria-hidden="true"></i> Tip</strong> If you receive <code>transaction_error.code = invalid_token</code>, request a fresh token from Recurly.js and retry.</div>
</div>

# Endpoints that accept a token

Attach `token_id` inside `billing_info` on any of these:

<ul class="rp-list">
  <li><strong>Purchase</strong> — <a href="https://docs.recurly.com/recurly-subscriptions/v2021-02-25/reference/create_purchase" target="_blank">Create a purchase</a></li>
  <li><strong>Subscription</strong> — <a href="https://docs.recurly.com/recurly-subscriptions/v2021-02-25/reference/create_subscription" target="_blank">Create a subscription</a></li>
  <li><strong>Account</strong> — <a href="https://docs.recurly.com/recurly-subscriptions/v2021-02-25/reference/create_account" target="_blank">Create</a> / <a href="https://docs.recurly.com/recurly-subscriptions/v2021-02-25/reference/update_account" target="_blank">Update</a></li>
  <li><strong>Billing info</strong> — <a href="https://docs.recurly.com/recurly-subscriptions/v2021-02-25/reference/update_billing_info" target="_blank">Set an account's billing information</a></li>
</ul>

Attach the token like so:

```json
"billing_info": {
  "token_id": "1d1e4f0447c2b7e6d2f6cbf5c4b2c9aa"
}
```

Recurly swaps the token for the underlying card or bank details and completes the request while you stay out of PCI scope.

# What's next

- <a href="https://docs.recurly.com/recurly-subscriptions/v2021-02-25/reference" target="_blank">Recurly Subscriptions API reference</a> — the complete endpoint and field schema
- <a href="https://docs.recurly.com/recurly-subscriptions/v2021-02-25/reference/create_purchase" target="_blank">Create a purchase</a> — the full request and response for a token-based purchase
- <a href="https://docs.recurly.com/recurly-subscriptions/docs/overview-recurlyjs" target="_blank">Recurly.js overview</a> — how tokens are generated in the browser

{/*
📋 TODO before publishing:
- [ ] Transaction endpoint — the source listed a fifth entry, "Transaction — Create," linking to list_account_transactions. That's a GET list endpoint and doesn't accept token_id, so it was removed. If a fifth object was intended, confirm which endpoint (for example, create_billing_info — "Add new billing information on an account") and I'll add it.
- [ ] API version — reference links use the v2021-02-25 path. Switch to another version or to /latest if you'd prefer.
- [ ] Page slug — confirm this page's slug (suggested: using-a-token) and its placement in the Recurly.js section.
*/}
