---
title: Client libraries
excerpt: >-
  Official SDKs and client libraries for integrating the Recurly Subscriptions
  API in your preferred language or platform.
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

Recurly provides official client libraries for all major programming languages and mobile platforms. These libraries handle authentication, request formatting, and error handling — so you can focus on building your subscription features

## API client libraries

We maintain official client libraries for seven languages. Each library is kept in sync with the latest API version and includes comprehensive documentation.

### Ruby

The Ruby client is distributed via Rubygems and works with Ruby 2.7+.

* **Documentation**: [Rubydocs](https://recurly.github.io/recurly-client-ruby/)
* **Source code**: [GitHub](https://github.com/recurly/recurly-client-ruby)
* **Package**: [Rubygems](https://rubygems.org/gems/recurly)

Install via Bundler:

```ruby
gem 'recurly'
bundle install
```

### Node.js

The Node.js client supports Node 14+.

* **Documentation**: [GitHub Pages](https://recurly.github.io/recurly-client-node/)
* **Source code**: [GitHub](https://github.com/recurly/recurly-client-node)
* **Package**: [npm](https://www.npmjs.com/package/recurly)

Install via npm:

```bash
npm install recurly
```

### Python

The Python client supports Python 3.7+.

* **Documentation**: [ReadTheDocs](https://recurly-client-python.readthedocs.io/en/latest/)
* **Source code**: [GitHub](https://github.com/recurly/recurly-client-python/)
* **Package**: [PyPI](https://pypi.org/project/recurly/)

Install via pip:

```bash
pip install recurly
```

### .NET

The .NET client supports .NET 6.0+.

* **Source code**: [GitHub](https://github.com/recurly/recurly-client-dotnet)
* **Package**: [NuGet](https://www.nuget.org/packages/Recurly/)

Install via NuGet Package Manager:

```
Install-Package Recurly
```

### Java

The Java client supports Java 8+.

* **Source code**: [GitHub](https://github.com/recurly/recurly-client-java)
* **Package**: [Maven Central](https://search.maven.org/artifact/com.recurly.v3/api-client/)

Add to your `pom.xml`:

```xml
<dependency>
  <groupId>com.recurly.v3</groupId>
  <artifactId>api-client</artifactId>
  <version>LATEST</version>
</dependency>
```

### PHP

The PHP client supports PHP 7.4+.

* **Source code**: [GitHub](https://github.com/recurly/recurly-client-php)
* **Package**: [Packagist](https://packagist.org/packages/recurly/recurly-client)

Install via Composer:

```bash
composer require recurly/recurly-client
```

### Go

The Go client supports Go 1.16+.

* **Source code**: [GitHub](https://github.com/recurly/recurly-client-go)
* **Releases**: [GitHub Releases](https://github.com/recurly/recurly-client-go/releases)

Install via `go get`:

```bash
go get github.com/recurly/recurly-client-go/v3
```

## Mobile SDKs

The Recurly Native Mobile SDKs let you securely collect payment information directly on iOS and Android devices. When customers submit payment details through the SDK, the data is encrypted and sent directly to Recurly — your servers never touch sensitive card data. This drastically reduces your PCI compliance scope.

### How it works

1. Customer enters payment details in your app using the Recurly SDK
2. SDK encrypts the data and sends it directly to Recurly
3. Recurly returns an authorization token
4. Your app sends that token to your server
5. Your server completes the subscription using the Recurly API

This flow means your PCI scope is minimal — you're not storing or transmitting raw payment data.

### iOS

The Recurly iOS SDK integrates with Xcode and CocoaPods.

* **Source code**: [GitHub](https://github.com/recurly/recurly-client-ios)
* **Documentation**: [CocoaPods](https://cocoapods.org/pods/RecurlySDK)

Install via CocoaPods:

```
pod 'RecurlySDK'
pod install
```

### Android

The Recurly Android SDK works with Android API level 21+.

* **Source code**: [GitHub](https://github.com/recurly/recurly-client-android)
* **Package**: [Maven Central](https://search.maven.org/artifact/com.recurly/android-sdk)

Add to your `build.gradle`:

```gradle
dependencies {
  implementation 'com.recurly:android-sdk:LATEST'
}
```

## Older API versions

If you're still using our older XML API (v2), documentation and client libraries are available separately. However, we strongly recommend upgrading to the REST API v3, which offers better performance, more features, and improved developer experience.

[Browse v2 documentation and libraries](/developers/api-v2)

# FAQs

**Which client library should I use?**

Choose the library that matches your project's language or platform. All official libraries are maintained and kept current with the API.

**Are the client libraries open source?**

Yes, all Recurly client libraries are open source and hosted on GitHub. You can review the code, file issues, and contribute.

**Do I have to use an official client library?**

No, you can work directly with the REST API using any HTTP client. However, the official libraries save you time by handling authentication, serialization, and error handling.

**How do I report a bug in a client library?**

File an issue on the library's GitHub repository. For security issues, email [security@recurly.com](mailto:security@recurly.com).

**Can I use the mobile SDKs without a backend server?**

Not for completing subscriptions. The mobile SDK collects payment data and returns a token, but you still need a backend server to call the Recurly API to create or update subscriptions. This architecture keeps your PCI compliance scope minimal.

**What if my language isn't supported?**

You can integrate directly with our REST API using any HTTP client library. The Recurly API is language-agnostic — you just need to handle HTTP requests and JSON responses.

**How do I keep my client library up to date?**

Each language's package manager (npm, pip, Rubygems, etc.) lets you check for and install updates. We recommend staying on the latest version for the best performance and features.