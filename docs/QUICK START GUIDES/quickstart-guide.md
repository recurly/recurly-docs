---
title: Quickstart Guide
excerpt: >-
  This guide is intended to get you up and running with the Recurly API as
  quickly as possible using one of the official Recurly client libraries.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Quickstart Guide

This guide is intended to get you up and running with the Recurly API as quickly as possible using one of the official Recurly client libraries.

**Estimated completion time:** 5 minutes

***

## Step 1: Authentication Keys

Recurly authenticates your API requests using your private API key. You can generate and retrieve private API keys in the [Recurly Admin Dashboard](https://app.recurly.com/go/integrations/api_keys).

***

## Step 2: Choose a Client Library

Recurly offers a number of client libraries to integrate with the API. We suggest using one of these official clients as it will make support, onboarding, and security much easier.

### Ruby

Check out the [Ruby API docs](https://www.rubydoc.info/github/recurly/recurly-client-ruby/), or see the source on [GitHub](https://github.com/recurly/recurly-client-ruby).

Add to your `Gemfile`:

```ruby
gem 'recurly', '~> 4.0'
```

Or install from the command line:

```bash
gem install recurly
```

***

### Node.js

Check out the [Js API docs](https://recurly.github.io/recurly-client-node/), or see the source on [GitHub](https://github.com/recurly/recurly-client-node).

Install via [npm](https://www.npmjs.com/package/recurly):

```bash
npm install recurly --save
```

Or add directly to your dependencies in `package.json`:

```json
{
  "recurly": "^4.0.0"
}
```

***

### Python

Check out the [Python API docs](https://recurly-client-python.readthedocs.io/en/latest/), or see the source on [GitHub](https://github.com/recurly/recurly-client-python/tree/4_0_0).

Add to your `requirements.txt`:

```
recurly~=4.0
```

Or install via pip:

```bash
pip install --upgrade recurly
```

***

### Java

See the source on [GitHub](https://github.com/recurly/recurly-client-java) and release details on [Maven Central](https://search.maven.org/artifact/com.recurly.v3/api-client/4.4.0/jar).

As a Maven dependency:

```xml
<dependency>
  <groupId>com.recurly.v3</groupId>
  <artifactId>api-client</artifactId>
  <version>4.0.0</version>
</dependency>
```

In Gradle:

```bash
implementation 'com.recurly.v3:api-client:4.4.0'
```

***

### Dotnet (C#)

See the source on [GitHub](https://github.com/recurly/recurly-client-dotnet).

Install via the `dotnet` tool:

```bash
dotnet add package Recurly --version 4.*
```

Or manually insert into your `.csproj` file:

```xml
<ItemGroup>
  <PackageReference Include="Recurly" Version="4.*" />
  <!-- ... -->
</ItemGroup>
```

***

### PHP

See the source on [GitHub](https://github.com/recurly/recurly-client-php).

Install via the `composer` tool:

```bash
composer install recurly/recurly-client
```

Or manually add to your `composer.json`:

```json
{
    "require": {
        "recurly/recurly-client": "^4"
    }
}
```

***

## Step 3: Create a Client Instance

Your integration starts by creating an instance of the Client class. The client represents a connection to Recurly's API. Every operation in the API exists as a method on this object. Creating a client only requires the private API key.

### Ruby

```ruby
require 'recurly'
client = Recurly::Client.new(
  api_key: '<your private api key>'
)
```

***

### Node.js

```js
const recurly = require('recurly');
const client = new recurly.Client('<your private api key>');
```

***

### Python

```python
import recurly
client = recurly.Client('<your private api key>')
```

***

### Java

```java
import com.recurly.v3.Client;

final Client client = new Client("<your private api key>");
```

***

### Dotnet (C#)

```csharp
using Recurly;

var client = new Recurly.Client("<your private api key>");
```

***

### PHP

```php
$client = new \Recurly\Client("<your private api key>");
```

***

## Step 4: Create a Plan

A plan tells Recurly how often and how much to charge your customers. Plans can be created with free trials, optional products (called add-ons), setup fees, and more.

Plans are typically created in the [admin interface](https://app.recurly.com/go/plans/new) if you only have a few offerings, but you can also create as many plans as you need through the [API](/developers/api/latest/index.html#operation/create_plan).

Let's create a hypothetical plan for a monthly coffee delivery product. The customer will be charged $100 a month. It will use the unique identifier `coffee-monthly` to refer to this plan.

### Ruby

```ruby
plan_create = {
  code: "coffee-monthly",
  name: "Monthly Coffee Subscription",
  currencies: [
    {
      currency: "USD",
      unit_amount: 100
    }
  ]
}
plan = client.create_plan(body: plan_create)
puts "Created Plan #{plan}"
```

***

### Node.js

```js
const planCreate = {
  code: 'coffee-monthly',
  name: 'Monthly Coffee Subscription',
  currencies: [
    {
      currency: 'USD',
      unitAmount: 100
    }
  ]
};
const plan = await client.createPlan(planCreate);
console.log('Created Plan:', plan.code);
```

***

### Python

```python
plan_create = {
    "code": 'coffee-monthly',
    "name": "Monthly Coffee Subscription",
    "currencies": [{
        "currency": "USD",
        "unit_amount": 100
    }],
}
plan = client.create_plan(plan_create)
print("Created Plan %s" % plan)
```

***

### Java

```java
import com.recurly.v3.requests.PlanCreate;
import com.recurly.v3.requests.PlanPricing;
import com.recurly.v3.resources.Plan;
import java.util.ArrayList;
import java.util.List;

PlanCreate planCreate = new PlanCreate();
planCreate.setCode("coffee-monthly");
planCreate.setName("Monthly Coffee Subscription");

List<PlanPricing> currencies = new ArrayList<>();
PlanPricing planPrice = new PlanPricing();
planPrice.setCurrency("USD");
planPrice.setUnitAmount(100.0f);
currencies.add(planPrice);
planCreate.setCurrencies(currencies);

Plan plan = client.createPlan(planCreate);
System.out.println("Created Plan " + plan.getCode());
```

***

### Dotnet (C#)

```csharp
using Recurly.Resources;
using System.Collections.Generic;

var planReq = new PlanCreate()
{
    Code = "coffee-monthly",
    Name = "Monthly Coffee Subscription",
    Currencies = new List<PlanPricing>() {
        new PlanPricing() {
            Currency = "USD",
            UnitAmount = 100
        }
    }
};
Plan plan = client.CreatePlan(planReq);
Console.WriteLine($"Created plan {plan.Code}");
```

***

### PHP

```php
$plan_create = [
    "name" => "Monthly Coffee Subscription",
    "code" => "coffee-monthly",
    "currencies" => [
        [
            "currency" => "USD",
            "unit_amount" => 100
        ]
    ]
];

$plan = $client->createPlan($plan_create);

echo "Created Plan:\n";
var_dump($plan);
```

***

## Step 5: Verify and Finish

That's it! You can now view your newly created plan in the [admin interface](https://app.recurly.com/go/plans).

***

## Next Steps

With a newly created plan at your disposal, it's time to start creating customer accounts, billing info, subscriptions, and/or one-time payments using the [Purchases endpoint](/developers/guides/purchases.html).