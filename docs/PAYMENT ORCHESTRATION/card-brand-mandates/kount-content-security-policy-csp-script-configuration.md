---
title: Kount Content Security Policy (CSP) Script Configuration
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
[block:callout]
{
  "type": "danger",
  "body": "This documentation only applies to merchants who use a Content Security Policy (CSP). If you do not use a CSP, you do not need to complete this configuration.",
  "title": "Notice for merchants without a CSP"
}
[/block]
###Background
With the Google Chrome 80 update, Recurly has needed to make several updates to our Kount integration, which powers all existing fraud management solutions within Recurly. These updates will require some action from your end if you use a Content Security Policy on your checkout page. 

###Configuration
To ensure device fingerprinting continues to work as expected for your site, you will need to add the script called out below to your existing CSP:
[block:code]
{
  "codes": [
    {
      "code": "<meta http-equiv=\"Content-Security-Policy\" content=\"img-src https://DATA_COLLECTOR_URL;connect-src 'self' 'unsafe-eval' 'unsafe-inline' https://DATA_COLLECTOR_URL; script-src 'unsafe-eval' 'unsafe-inline' https://DATA_COLLECTOR_URL; child-src https://DATA_COLLECTOR_URL\">",
      "language": "text"
    }
  ]
}
[/block]
For the script above, replace the DATA_COLLECTOR_URL value with one of the following URLs depending on your site mode:

* Sandbox: https://tst.kaptcha.com
* Production: https://ssl.kaptcha.com