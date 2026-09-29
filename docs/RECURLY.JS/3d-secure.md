---
title: 3D Secure
excerpt: >-
  Add PSD-2 compliant 3-D Secure (3DS 2.x) flows to your Recurly.js checkout so
  card-holders can complete issuer-mandated authentication without leaving your
  page.
deprecated: false
hidden: false
metadata:
  robots: index
---
<div class="rp-page">
  <div class="rp-overview"><code>recurly.Risk().ThreeDSecure()</code> lets you trigger and complete Strong Customer Authentication (SCA) right in the browser. Pass the action token you received from the Recurly API, attach the component to an element on your page, and listen for a <code>token</code> (success) or <code>error</code> event. Recurly.js handles device fingerprinting and challenge display, then returns a <code>three_d_secure_action_result</code> token you can use in any follow-up API call — a purchase, a subscription, or a billing info update.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly Subscriptions plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">2</span>Key details</a>
  </div>
</div>

### Prerequisites & limitations

<ul class="rp-list">
  <li>Your site must use a gateway that Recurly supports for 3-D Secure 2.x (e.g., Braintree, Cybersource, Worldpay, Adyen).</li>
  <li>You must already have an action token from the Recurly API (<code>three_d_secure_action_token_id</code> or a proactive token).</li>
  <li><code>threeDSecure.attach()</code> must be called from a user-initiated event such as <code>click</code> or <code>touchend</code> — otherwise browsers will block the pop-up/iframe.</li>
  <li>By default, Recurly performs gateway device-data pre-flights. You may disable them (<code>preflightDeviceDataCollector.enabled: false</code>) only if you're certain no challenge will be required.</li>
  <li>Proactive 3-D Secure (authenticating before the first transaction) is currently available only for Braintree — enable it via <code>risk.threeDSecure.proactive</code> in <code>recurly.configure</code>.</li>
  <li>Provide a visible container element (~250 × 400 px) for the challenge, and remove or hide it only after a <code>token</code> or <code>error</code> event.</li>
  <li>The resulting <code>three_d_secure_action_result</code> token expires in 20 minutes and cannot be recovered after expiry.</li>
</ul>

# Definition

<div class="rp-definition">Recurly.js's <code>ThreeDSecure</code> component handles Strong Customer Authentication (SCA) — the identity checks card networks and issuing banks require under PSD2 — directly on your checkout page. It exists so you can complete this authentication without redirecting shoppers away from your site or building the device-fingerprinting and challenge-display logic yourself.</div>

# Key details

Strong customer authentication for your users.

Recurly.js provides a set of utilities that allow you to support 3-D Secure authentication on your checkout page seamlessly. For more information on 3-D Secure, see our <a href="https://docs.recurly.com/recurly-subscriptions/docs/revised-payment-services-directive-psd2#/" target="_blank">Introduction to Strong Customer Authentication</a>.

Recurly's support for 3-D Secure utilizes both Recurly.js and our API. For a complete guide to this integration, start with our <a href="https://docs.recurly.com/recurly-subscriptions/docs/3d-secure-20-integration-guide#/understanding-the-sca-flows" target="_blank">Strong Customer Authentication (SCA) Integration Guide</a>.

Let's take a look at an example implementation.

```javascript
const risk = recurly.Risk();
const threeDSecure = risk.ThreeDSecure({
  actionTokenId: myActionTokenId
});

threeDSecure.on('token', function (token) {
  // handle passing the action result
  // token back to your server

  // token.type => 'three_d_secure_action_result'
  // token.id

  // optionally, you may call threeDSecure.remove() to remove the element
});

threeDSecure.on('error', function (error) {
  // handle error scenarios.

  // error.code
  // error.message

  // optionally, you may call threeDSecure.remove() to remove the element
});

threeDSecure.attach(document.querySelector('#my-auth-container'));
```

## Additional configuration

### Pre-flight 3-D Secure authentication

Recurly.js will perform some pre-flight authentication steps prior to tokenization. If you use a gateway that's compatible with this process, it happens automatically.

This process can be prevented with the following configuration value:

```javascript
recurly.configure({
  // ...
  risk: {
    threeDSecure: {
      preflightDeviceDataCollector: {
        enabled: false
      }
    }
  }
  // ..
});
```

### Re-authenticating existing billing information

You can collect device data to re-authenticate existing billing information by providing the billing info ID alongside the CVV element.

Below is an example of configuring preflight fingerprinting for existing billing infos for Cybersource and WorldPay gateways.

```javascript
recurly.configure({
  // ...
  risk: {
    threeDSecure: {
      preflightDeviceDataCollector: {
        enabled: true,
        billingInfoId: "abc1234"
      },
    }
  }
  // ..
});
```

### Proactive 3-D Secure

Recurly.js can perform Strong Customer Authentication prior to an initial transaction. This feature is currently available only if you are using a Braintree gateway.

Enable proactive 3-D Secure with the following configuration:

```javascript
recurly.configure({
  // ...
  risk: {
    threeDSecure: {
      proactive: {
        enabled: true,
        gatewayCode: 'my-gateway-code',
        amount: 0.00
      },
    }
  }
  // ..
});
```

With proactive 3-D Secure enabled, you will receive a `three_d_secure_proactive_action_token` when you tokenize your billing information. This value can be passed in as an `actionTokenId` to the `threeDSecure` class to enable the Strong Customer Authentication flow.

## Reference

### <span class="heading-tag heading-tag--fn">fn</span> recurly.Risk

#### Arguments

None.

#### Returns

A new `Risk` instance.

### <span class="heading-tag heading-tag--fn">fn</span> recurly.ThreeDSecure

#### Arguments

<table class="rp-params">
  <tr class="rp-thead-row"><td>Param</td><td>Type</td><td>Description</td></tr>
  <tr><td><code>options</code></td><td><code>Object</code></td><td></td></tr>
  <tr><td><code>options.actionTokenId</code></td><td><code>String</code></td><td><code>three_d_secure_action_token_id</code> OR <code>three_d_secure_proactive_action_token_id</code> returned by the Recurly API when 3-D Secure authentication is required for a transaction</td></tr>
</table>

#### Returns

A new `ThreeDSecure` instance.

### <span class="heading-tag heading-tag--fn">fn</span> threeDSecure.attach

#### Arguments

<table class="rp-params">
  <tr class="rp-thead-row"><td>Param</td><td>Type</td><td>Description</td></tr>
  <tr><td><code>container</code></td><td><code>HTMLElement</code></td><td>A DOM element to contain any UI elements necessary to fulfill the 3-D Secure authentication process. We recommend this element be a minimum size of 250px (W) x 400px (H), and contain an interstitial message to explain that 3-D Secure authentication will be required to complete the transaction.</td></tr>
</table>

#### Returns

Nothing.

#### Events

##### `token`

This event is fired when your customer has completed the 3-D Secure flow. Recurly has received the authentication details, and generated this token to be used in our API.

<table class="rp-params">
  <tr class="rp-thead-row"><td>Param</td><td>Type</td><td>Description</td></tr>
  <tr><td><code>token</code></td><td><code>Object</code></td><td></td></tr>
  <tr><td><code>token.type</code></td><td><code>String</code></td><td>'three_d_secure_action_result'</td></tr>
  <tr><td><code>token.id</code></td><td><code>String</code></td><td>Token identifier to be sent to the API</td></tr>
</table>

##### `error`

This event is emitted when any error is encountered, whether during setup of the 3-D Secure flow, or during authentication. It will be useful to display errors to your customer if a problem occurs during the 3-D Secure flow.

<table class="rp-params">
  <tr class="rp-thead-row"><td>Param</td><td>Type</td><td>Description</td></tr>
  <tr><td><code>error</code></td><td><code>RecurlyError</code></td><td>An error describing the issue that occurred.</td></tr>
</table>
