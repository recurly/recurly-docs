---
title: Getting started v2021-02-25
excerpt: >-
  Understand API versioning, error handling, pagination, rate limits, and best
  practices for integrating with the Recurly Subscriptions API.
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

This guide walks you through the essential concepts you'll need to work with the Recurly Subscriptions API. We'll cover versioning, error handling, pagination, and rate limits — everything you need to build a stable integration.

## API versioning

The Recurly Subscriptions API uses date-based versioning to give you stability while we continue improving the platform. This means your code won't break when we ship new features.

### Specify a version in every request

Every API request must include an `Accept` header that specifies the API version you're targeting. Without it, your request will fail.

```
Accept: application/vnd.recurly.v2021-02-25
Accept: application/vnd.recurly.v2021-02-25+json
```

All responses include a `Recurly-Version` header that confirms which version processed your request:

```
Recurly-Version: recurly.v2021-02-25
```

### Version format

Versions follow a `YYYY-MM-DD` format (for example, `v2021-02-25`), which reflects the approximate date the changes were released.

### Available versions and client library compatibility

If you're using one of Recurly's official client libraries, make sure your library version aligns with your API version:

| API Version | Client Library Version |
| ----------- | ---------------------- |
| v2021-02-25 | 4.x                    |
| v2019-10-10 | 3.x                    |

**Client libraries by language:**

* [Node.js](https://github.com/recurly/recurly-client-node/releases)
* [Python](https://github.com/recurly/recurly-client-python/releases)
* [.NET](https://github.com/recurly/recurly-client-dotnet/releases)
* [Ruby](https://github.com/recurly/recurly-client-ruby/releases)
* [Java](https://github.com/recurly/recurly-client-java/releases)
* [PHP](https://github.com/recurly/recurly-client-php/releases)
* [Go](https://github.com/recurly/recurly-client-go/releases)

We recommend updating to the latest version of both the API and your client library regularly. Later versions are more performant and include important bug fixes. See the [changelog](/docs/api-changelog) for a complete list of improvements in the latest version.

### Using the latest version

If you're willing to accept the risk of breaking changes and want to automatically use the newest API version, you can specify `latest` instead of a specific date:

```
Accept: application/vnd.recurly.latest
Accept: application/vnd.recurly.latest+json
```

### Deprecated versions

When we deprecate an API version, response headers will tell you it's nearing retirement:

```
Recurly-Deprecated: TRUE
Recurly-Sunset-Date: 2017-06-01T00:00:00+00:00
```

The sunset date is an ISO 8601 formatted timestamp. After that date, the version will no longer be accessible.

### Unsupported versions

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

## Error messages

API errors are designed for developers. If you're displaying these messages to end users, consider translating them into language your users will understand. For example, a technical error message like "Invalid account code format" might be better displayed as "We couldn't find that account."

For detailed information on transaction-specific error codes, see [transaction error codes](https://recurly.com/developers/pages/api-transaction-errors.html).

## Pagination

All GET listing endpoints return results in pages to keep responses fast. Here's how to work with paginated data.

### Response format

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

* `object`: Always `"list"` for listing endpoints.
* `has_more`: `true` if there are more pages; `false` if you've reached the last page.
* `next`: A URL pointing to the next page of results.
* `data`: An array of objects for the current page.

### Walking through all pages

To retrieve every record, simply follow the `next` URL until `has_more` is `false`:

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

### Query parameters

Most listing endpoints accept parameters to filter and sort results:

* `ids`: A comma-separated list of specific IDs to fetch.
* `limit`: The number of records to return per page.
* `order`: The sort order (`asc` for ascending, `desc` for descending).
* `sort`: The field to sort by (often a date field).
* `begin_time`: ISO 8601 datetime to start filtering from.
* `end_time`: ISO 8601 datetime to stop filtering at.

Example:

```
GET /v2021-02-25/accounts?limit=100&sort=updated_at&order=desc&begin_time=2024-01-01T00:00:00Z
```

### Counting total records with HEAD

Every GET listing endpoint also supports the `HEAD` HTTP method. This gives you a count of total records matching your filters without downloading the actual data:

```
HEAD /v2021-02-25/accounts?begin_time=2024-01-01T00:00:00Z
```

The response includes a `Recurly-Total-Records` header with the total count.

## Rate limits

To keep our API fast and reliable for all customers, we apply rate limits to all requests. Your limit depends on whether you're using a sandbox or production account.

### Rate limit tiers

* **Sandbox sites**: 400 requests per minute. All requests count.
* **Production sites**: 1,000 requests per minute. Only GET requests count; POST, PUT, and DELETE requests don't count against your limit.

This means in production, you can create new subscriptions, update accounts, and delete resources without worrying about rate limits — only reads are throttled.

### How limits are calculated

The rate limit is measured over a rolling five-minute window. For example, a production site could make 4,000 GET requests in one minute without hitting the limit, as long as it made fewer than 1,000 requests during the preceding four minutes.

### Exceeding your limit

If you exceed your rate limit, the API returns a `429 Too Many Requests` status code. If your business needs a higher limit, reach out to [support@recurly.com](mailto:support@recurly.com).

### Monitoring your usage

Three response headers help you track your rate limit status:

* `X-RateLimit-Limit`: Your rate limit (requests per minute).
* `X-RateLimit-Remaining`: How many requests you have left before the window resets.
* `X-RateLimit-Reset`: A Unix timestamp indicating when your request count will reset.

## What's next

* <Anchor label="Browse the complete API reference" target="_blank" href="recurly-subscriptions/reference">Browse the complete API reference</Anchor>
* [View the API changelog](recurly-subscriptions/changelog)
* [Explore our client libraries](/docs/client-libraries)

# FAQs

**Do I have to specify an API version?**

Yes. Every request must include an `Accept` header with a specific API version. If you don't, the API will reject your request with a 406 error.

**How often are new API versions released?**

We release new versions as we add significant features or make breaking changes. Each version is supported for an extended period before sunset, giving you time to migrate.

**Can I use the latest version automatically?**

You can specify `latest` in your `Accept` header to always use the newest version. However, this means your code could break if we introduce breaking changes — use this only if you're comfortable monitoring for API updates.

**What happens if I request an old API version?**

Once an API version reaches its sunset date, requests to that version will return a 406 error with a list of supported versions. We give plenty of warning before sunsetting a version.

**Do POST, PUT, and DELETE requests count against my rate limit in production?**

No. In production, only GET requests are rate-limited. Write operations (creating, updating, or deleting data) don't count toward your limit.

**I keep hitting the rate limit. Can I get a higher limit?**

Yes, contact [support@recurly.com](mailto:support@recurly.com) or your account manager to discuss higher limits. We can also help you optimize your integration to use fewer requests.