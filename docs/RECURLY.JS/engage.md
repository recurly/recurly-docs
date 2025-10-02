---
title: Recurly Engage
excerpt: Use Recurly Engage with Recurly.js
deprecated: false
hidden: false
metadata:
  robots: index
---
If you are using [Recurly Engage](https://docs.recurly.com/recurly-engage/docs/overview-recurly-engage), Recurly.js will automatically load your directives. This is accomplished by checking for Engage settings when Recurly.js is loaded.

If you know that you do not want to load Engage on a specific page or context, you can circumvent the remote settings check using the following configuration.

```javascript
recurly.configure({
  // ...
  "engage": {
    "enabled": false
  }
});
```