---
title: 'Overview: Webhooks'
excerpt: >-
  Receive real-time notifications from Recurly—learn how to configure, secure,
  and consume webhook events to keep your internal systems and partners in sync.
deprecated: false
hidden: false
metadata:
  robots: index
---
# Webhooks

Webhooks let you notify your internal systems and partner applications whenever something important happens in Recurly. Treat them as **alerts**—not as the sole source of truth—then follow the <Anchor label="Best Practices" target="_blank" href="best-practices">Best Practices</Anchor> section to act on those events safely.

Recurly can post notifications to any publicly reachable server. When a qualifying event occurs (for example, a new account is created), Recurly sends a webhook to each endpoint you configure—up to **10 endpoints** per site. Every endpoint receives the notifications for the [lifecycle events](https://docs.recurly.com/recurly-subscriptions/docs/lifecycle-events#/) it is subscribed to.

A notification counts as **delivered** only when Recurly gets a timely, successful response:

* The endpoint must listen on port **80 (HTTP)** or **443 (HTTPS)**—other ports are not supported.
* The endpoint must reply within **5 seconds**.
* The response must be an HTTP **2XX** status (200, 201, 204, etc.). Recurly does not follow redirects, and non-2XX responses are treated as failures.

# Sandbox vs Production

Recurly sends sandbox and production webhooks from different services, so that the high level of testing done in sandbox mode does not impact production data.

In times of high sandbox testing volume, sandbox webhook deliverability may be delayed by up to **48 hours**.

Recurly may auto-pause sandbox webhook endpoints that consistently return a high number of deliverability errors in a short window of time.

# Best practices

<br />

Webhooks are **notifications**, not commands. Use them to discover that something **might** have changed in Recurly, then confirm the authoritative state with the Recurly API before you update your own systems.

### Prerequisites and limitations

* Your endpoint already meets the connectivity rules outlined in **Webhooks** (publicly reachable on port 80/443 and capable of replying with a **2XX** within 5 seconds).
* Recurly can retry or resend a webhook, so duplicate deliveries are expected.
* Retries may arrive **out of order**—your logic must handle older events that follow newer ones.

# Key details

Webhooks are not actionable on their own and should **not** be used for critical functions such as provisioning accounts. The API response from the originating action (e.g., signup, one-time purchase) should provision the account and store the resulting state in your own database. Treat that local state as correct **unless** a webhook indicates a change.

When a webhook arrives, use it as a trigger to:

1. **Call the Recurly API** to confirm the current status of the resource.
2. **Compare** the payload to your local record.
3. **Update** your database only if the API shows a real change.

Recurly webhooks may be retried or sent multiple times if delivery is considered failed. Your endpoint **must**:

* Accept the same notification more than once.
* Tolerate events that arrive in the wrong order.

<Cards columns={1}>
  <Card title="Example" icon="fa-info-circle">
    For example, an account can close and we will send a notification for this. If delivery fails, the notification will be sent again later. In the meantime, the account could reopen (triggering another push notification). If your endpoint begins working again, it may receive the closed-account notification **after** the account was reopened. Make sure that, if your application takes action on closed accounts, it verifies the account is still closed by issuing an API request.
  </Card>
</Cards>

# Configuration and security

This section covers how Recurly handles webhook retries, how to authenticate incoming webhook requests, and ways to secure your endpoint.

### Prerequisites and limitations

* Configure HTTP Basic Authentication if you wish to verify incoming requests.
* Restrict access to Recurly’s IP ranges (see IP Whitelisting link below).
* Web-application firewalls (e.g., ModSecurity) may block webhook traffic unless adjusted.

# Key details

If Recurly fails to deliver a webhook, it will retry it (see [Automatic Retries](https://docs.recurly.com/v1.3/docs/automatic-retries#/), below).

Webhooks support **HTTP Basic Authentication** to verify the request came from Recurly's servers.

Please see our [IP Whitelisting documentation](https://docs.recurly.com/v1.0/docs/ip-allowlist#/) for the current list of Recurly IPs.  
You may refuse other IP addresses at your endpoint or firewall.

<Cards columns={1}>
  <Card title="ModSecurity Users" icon="fa-exclamation-triangle">
    Recurly does not endorse any specific web server or plugin, but if you run Apache with ModSecurity, you may need to disable rule #990011 so webhook requests are not blocked.
  </Card>
</Cards>
