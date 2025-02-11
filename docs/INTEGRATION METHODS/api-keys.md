---
title: REST API keys
excerpt: >-
  Integrate and communicate effortlessly with Recurly using secure REST API
  keys.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Overview

### Required plan

This feature or setting is available to all customers on any Recurly subscription plan.

### Prerequisites

* A Recurly account with a Role that includes the Integration permission.
* Familiarity with API integrations and basic understanding of HTTP Basic Authentication.

### Limitations

* API keys grant full access to your Recurly account and should be protected diligently.
* Exposing API keys publicly can compromise account security.

# Definition

REST API keys are unique identifiers that authenticate and grant access to the Recurly API. They function as a secure bridge, allowing external applications to communicate and interact with Recurly's platform.

# What is an API?

An API, or Application Programming Interface, acts as a communication channel between different software applications. To interface with Recurly, an API key is essential. Think of this key as a unique password that Recurly uses to identify and authenticate the requesting program.

### Find or generate your API key

To integrate with Recurly, you'll often need an API key. Here's how to obtain or create one:

1. Navigate to **Integrations > API Credentials** as a User assigned a Role that includes the Integration permission.

   <Image align="center" className="border" width="50% " border={true} src="https://files.readme.io/bfd81d4-Screen_Shot_2019-11-12_at_08.32.07.png" />

2. Scroll to the bottom and select **Add Private API Key**.

<Image align="center" className="border" border={true} src="https://files.readme.io/4ec2676-Screen_Shot_2017-02-24_at_3.31.06_PM.png" />

3. Assign a name to your API key, jot down its purpose, and specify the third-party application it's intended for.

<Image align="center" className="border" border={true} src="https://files.readme.io/8793e7e-Screen_Shot_2017-02-24_at_3.31.38_PM.png" />

4. Confirm by clicking **Save Changes**.

### Regenerating an API key

An API key can be regenerated in 2 different ways. Either the existing API key will remain active for a 12 hour window or it will be disabled immediately. To regenerate a key, follow these steps:

1. Head to **Developers > API keys**.
2. **Identify** the key that you wish to regenerate.
3. **Choose** the Regenerate Key option.
4. **Select** the behavior that you would like to apply to the existing API key.

## Revoking an API key

If you would like to revoke an API key, you can do so by following the steps below. We recommend that you revoke your API key if you have any reason to believe the security of the key may be compromised.

1. As a developer or Admin user, navigate to Developers > API Keys.

2. Find the key you would like to revoke.

3. You have three options: revoke the key permanently, to regenerate the key immediately, or to regenerate the key within 12 hours.

<Image align="center" className="border" border={true} src="https://files.readme.io/48ebbca-Screen_Shot_2017-02-24_at_3.36.40_PM.png" />

**Immediately Revoke**

If you revoke the key, we will not create another key, and it will immediately stop working. All applications that have access to Recurly via that key will immediately cease to have access.

**Regenerate Immediately**

If you regenerate a key immediately, the old key will stop working, and Recurly will issue you a new API key. All applications that have access to Recurly via the old key will immediately cease to have access, and we recommend that you update applications with the new key.

<Image align="center" className="border" border={true} src="https://files.readme.io/e73019d-Screen_Shot_2017-02-24_at_3.39.18_PM.png" />

## Base64 encoded API keys

For a Base64 encoded API key, simply navigate to **Integrations > API Credentials** and expand **"Need help using the API Key?"**. The characters following "Authorization: Basic" represent your encoded key.

<Image align="center" className="border" border={true} src="https://files.readme.io/242d8ac-2019-11-07_0926.png" />

**Regenerate after 12 hours**

If you choose this option, the old key is still valid for 12 hours, and Recurly will generate a new key. This will allow you time to update applications using the old key to the new key. During the 12-hour period, applications using the old key will not be affected and will be able to authenticate as if nothing has changed. When 12 hours passes, the old key will no longer function.

## API key security

API keys grant full access to your Recurly account and should be protected the same way you would protect your password. In particular, there are a few common scenarios to keep in mind when working with API keys.

* Give each integration its own API key, and assign labels to each key so you know which key goes with which application. If a specific API key is compromised, you can disable that key without disabling access to all of your other integrations.
* Be careful not to expose the key to the public (such as in screenshots, videos, or help documentation). Remember that blurring your data isn't always enough. It's best to use "cut" functions in your graphics program to remove the data completely.
* If a key needs to be shared, generate a new key and label it accordingly so it can be disabled, if needed. Never email the API key, because it would allow access to your Recurly account if hackers were to compromise your email account.
* If you revoke a user's access to your Recurly account, any API keys created by the user will be removed from your account.
* Do not embed, store, or expose your API key(s) within client-side code, including JavaScript, mobile applications, and native executables. A bad actor can decompile your application and obtain your API key(s).

# FAQs

**Q:** What exactly is an API key in the context of Recurly?\
**A:** An API key is a unique identifier that allows external applications to securely communicate and interact with Recurly's platform. Think of it as a specialized password that Recurly uses to authenticate and authorize the requesting program.

**Q:** How often should I change or update my API keys?\
**A:** While there's no strict frequency, it's a good practice to update API keys periodically or if you believe they might have been compromised. Regularly reviewing and managing your API keys enhances security.

**Q:** Can I have multiple API keys for different applications or integrations?\
**A:** Yes, you can generate multiple API keys. In fact, it's recommended to use separate keys for different integrations to ensure better security and easier management.

**Q:** What happens if I revoke an API key?\
**A:** Once revoked, the API key will no longer function. Any application or integration using that key will immediately lose access to Recurly until a valid key is provided.

**Q:** Is there a way to temporarily disable an API key without revoking it?\
**A:** No, the options available are to either revoke the key immediately or regenerate it. If you wish to temporarily disable access, you might consider regenerating the key and then providing the new key when you want to restore access.

**Q:** How do I ensure the security of my API keys?\
**A:** Treat API keys as you would sensitive passwords. Avoid exposing them publicly, share them securely, and never embed them in client-side code. Regularly reviewing and updating your keys also enhances security.
