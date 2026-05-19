---
title: Create and manage subscriptions
excerpt: >-
  Learn how to create and manage subscriptions using the Recurly API v3,
  covering authentication, SDK setup, account and plan creation, subscription
  lifecycle management, webhook configuration, and sandbox testing.
deprecated: false
hidden: true
metadata:
  robots: index
---
<div class="rp-page">

  <div class="rp-overview">This guide walks you through building a complete subscription integration with Recurly's API v3 — from authenticating your first request to managing the full subscription lifecycle. By the end, you'll have working code that creates accounts, assigns plans, starts subscriptions, handles billing changes, and responds to lifecycle events via webhooks.</div>

  <div class="rp-plan">✦ Available on all Recurly plans</div>

  <div class="rp-cost">
    <strong>Additional cost</strong><br/>
    Dunning and advanced retry logic require an additional cost. Please reach out to your Recurly account manager or <a href="mailto:support@recurly.com">support@recurly.com</a> for pricing details.
  </div>

  ### Prerequisites
  <ul class="rp-list">
    <li>A Recurly account with API access enabled</li>
    <li>A private API key from <strong>Integrations > API Keys</strong> in the Recurly Admin Dashboard</li>
    <li>Your Recurly site ID, visible in the Admin Dashboard URL: <code>app.recurly.com/a/<strong>your-site-id</strong></code></li>
    <li>One of the supported runtimes: Ruby 2.7+, Node.js 18+, Python 3.8+, Java 11+, .NET 6+, or PHP 8.0+</li>
  </ul>

  ### Limitations
  <ul class="rp-list">
    <li>The Recurly API enforces a rate limit of 1,400 requests per minute per site. Requests beyond this threshold return a <code>429</code> response.</li>
    <li>Subscription quantity changes take effect at the next renewal by default. Immediate prorated changes require setting <code>timeframe: now</code> on the update request.</li>
    <li>Trial periods cannot be extended after a subscription is active.</li>
  </ul>

  ### Supported SDKs

</div>

<div class="rp-sdk-grid">
<Cards>
  <Card title="Ruby" href="https://github.com/recurly/recurly-client-ruby"></Card>
  <Card title="Node.js" href="https://github.com/recurly/recurly-client-node"></Card>
  <Card title="Python" href="https://github.com/recurly/recurly-client-python"></Card>
  <Card title="Java" href="https://github.com/recurly/recurly-client-java"></Card>
  <Card title="C#" href="https://github.com/recurly/recurly-client-dotnet"></Card>
  <Card title="PHP" href="https://github.com/recurly/recurly-client-php"></Card>
</Cards>
</div>

<div class="rp-page">

  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-concepts"><span class="rp-toc-num">2</span>Key concepts</a>
    <a class="rp-toc-pill" href="#integration-guide"><span class="rp-toc-num">3</span>Integration guide</a>
    <a class="rp-toc-pill" href="#error-handling-and-troubleshooting"><span class="rp-toc-num">4</span>Error handling and troubleshooting</a>
    <a class="rp-toc-pill" href="#webhooks"><span class="rp-toc-num">5</span>Webhooks</a>
    <a class="rp-toc-pill" href="#testing-your-integration"><span class="rp-toc-num">6</span>Testing your integration</a>
    <a class="rp-toc-pill" href="#whats-next"><span class="rp-toc-num">7</span>What's next</a>
  </div>

</div>

# Definition

<div class="rp-definition">The Recurly Subscriptions API gives you programmatic control over the full subscription lifecycle — creating accounts, attaching payment methods, starting and modifying subscriptions, and handling renewals and cancellations. It's a REST API that accepts JSON request bodies and returns JSON responses, authenticated with your private API key over HTTPS. This guide covers API v3, Recurly's current version, which uses explicit site-scoped endpoints and returns typed error objects rather than HTTP status codes alone.</div>

# Key concepts

<div class="rp-card">

**Account** — The record that represents one of your customers in Recurly. Every subscription must belong to an Account, identified by a unique `account_code` you assign. Think of it as your customer ID bridging your system to Recurly's.

**Plan** — The template that defines a subscription's billing interval, currency, and base price. Plans are created in the Recurly Admin Dashboard or via the API, then referenced by `plan_code` when creating subscriptions.

**Subscription** — The active billing relationship between an Account and a Plan. A Subscription tracks its current state (`active`, `canceled`, `expired`, `future`, `paused`), current period dates, and any pending changes.

**Invoice** — The financial record generated at each billing event — trial end, renewal, plan change, or immediate charge. Invoices contain line items, applied credits, and the associated Transaction.

**Transaction** — The record of a single payment attempt against an Invoice. A Transaction can be `success`, `declined`, or `void`, and carries the gateway response code that explains a decline.

**Add-on** — A billable item attached to a Plan that lets you charge for usage, seats, or optional features on top of the base subscription price.

</div>

# Integration guide

## Authentication

Generate your private API key in the Recurly Admin Dashboard under **Integrations > API Keys**, then pass it as the HTTP Basic Auth username with an empty password on every request.

<div class="rp-callout rp-callout-warning">
  <div><strong>Security note</strong>Never embed your private API key in client-side code, mobile apps, or version control. Use environment variables or a secrets manager such as AWS Secrets Manager, HashiCorp Vault, or GCP Secret Manager in production.</div>
</div>

<Tabs>
  <Tab title="curl">
  ```bash
  # Replace YOUR_SITE_ID with your Recurly site ID
  # Pass the API key as the Basic Auth username; leave the password empty
  curl -u YOUR_PRIVATE_API_KEY: \
    https://v3.recurly.com/sites/YOUR_SITE_ID/accounts
  ```
  </Tab>
  <Tab title="Ruby">
  ```ruby
  require 'recurly'

  # Initialize once; reuse the client instance for every API call
  client = Recurly::Client.new(api_key: ENV['RECURLY_PRIVATE_KEY'])
  ```
  </Tab>
  <Tab title="Node.js">
  ```javascript
  import { Client } from '@recurly/recurly-client'

  // Initialize once at application startup
  const client = new Client(process.env.RECURLY_PRIVATE_KEY)
  ```
  </Tab>
  <Tab title="Python">
  ```python
  import recurly

  # Initialize once; the client is thread-safe
  client = recurly.Client(api_key=os.environ['RECURLY_PRIVATE_KEY'])
  ```
  </Tab>
  <Tab title="Java">
  ```java
  import com.recurly.v3.Client;

  // Initialize with your private key; store as a singleton
  Client client = new Client(System.getenv("RECURLY_PRIVATE_KEY"));
  ```
  </Tab>
  <Tab title="C#">
  ```csharp
  using Recurly;

  // Initialize once; Client is thread-safe
  var client = new Client(Environment.GetEnvironmentVariable("RECURLY_PRIVATE_KEY"));
  ```
  </Tab>
  <Tab title="PHP">
  ```php
  $client = new \Recurly\Client(getenv('RECURLY_PRIVATE_KEY'));
  ```
  </Tab>
</Tabs>

## Install the SDK

Install the Recurly SDK for your language using its standard package manager.

<Tabs>
  <Tab title="Ruby">
  ```bash
  gem install recurly
  ```
  </Tab>
  <Tab title="Node.js">
  ```bash
  npm install @recurly/recurly-client
  ```
  </Tab>
  <Tab title="Python">
  ```bash
  pip install recurly
  ```
  </Tab>
  <Tab title="Java">
  ```xml
  <dependency>
    <groupId>com.recurly.v3</groupId>
    <artifactId>api-client</artifactId>
    <version>4.0.0</version>
  </dependency>
  ```
  </Tab>
  <Tab title="C#">
  ```bash
  dotnet add package Recurly
  ```
  </Tab>
  <Tab title="PHP">
  ```bash
  composer require recurly/recurly-client
  ```
  </Tab>
</Tabs>

## Create an account

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Create an account</h4><p>An Account is the starting point for every subscription. Create one with a unique <code>code</code> that maps to your internal customer ID — this is how you'll look up the account in future requests without storing Recurly's internal ID.</p></div>
  </div>
</div>

<Tabs>
  <Tab title="curl">
  ```bash
  curl -u YOUR_PRIVATE_API_KEY: \
    -H "Content-Type: application/json" \
    -X POST https://v3.recurly.com/sites/YOUR_SITE_ID/accounts \
    -d '{
      "code": "acct-jane-smith-001",
      "first_name": "Jane",
      "last_name": "Smith",
      "email": "jane.smith@example.com"
    }'
  ```
  </Tab>
  <Tab title="Ruby">
  ```ruby
  account = client.create_account(
    body: {
      code: 'acct-jane-smith-001',
      first_name: 'Jane',
      last_name: 'Smith',
      email: 'jane.smith@example.com'
    }
  )

  puts account.id # => "abc123def456"
  ```
  </Tab>
  <Tab title="Node.js">
  ```javascript
  const account = await client.createAccount({
    code: 'acct-jane-smith-001',
    firstName: 'Jane',
    lastName: 'Smith',
    email: 'jane.smith@example.com'
  })

  console.log(account.id) // => "abc123def456"
  ```
  </Tab>
  <Tab title="Python">
  ```python
  account = client.create_account(body={
      'code': 'acct-jane-smith-001',
      'first_name': 'Jane',
      'last_name': 'Smith',
      'email': 'jane.smith@example.com'
  })

  print(account.id)  # => "abc123def456"
  ```
  </Tab>
  <Tab title="Java">
  ```java
  AccountCreate body = new AccountCreate();
  body.setCode("acct-jane-smith-001");
  body.setFirstName("Jane");
  body.setLastName("Smith");
  body.setEmail("jane.smith@example.com");

  Account account = client.createAccount(body);
  System.out.println(account.getId()); // => "abc123def456"
  ```
  </Tab>
  <Tab title="C#">
  ```csharp
  var accountCreate = new AccountCreate
  {
      Code = "acct-jane-smith-001",
      FirstName = "Jane",
      LastName = "Smith",
      Email = "jane.smith@example.com"
  };

  var account = client.CreateAccount(accountCreate);
  Console.WriteLine(account.Id); // => "abc123def456"
  ```
  </Tab>
  <Tab title="PHP">
  ```php
  $account = $client->createAccount([
      'code' => 'acct-jane-smith-001',
      'first_name' => 'Jane',
      'last_name' => 'Smith',
      'email' => 'jane.smith@example.com'
  ]);

  echo $account->getId(); // => "abc123def456"
  ```
  </Tab>
</Tabs>

```json
// Response (truncated — key fields shown)
{
  "object": "account",
  "id": "abc123def456",
  "code": "acct-jane-smith-001",
  "state": "active",
  "first_name": "Jane",
  "last_name": "Smith",
  "email": "jane.smith@example.com",
  "created_at": "2025-03-01T10:00:00Z"
  // ... additional fields
}
```

<div class="rp-callout rp-callout-tip">
  <div><strong>Tip</strong>The <code>code</code> field is your own identifier — set it to your internal customer or user ID so you can look up accounts by your ID without storing Recurly's <code>id</code> separately.</div>
</div>

## Add a billing token

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Add a billing token</h4><p>Recurly never accepts raw card numbers through the API directly — card data must be tokenized first via Recurly.js or a mobile SDK in your frontend. The resulting token is a one-time-use string you attach to the account as a billing info record.</p></div>
  </div>
</div>

<div class="rp-callout rp-callout-important">
  <div><strong>Important</strong>Billing tokens expire after 20 minutes. Complete the account billing info update immediately after your frontend generates the token. If the token expires, the customer must re-enter their card details.</div>
</div>

<Tabs>
  <Tab title="curl">
  ```bash
  curl -u YOUR_PRIVATE_API_KEY: \
    -H "Content-Type: application/json" \
    -X POST https://v3.recurly.com/sites/YOUR_SITE_ID/accounts/YOUR_ACCOUNT_CODE/billing_info \
    -d '{
      "token_id": "tok_abc123xyz789"
    }'
  ```
  </Tab>
  <Tab title="Ruby">
  ```ruby
  billing_info = client.create_billing_info(
    account_id: 'acct-jane-smith-001',
    body: { token_id: 'tok_abc123xyz789' }
  )

  puts billing_info.card_type    # => "Visa"
  puts billing_info.last_four    # => "1111"
  ```
  </Tab>
  <Tab title="Node.js">
  ```javascript
  const billingInfo = await client.createBillingInfo('acct-jane-smith-001', {
    tokenId: 'tok_abc123xyz789'
  })

  console.log(billingInfo.cardType) // => "Visa"
  console.log(billingInfo.lastFour) // => "1111"
  ```
  </Tab>
  <Tab title="Python">
  ```python
  billing_info = client.create_billing_info(
      account_id='acct-jane-smith-001',
      body={'token_id': 'tok_abc123xyz789'}
  )

  print(billing_info.card_type)  # => "Visa"
  print(billing_info.last_four)  # => "1111"
  ```
  </Tab>
  <Tab title="Java">
  ```java
  BillingInfoCreate body = new BillingInfoCreate();
  body.setTokenId("tok_abc123xyz789");

  BillingInfo billingInfo = client.createBillingInfo("acct-jane-smith-001", body);
  System.out.println(billingInfo.getCardType()); // => "Visa"
  ```
  </Tab>
  <Tab title="C#">
  ```csharp
  var billingInfoCreate = new BillingInfoCreate { TokenId = "tok_abc123xyz789" };
  var billingInfo = client.CreateBillingInfo("acct-jane-smith-001", billingInfoCreate);
  Console.WriteLine(billingInfo.CardType); // => "Visa"
  ```
  </Tab>
  <Tab title="PHP">
  ```php
  $billingInfo = $client->createBillingInfo('acct-jane-smith-001', [
      'token_id' => 'tok_abc123xyz789'
  ]);

  echo $billingInfo->getCardType(); // => "Visa"
  ```
  </Tab>
</Tabs>

```json
// Response (truncated — key fields shown)
{
  "object": "billing_info",
  "account_id": "abc123def456",
  "card_type": "Visa",
  "last_four": "1111",
  "exp_month": 12,
  "exp_year": 2028,
  "updated_at": "2025-03-01T10:01:00Z"
  // ... additional fields
}
```

## Create a subscription

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Create a subscription</h4><p>With a billing-info-equipped account in place, create the subscription by pairing the account's <code>code</code> with a <code>plan_code</code>. Recurly immediately charges the card for the first billing period and returns the active Subscription object.</p></div>
  </div>
</div>

<Tabs>
  <Tab title="curl">
  ```bash
  curl -u YOUR_PRIVATE_API_KEY: \
    -H "Content-Type: application/json" \
    -X POST https://v3.recurly.com/sites/YOUR_SITE_ID/subscriptions \
    -d '{
      "plan_code": "plan-pro-monthly",
      "account": {
        "code": "acct-jane-smith-001"
      },
      "currency": "USD"
    }'
  ```
  </Tab>
  <Tab title="Ruby">
  ```ruby
  subscription = client.create_subscription(
    body: {
      plan_code: 'plan-pro-monthly',
      account: { code: 'acct-jane-smith-001' },
      currency: 'USD'
    }
  )

  puts subscription.uuid  # => "sub_xyz789abc123"
  puts subscription.state # => "active"
  ```
  </Tab>
  <Tab title="Node.js">
  ```javascript
  const subscription = await client.createSubscription({
    planCode: 'plan-pro-monthly',
    account: { code: 'acct-jane-smith-001' },
    currency: 'USD'
  })

  console.log(subscription.uuid)  // => "sub_xyz789abc123"
  console.log(subscription.state) // => "active"
  ```
  </Tab>
  <Tab title="Python">
  ```python
  subscription = client.create_subscription(body={
      'plan_code': 'plan-pro-monthly',
      'account': {'code': 'acct-jane-smith-001'},
      'currency': 'USD'
  })

  print(subscription.uuid)   # => "sub_xyz789abc123"
  print(subscription.state)  # => "active"
  ```
  </Tab>
  <Tab title="Java">
  ```java
  SubscriptionCreate body = new SubscriptionCreate();
  body.setPlanCode("plan-pro-monthly");
  body.setCurrency("USD");

  AccountCreate account = new AccountCreate();
  account.setCode("acct-jane-smith-001");
  body.setAccount(account);

  Subscription subscription = client.createSubscription(body);
  System.out.println(subscription.getUuid()); // => "sub_xyz789abc123"
  ```
  </Tab>
  <Tab title="C#">
  ```csharp
  var subscriptionCreate = new SubscriptionCreate
  {
      PlanCode = "plan-pro-monthly",
      Currency = "USD",
      Account = new AccountCreate { Code = "acct-jane-smith-001" }
  };

  var subscription = client.CreateSubscription(subscriptionCreate);
  Console.WriteLine(subscription.Uuid); // => "sub_xyz789abc123"
  ```
  </Tab>
  <Tab title="PHP">
  ```php
  $subscription = $client->createSubscription([
      'plan_code' => 'plan-pro-monthly',
      'account' => ['code' => 'acct-jane-smith-001'],
      'currency' => 'USD'
  ]);

  echo $subscription->getUuid();  // => "sub_xyz789abc123"
  echo $subscription->getState(); // => "active"
  ```
  </Tab>
</Tabs>

```json
// Response (truncated — key fields shown)
{
  "object": "subscription",
  "uuid": "sub_xyz789abc123",
  "state": "active",
  "plan": {
    "code": "plan-pro-monthly",
    "name": "Pro Monthly"
  },
  "quantity": 1,
  "unit_amount": 4900,
  "currency": "USD",
  "current_period_started_at": "2025-03-01T10:02:00Z",
  "current_period_ends_at": "2025-04-01T10:02:00Z"
  // ... additional fields
}
```

<div class="rp-callout rp-callout-note">
  <div><strong>Note</strong>The <code>unit_amount</code> field is returned in the currency's smallest unit — cents for USD. A value of <code>4900</code> means $49.00.</div>
</div>

## Change a subscription plan

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">4</div>
    <div><h4>Change a subscription plan</h4><p>To upgrade or downgrade a subscription, create a pending change on it. By default, the change takes effect at the next renewal. Set <code>timeframe</code> to <code>now</code> to apply the change immediately with proration.</p></div>
  </div>
</div>

<div class="rp-callout rp-callout-warning">
  <div><strong>Warning</strong>Setting <code>timeframe: now</code> immediately charges the prorated difference to the card on file. Confirm this is the intended behavior before using it in production — it cannot be undone without issuing a manual credit.</div>
</div>

<Tabs>
  <Tab title="curl">
  ```bash
  curl -u YOUR_PRIVATE_API_KEY: \
    -H "Content-Type: application/json" \
    -X POST https://v3.recurly.com/sites/YOUR_SITE_ID/subscriptions/YOUR_SUBSCRIPTION_ID/change \
    -d '{
      "plan_code": "plan-enterprise-monthly",
      "timeframe": "now"
    }'
  ```
  </Tab>
  <Tab title="Ruby">
  ```ruby
  change = client.create_subscription_change(
    subscription_id: 'sub_xyz789abc123',
    body: {
      plan_code: 'plan-enterprise-monthly',
      timeframe: 'now'
    }
  )

  puts change.plan.code # => "plan-enterprise-monthly"
  ```
  </Tab>
  <Tab title="Node.js">
  ```javascript
  const change = await client.createSubscriptionChange('sub_xyz789abc123', {
    planCode: 'plan-enterprise-monthly',
    timeframe: 'now'
  })

  console.log(change.plan.code) // => "plan-enterprise-monthly"
  ```
  </Tab>
  <Tab title="Python">
  ```python
  change = client.create_subscription_change(
      subscription_id='sub_xyz789abc123',
      body={
          'plan_code': 'plan-enterprise-monthly',
          'timeframe': 'now'
      }
  )

  print(change.plan.code)  # => "plan-enterprise-monthly"
  ```
  </Tab>
  <Tab title="Java">
  ```java
  SubscriptionChangeCreate body = new SubscriptionChangeCreate();
  body.setPlanCode("plan-enterprise-monthly");
  body.setTimeframe(SubscriptionChangeCreate.Timeframe.NOW);

  SubscriptionChange change = client.createSubscriptionChange("sub_xyz789abc123", body);
  System.out.println(change.getPlan().getCode());
  ```
  </Tab>
  <Tab title="C#">
  ```csharp
  var changeCreate = new SubscriptionChangeCreate
  {
      PlanCode = "plan-enterprise-monthly",
      Timeframe = SubscriptionChangeCreate.TimeframeEnum.Now
  };

  var change = client.CreateSubscriptionChange("sub_xyz789abc123", changeCreate);
  Console.WriteLine(change.Plan.Code);
  ```
  </Tab>
  <Tab title="PHP">
  ```php
  $change = $client->createSubscriptionChange('sub_xyz789abc123', [
      'plan_code' => 'plan-enterprise-monthly',
      'timeframe' => 'now'
  ]);

  echo $change->getPlan()->getCode();
  ```
  </Tab>
</Tabs>

```json
// Response (truncated — key fields shown)
{
  "object": "subscription_change",
  "subscription_id": "sub_xyz789abc123",
  "plan": {
    "code": "plan-enterprise-monthly",
    "name": "Enterprise Monthly"
  },
  "activate_at": "2025-03-01T10:05:00Z",
  "activated": true
  // ... additional fields
}
```

## Cancel a subscription

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">5</div>
    <div><h4>Cancel a subscription</h4><p>Canceling a subscription moves it to <code>canceled</code> state and stops it from renewing. The subscription remains active and accessible until the end of the current billing period, after which it transitions to <code>expired</code>.</p></div>
  </div>
</div>

<Tabs>
  <Tab title="curl">
  ```bash
  curl -u YOUR_PRIVATE_API_KEY: \
    -X DELETE https://v3.recurly.com/sites/YOUR_SITE_ID/subscriptions/YOUR_SUBSCRIPTION_ID
  ```
  </Tab>
  <Tab title="Ruby">
  ```ruby
  subscription = client.cancel_subscription('sub_xyz789abc123')

  puts subscription.state # => "canceled"
  ```
  </Tab>
  <Tab title="Node.js">
  ```javascript
  const subscription = await client.cancelSubscription('sub_xyz789abc123')

  console.log(subscription.state) // => "canceled"
  ```
  </Tab>
  <Tab title="Python">
  ```python
  subscription = client.cancel_subscription('sub_xyz789abc123')

  print(subscription.state)  # => "canceled"
  ```
  </Tab>
  <Tab title="Java">
  ```java
  Subscription subscription = client.cancelSubscription("sub_xyz789abc123");
  System.out.println(subscription.getState()); // => "canceled"
  ```
  </Tab>
  <Tab title="C#">
  ```csharp
  var subscription = client.CancelSubscription("sub_xyz789abc123");
  Console.WriteLine(subscription.State); // => "canceled"
  ```
  </Tab>
  <Tab title="PHP">
  ```php
  $subscription = $client->cancelSubscription('sub_xyz789abc123');
  echo $subscription->getState(); // => "canceled"
  ```
  </Tab>
</Tabs>

```json
// Response (truncated — key fields shown)
{
  "object": "subscription",
  "uuid": "sub_xyz789abc123",
  "state": "canceled",
  "canceled_at": "2025-03-01T10:10:00Z",
  "expires_at": "2025-04-01T10:02:00Z"
  // ... additional fields
}
```

<div class="rp-callout rp-callout-tip">
  <div><strong>Tip</strong>To reactivate a canceled subscription before its expiry date, send a <code>PUT</code> request to <code>/sites/YOUR_SITE_ID/subscriptions/YOUR_SUBSCRIPTION_ID/reactivate</code>. After the expiry date, a new subscription must be created.</div>
</div>

# Error handling and troubleshooting

## API error codes

<table class="rp-params">
  <tr class="rp-thead-row"><td>HTTP status</td><td>Error type</td><td>Meaning</td><td>What to do</td></tr>
  <tr><td><code>400</code></td><td><code>validation</code></td><td>One or more request parameters failed validation</td><td>Inspect the <code>params</code> array in the error body — each entry names the field and describes the failure</td></tr>
  <tr><td><code>401</code></td><td><code>unauthorized</code></td><td>API key is missing, invalid, or lacks permissions</td><td>Verify the key is correct, confirm it's not revoked, and check it has the required scopes in the Dashboard</td></tr>
  <tr><td><code>403</code></td><td><code>forbidden</code></td><td>The key doesn't have access to the requested site or resource</td><td>Confirm the site ID in the URL matches the site the key belongs to</td></tr>
  <tr><td><code>404</code></td><td><code>not_found</code></td><td>The resource doesn't exist</td><td>Double-check the ID or code in the URL path; resources are permanently deleted and won't be found after deletion</td></tr>
  <tr><td><code>422</code></td><td><code>transaction_error</code></td><td>Payment was declined or couldn't be processed</td><td>Check the <code>transaction_error</code> object — the <code>merchant_message</code> field contains the gateway's decline reason</td></tr>
  <tr><td><code>422</code></td><td><code>immutable_subscription</code></td><td>A change was attempted on a subscription in a non-modifiable state</td><td>Check the subscription's <code>state</code> — changes can't be made to <code>expired</code> or <code>failed</code> subscriptions</td></tr>
  <tr><td><code>429</code></td><td><code>rate_limited</code></td><td>Requests exceeded 1,400 per minute for this site</td><td>Implement exponential backoff with jitter; the <code>Retry-After</code> response header tells you when to resume</td></tr>
</table>

## Common issues

<Accordion title="Why is the subscription state 'future' instead of 'active'?">
A subscription enters `future` state when its `starts_at` date is set to a future timestamp. This is used for scheduling subscriptions that begin on a future date, such as at the end of a trial you're managing externally. If you didn't intend this, check whether `starts_at` was included in your creation request — omitting it defaults to immediate activation.
</Accordion>

<Accordion title="Why did creating a subscription return a 422 transaction_error?">
The card was declined at the gateway. Check the `transaction_error` object in the response — specifically the `merchant_message` field, which contains the raw decline reason from the payment gateway. Common causes include an expired card, insufficient funds, or the card issuer blocking the transaction. Use Recurly's test card numbers in the sandbox to simulate specific decline scenarios before going live.
</Accordion>

<Accordion title="Can I create an account and subscription in a single API call?">
Yes. The `POST /subscriptions` endpoint accepts a nested `account` object. If the `code` in that object matches an existing account, Recurly links the subscription to it. If the code is new, Recurly creates the account and the subscription atomically. You can also nest `billing_info` inside the `account` object to attach a payment token in the same request.
</Accordion>

<Accordion title="Why is my plan change not reflected on the current invoice?">
Plan changes with `timeframe: renewal` (the default) don't affect the current billing period — they queue for the next renewal. Only `timeframe: now` applies immediately with proration. Check the subscription's `pending_change` object to confirm the change is queued and will activate on the next renewal date shown in `current_period_ends_at`.
</Accordion>

# Webhooks

Recurly sends webhook notifications to your server whenever key subscription events occur — renewals, cancellations, payment failures, and more. Because these events happen asynchronously (often minutes or hours after your API call), webhooks are how your backend stays in sync with Recurly's state rather than polling the API.

<table class="rp-params">
  <tr class="rp-thead-row"><td>Event</td><td>When it fires</td></tr>
  <tr><td><code>new_subscription_notification</code></td><td>A new subscription is created and activated</td></tr>
  <tr><td><code>updated_subscription_notification</code></td><td>A subscription is modified — plan change, quantity change, or reactivation</td></tr>
  <tr><td><code>canceled_subscription_notification</code></td><td>A subscription is canceled (still active until period end)</td></tr>
  <tr><td><code>expired_subscription_notification</code></td><td>A canceled subscription reaches its expiry date and becomes inactive</td></tr>
  <tr><td><code>renewed_subscription_notification</code></td><td>A subscription successfully renews at the end of a billing period</td></tr>
  <tr><td><code>failed_renewal_notification</code></td><td>A renewal charge fails — dunning begins if configured</td></tr>
  <tr><td><code>successful_payment_notification</code></td><td>Any payment transaction succeeds</td></tr>
  <tr><td><code>failed_payment_notification</code></td><td>Any payment transaction is declined</td></tr>
</table>

<div class="rp-callout rp-callout-tip">
  <div><strong>Tip</strong>Configure your webhook endpoint in the Recurly Admin Dashboard under <strong>Integrations > Webhooks</strong>. Recurly sends an HTTP POST to your endpoint with an XML payload and expects a <code>2xx</code> response within 5 seconds — return immediately and process asynchronously if your handler is slow.</div>
</div>

<a class="rp-btn rp-btn-primary" href="/docs/webhooks" target="_blank">Webhooks reference →</a>

# Testing your integration

## Sandbox environment

Your Recurly test site is a fully isolated environment — transactions never move real money and all data is separate from your live site. Use your **test site API key** (visible at the top of your Recurly test site's Dashboard) for all development and QA work.

<table class="rp-params">
  <tr class="rp-thead-row"><td>Test card number</td><td>Behavior</td></tr>
  <tr><td><code>4111 1111 1111 1111</code></td><td>Successful charge — Visa</td></tr>
  <tr><td><code>5105 1051 0510 5100</code></td><td>Successful charge — Mastercard</td></tr>
  <tr><td><code>4000 0000 0000 0002</code></td><td>Declined — generic decline</td></tr>
  <tr><td><code>4000 0000 0000 0341</code></td><td>Declined — expired card</td></tr>
  <tr><td><code>4000 0000 0000 9995</code></td><td>Declined — insufficient funds</td></tr>
</table>

Use `01` for the expiry month, any future year, and any three-digit CVV for all test cards.

<div class="rp-callout rp-callout-tip">
  <div><strong>Tip</strong>Use the <strong>Time Machine</strong> feature in the Recurly Admin Dashboard to fast-forward subscription billing periods, simulate renewals, trigger dunning runs, and test expiry behavior — without waiting for real time to pass.</div>
</div>

## Verifying the integration

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Confirm the account exists in the Dashboard</h4><p>Navigate to <strong>Accounts</strong> in the Recurly Admin Dashboard and search for the <code>account_code</code> you used. You should see the account with the billing info card and the active subscription listed.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Inspect the invoice and transaction</h4><p>Open the account and check the <strong>Invoices</strong> tab. The first invoice for the subscription should show a <code>collected</code> state, with a linked Transaction showing <code>success</code>.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Verify webhook delivery</h4><p>In the Dashboard, go to <strong>Integrations > Webhooks > Webhook logs</strong>. Confirm that <code>new_subscription_notification</code> was sent to your endpoint and received a <code>2xx</code> response. If it shows failed, check your endpoint logs for the received payload.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">4</div>
    <div><h4>Test a renewal with Time Machine</h4><p>Use Time Machine to advance the subscription past its <code>current_period_ends_at</code> date. A new invoice should appear with state <code>collected</code> and a <code>renewed_subscription_notification</code> webhook should fire to your endpoint.</p></div>
  </div>
</div>

# What's next

<Cards>
  <Card title="API reference" href="/docs/api">Complete endpoint documentation for every Recurly resource — Accounts, Subscriptions, Plans, Invoices, Transactions, and more.</Card>
  <Card title="Recurly.js" href="/docs/recurly-js">Tokenize card data securely in the browser so raw card numbers never touch your server.</Card>
  <Card title="Webhooks" href="/docs/webhooks">Full reference for every webhook event type, payload schemas, signature verification, and retry behavior.</Card>
  <Card title="Dunning and payment recovery" href="/docs/dunning">Configure automated retry schedules and customer communications for failed payments.</Card>
  <Card title="Add-ons and usage billing" href="/docs/add-ons">Charge for seats, usage, or optional features on top of a base subscription price.</Card>
</Cards>