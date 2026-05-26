---
title: Getting started v2021-02-25
excerpt: >-
  A reference guide to the Recurly Subscriptions API fundamentals, covering
  versioning, error handling, pagination, and rate limits.
deprecated: false
hidden: false
metadata:
  robots: index
---
<div class="rp-page">
  <div class="rp-overview">
    This guide covers the essential concepts you'll need to build a stable integration with the Recurly Subscriptions API — versioning, error handling, pagination, and rate limits.
  </div>

  <div class="rp-toc">
    <a class="rp-toc-pill" href="#api-versioning"><span class="rp-toc-num">1</span>API versioning</a>
    <a class="rp-toc-pill" href="#error-messages"><span class="rp-toc-num">2</span>Error messages</a>
    <a class="rp-toc-pill" href="#pagination"><span class="rp-toc-num">3</span>Pagination</a>
    <a class="rp-toc-pill" href="#rate-limits"><span class="rp-toc-num">4</span>Rate limits</a>
    <a class="rp-toc-pill" href="#whats-next"><span class="rp-toc-num">5</span>What's next</a>
    <a class="rp-toc-pill" href="#faqs"><span class="rp-toc-num">6</span>FAQs</a>
  </div>
</div>

# API versioning

The Recurly Subscriptions API uses date-based versioning to give you stability while we continue improving the platform. Your code won't break when we ship new features.

## Specify a version in every request

Every API request must include an `Accept` header specifying the API version you're targeting.

<div class="rp-callout rp-callout-important">
  <div><strong><i class="fa-solid fa-circle-exclamation" aria-hidden="true" /> Important</strong>Every request must include an <code>Accept</code> header with a valid API version. Without it, your request will fail.</div>
</div>

```
Accept: application/vnd.recurly.v2021-02-25
Accept: application/vnd.recurly.v2021-02-25+json
```

All responses include a `Recurly-Version` header confirming which version processed your request:

```
Recurly-Version: recurly.v2021-02-25
```

## Version format

Versions follow a `YYYY-MM-DD` format (for example, `v2021-02-25`), which reflects the approximate date the changes were released.

## Available versions and client library compatibility

If you're using one of Recurly's official client libraries, make sure your library version aligns with your API version:

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>API version</td><td>Client library version</td></tr>
  <tr><td>v2021-02-25</td><td>4.x</td></tr>
  <tr><td>v2019-10-10</td><td>3.x</td></tr>
</table>

We recommend keeping both your API version and client library up to date. Later versions are more performant and include important bug fixes. See the <Anchor label="changelog" target="_blank" href="https://docs.recurly.com/recurly-subscriptions/v2021-02-25/reference">changelog</Anchor> for a complete list of improvements.

**Client libraries by language:**

<ul class="rp-list">
  <li><a href="https://github.com/recurly/recurly-client-node/releases" target="_blank">Node.js</a></li>
  <li><a href="https://github.com/recurly/recurly-client-python/releases" target="_blank">Python</a></li>
  <li><a href="https://github.com/recurly/recurly-client-dotnet/releases" target="_blank">.NET</a></li>
  <li><a href="https://github.com/recurly/recurly-client-ruby/releases" target="_blank">Ruby</a></li>
  <li><a href="https://github.com/recurly/recurly-client-java/releases" target="_blank">Java</a></li>
  <li><a href="https://github.com/recurly/recurly-client-php/releases" target="_blank">PHP</a></li>
  <li><a href="https://github.com/recurly/recurly-client-go/releases" target="_blank">Go</a></li>
</ul>

## Using the latest version

If you want to automatically use the newest API version and are comfortable accepting the risk of breaking changes, specify `latest` instead of a specific date:

```
Accept: application/vnd.recurly.latest
Accept: application/vnd.recurly.latest+json
```

<div class="rp-callout rp-callout-warning">
  <div><strong><i class="fa-solid fa-triangle-exclamation" aria-hidden="true" /> Warning</strong>Using <code>latest</code> means your integration may break without notice if we introduce breaking changes. Use a pinned version in production.</div>
</div>

## Deprecated versions

When we deprecate an API version, response headers will tell you it's nearing retirement:

```
Recurly-Deprecated: TRUE
Recurly-Sunset-Date: 2017-06-01T00:00:00+00:00
```

The sunset date is an ISO 8601 formatted timestamp. After that date, the version will no longer be accessible.

## Unsupported versions

Requests to unsupported API versions return a `406` status code with a list of acceptable versions:

```json
{
  "error": {
    "type": "invalid_api_version",
    "message": "That accept header isn't in the format we use to specify an API version. Try one of these instead:",
    "acceptable_accept_headers": [
      "application/vnd.recurly.v2021-02-25",
      "application/vnd.recurly.v2019-10-10"
    ]
  }
}
```

# Error messages

API errors are designed for developers. If you're displaying these messages to end users, translate them into language your users will understand — for example, a technical message like "Invalid account code format" might be better displayed as "We couldn't find that account."

For detailed information on transaction-specific error codes, see our <Anchor label="documentation" target="_blank" href="https://docs.recurly.com/recurly-subscriptions/docs/api-transaction-errors">documentation</Anchor>.

# Pagination

All GET listing endpoints return results in pages to keep responses fast.

## Response format

Every listing endpoint returns the same response structure:

```json
{
  "object": "list",
  "has_more": true,
  "next": "https://api.recurly.com/v2021-02-25/accounts?limit=200&cursor=1234",
  "data": [
    { "id": "account1", "code": "acme-corp" },
    { "id": "account2", "code": "widgets-inc" }
  ]
}
```

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Field</td><td>Description</td></tr>
  <tr><td><code>object</code></td><td>Always <code>"list"</code> for listing endpoints.</td></tr>
  <tr><td><code>has\_more</code></td><td><code>true</code> if there are more pages; <code>false</code> if you've reached the last page.</td></tr>
  <tr><td><code>next</code></td><td>A URL pointing to the next page of results.</td></tr>
  <tr><td><code>data</code></td><td>An array of objects for the current page.</td></tr>
</table>

## Walking through all pages

To retrieve every record, follow the `next` URL until `has_more` is `false`:

```javascript
let allRecords = [];
let nextUrl = 'https://api.recurly.com/v2021-02-25/accounts';

while (nextUrl) {
  const response = await fetch(nextUrl, {
    headers: { 'Accept': 'application/vnd.recurly.v2021-02-25' }
  });
  const page = await response.json();
  allRecords = allRecords.concat(page.data);
  nextUrl = page.has_more ? page.next : null;
}
```

## Query parameters

Most listing endpoints accept parameters to filter and sort results:

<ul class="rp-list">
  <li><code>ids</code> — A comma-separated list of specific IDs to fetch.</li>
  <li><code>limit</code> — The number of records to return per page.</li>
  <li><code>order</code> — The sort order (<code>asc</code> for ascending, <code>desc</code> for descending).</li>
  <li><code>sort</code> — The field to sort by (often a date field).</li>
  <li><code>begin\_time</code> — ISO 8601 datetime to start filtering from.</li>
  <li><code>end\_time</code> — ISO 8601 datetime to stop filtering at.</li>
</ul>

```
GET /v2021-02-25/accounts?limit=100&sort=updated_at&order=desc&begin_time=2024-01-01T00:00:00Z
```

## Counting total records with HEAD

Every GET listing endpoint also supports the `HEAD` HTTP method, which returns a count of matching records without downloading the actual data:

```
HEAD /v2021-02-25/accounts?begin_time=2024-01-01T00:00:00Z
```

The response includes a `Recurly-Total-Records` header with the total count.

# Rate limits

To keep the API fast and reliable for all customers, we apply rate limits to all requests. Your limit depends on whether you're using a sandbox or production account.

## Rate limit tiers

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Account type</td><td>Limit</td><td>What counts</td></tr>
  <tr><td>Sandbox</td><td>400 requests per minute</td><td>All requests</td></tr>
  <tr><td>Production</td><td>1,000 requests per minute</td><td>GET requests only — POST, PUT, and DELETE don't count</td></tr>
</table>

In production, you can create subscriptions, update accounts, and delete resources without worrying about rate limits — only reads are throttled.

## How limits are calculated

The rate limit is measured over a rolling five-minute window. A production site could make 4,000 GET requests in one minute without hitting the limit, as long as it made fewer than 1,000 requests during the preceding four minutes.

## Exceeding your limit

If you exceed your rate limit, the API returns a `429 Too Many Requests` status code. If your business needs a higher limit, reach out to <a href="mailto:support@recurly.com" target="_blank">[support@recurly.com](mailto:support@recurly.com)</a>.

## Monitoring your usage

Three response headers help you track your rate limit status:

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Header</td><td>Description</td></tr>
  <tr><td><code>X-RateLimit-Limit</code></td><td>Your rate limit (requests per minute).</td></tr>
  <tr><td><code>X-RateLimit-Remaining</code></td><td>How many requests you have left before the window resets.</td></tr>
  <tr><td><code>X-RateLimit-Reset</code></td><td>A Unix timestamp indicating when your request count resets.</td></tr>
</table>

# What's next

* <a href="recurly-subscriptions/reference" target="_blank">Browse the complete API reference</a>
* <a href="recurly-subscriptions/changelog" target="_blank">View the API changelog</a>
* <a href="https://docs.recurly.com/recurly-subscriptions/v2021-02-25/reference/client-libraries" target="_blank">Explore our client libraries</a>

# FAQs

<Accordion title="Do I have to specify an API version?">
  Yes. Every request must include an `Accept` header with a specific API version. Without it, the API will reject your request with a 406 error.
</Accordion>

<Accordion title="How often are new API versions released?">
  We release new versions as we add significant features or make breaking changes. Each version is supported for an extended period before sunset, giving you time to migrate.
</Accordion>

<Accordion title="Can I use the latest version automatically?">
  You can specify `latest` in your `Accept` header to always use the newest version. Keep in mind that your code could break if we introduce breaking changes — use this only if you're comfortable monitoring for API updates.
</Accordion>

<Accordion title="What happens if I request an old API version?">
  Once an API version reaches its sunset date, requests to that version return a 406 error with a list of supported versions. We give plenty of warning before sunsetting a version.
</Accordion>

<Accordion title="Do POST, PUT, and DELETE requests count against my rate limit in production?">
  No. In production, only GET requests are rate-limited. Write operations — creating, updating, or deleting data — don't count toward your limit.
</Accordion>

<Accordion title="I keep hitting the rate limit. Can I get a higher limit?">
  Yes, contact <a href="mailto:support@recurly.com" target="_blank">[support@recurly.com](mailto:support@recurly.com)</a> or your account manager to discuss higher limits. We can also help you optimize your integration to use fewer requests.
</Accordion>
