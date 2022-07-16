---
description: Security Kit for XSS, CSRF, SSL/TLS, Expect-CT, and More
---

# Other Security Kits

To configure the Security Kit module in your site, navigate to:\
**Administration** \ **Configuration** \ **System** \ _**Security Kit settings**_

![Security Kit](../../../.gitbook/assets/Security-Kit--varbase\_security.png)

The configuration page allows you to configure settings to tighten your website's security regarding:

* **Cross-site Scripting (XSS)**
  * **Content Security Policy (CSP)**: Content Security Policy is a policy framework that allows to specify trustworthy sources of content and to restrict its capabilities. You may read more about it at [Mozilla Wiki](https://wiki.mozilla.org/Security/CSP).
  * **X-XSS-Protection header**: `X-XSS-Protection` HTTP response header controls Microsoft Internet Explorer, Google Chrome and Apple Safari internal XSS filters.
* **Cross-site Request Forgery (CSRF):** Configure levels and various techniques of protection from cross-site request forgery attacks.
* **Clickjacking**
  * **X-Frame-Options header:** Configure the `X-Frame-Options` HTTP header.
  * **JavaScript-based protection:** Warning: With this enabled, the site will not work at all for users who have JavaScript disabled (e.g. users running the popular [NoScript](https://noscript.net/) browser extension, if they haven't whitelisted your site).
* **SSL/TLS:** Configure various techniques to improve security of SSL/TLS
* **Expect-CT:** Configure the `Expect-CT` header which allows sites to opt in to reporting and/or enforcement of Certificate Transparency requirements. See [Mozilla's developer documentation](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Expect-CT).
* **Feature policy:** Allows configuration of the `Feature-Policy` header to selectively enable, disable, and modify the behavior of certain APIs and web features in the browser. See [Google's developer documentation](https://developers.google.com/web/updates/2018/06/feature-policy).
* **Miscellaneous:** Configure miscellaneous unsorted security enhancements such as:
  * `From-Origin` HTTP response header
  * `Referrer-Policy` HTTP response header

All necessary documentation and examples of usage are on the __ settings page.
