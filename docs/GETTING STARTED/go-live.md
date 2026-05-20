---
title: Go live checklist
excerpt: >-
  A step-by-step checklist covering everything you need to set up, test, and
  launch your Recurly integration — from sandbox to production.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Welcome to Recurly

From acquisition to retention to scale, Recurly does it all. Whether you are choosing Recurly to optimize your subscription growth strategy, realize industry-leading revenue recovery, and/or greatly reduce involuntary churn, we are glad you are here.

Recurly is the only platform that has mastered plan management, recurring billing and payments, and intelligent retention, and we look forward to working with you through this experience.

## Go live checklist

Here is a general overview of the steps to implement Recurly, though complexity for each step may vary by your size, budget, and business needs.

<HTMLBlock>{`
<p><a href="https://recurly.com/product/support-and-services" target="_blank">Enablement</a> packages for onboarding, data migration and/or professional services can help make these steps much easier.</p>
`}</HTMLBlock>

<HTMLBlock>{`
<style>
  #go-live-checklist td,
  #go-live-checklist th {
    vertical-align: top;
    text-align: left;}
</style>
<table id="go-live-checklist">
  <thead>
    <tr>
      <th>✔️</th>
      <th>Step</th>
      <th>Action</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>&nbsp;</td>
      <td>1</td>
      <td><p>
          <a href="https://app.recurly.com/signup/" target="_blank">     Sign up for a sandbox site</a>&nbsp;to test out Recurly’s capabilities.</p>
<a href="https://app.recurly.com/signup/" target="_blank"></a>
<p>Take the time to explore the sandbox and build it to suit your needs. Here is <a href="https://docs.recurly.com/docs/sandbox-features-to-discover" target="_blank">a list of the sandbox features to consider</a> when setting up your sandbox for success.
        </p>
<p><strong>PLEASE NOTE</strong>: When you’re ready to go live, all sandbox customer accounts, transactions, and invoices are wiped clean so accounting can start fresh with real data. You can do that any time by clicking Clear Test Data.</p></td>
    </tr>
    <tr>
      <td>&nbsp;</td>
      <td>2</td>
      <td><p>Recurly offers two ways to integrate with your customer journey and enable PCI-compliant checkouts:</p>
<p><strong>Custom checkout</strong>: Create a custom checkout page or modify an existing one by adding the <a href="https://developers.recurly.com/reference/recurly-js/" target="_blank">Recurly.js</a> library. Use our <a href="https://recurly.com/developers/api/v2021-02-25/index.html" target="_blank">API documentation</a> to create accounts, subscriptions, and one-time purchases in a single checkout flow (we recommend the <code>/purchase</code> endpoint).</p>
<p><strong>Hosted Pages</strong>: Use Recurly’s <a href="https://docs.recurly.com/docs/checkout" target="_blank">Checkout</a> to quickly and easily allow customers to sign up for your plans.</p></td>
    </tr>
    <tr>
      <td>&nbsp;</td>
      <td>3</td>
      <td><p>Connect your gateway to your Recurly Account. If you don't already have a gateway, establish an account with <a href="https://recurly.com/gateways/" target="_blank">one</a> of Recurly’s supported <a href="https://docs.recurly.com/docs/payment-gateways" target="_blank">gateways</a>. Initiating a gateway can take up to 45 days.<br></p></td>
    </tr>
    <tr>
      <td>&nbsp;</td>
      <td>4</td>
      <td><p>Once you have subscribed to a <a href="https://recurly.com/plans/" target="_blank">Recurly plan</a> and are ready to test, <a href="https://support.recurly.com/" target="_blank">message support</a> to enable development mode.</p></td>
    </tr>
    <tr>
      <td>&nbsp;</td>
      <td>5</td>
      <td><p>Test your <a href="https://docs.recurly.com/docs/payment-gateways#test-configuration" target="_blank">gateway(s</a>) in development mode to verify that your Recurly integration is working correctly.</p></td>
    </tr>
    <tr>
      <td>&nbsp;</td>
      <td>6</td>
      <td><p>Get your customer service team trained on how to manage an account, create subscriptions, etc. </p></td>
    </tr>
    <tr>
      <td>&nbsp;</td>
      <td><p>7</p></td>
      <td><p>If using the API, review all API and Recurly.js calls - <a href="https://developers.recurly.com/api/v2021-02-25/index.html" target="_blank">API Documentation</a><br></p>
<ol><li>Complete a customer signup in your sandbox environment. Ensure that the customer account and subscription were created correctly.</li><li>Test any additional API requests and processes (e.g., upgrades, downgrades, cancellations, or refunds).</li><li>Review Recurly.js and API calls for operational efficiency.</li></ol></td>
    </tr>
    <tr>
      <td>&nbsp;</td>
      <td>8</td>
      <td><p>Click the link on the <a href="https://app.recurly.com/go/guides/progress" target="_blank">Welcome page</a> to switch to Production Mode and start billing customers. <strong>Note: This action is irreversible, so make sure you are finished testing in Sandbox or Development modes before proceeding.</strong></td>
    </tr>
    <tr>
      <td>&nbsp;</td>
      <td>9</td>
      <td><p>
          Update all configurations from Sandbox/Dev to Production, including
          payment gateways,
          <a href="https://developers.recurly.com/reference/webhooks/" target="_blank">webhooks</a>, etc.
        </p></td>
    </tr>
    <tr>
      <td>&nbsp;</td>
      <td>10</td>
      <td><p>
          Now that you’re in production, send a test transaction through the
          gateway and then
          <a href="https://docs.recurly.com/docs/transactions#refunds-and-voids" target="_blank">void</a>
          it. Remember that all transactions affect reporting and cannot be deleted.
        </p></td>
    </tr>
    <tr>
      <td>&nbsp;</td>
      <td>11</td>
      <td><p>
          <a href="https://docs.recurly.com/docs/customer-imports" target="_blank">Import</a> existing business data, such as customer accounts and billing information, using the API or through a <a href="https://go.recurly.com/rs/439-LSC-903/images/Recurly-EnablementServices-Imports-Overview.pdf" target="_blank">Professional Services engagement</a>. Historical transaction data is not imported, and data from gateways may take time to prepare.
        </p></td>
    </tr>
  </tbody>
</table>
`}</HTMLBlock>