---
description: >-
  URL is an abbreviation of "Uniform Resource Locator" and it is the page's
  address on the web.
---

# URL Aliases in Varbase/Drupal

URL/path aliases are automatically generated in Varbase for various kinds of content (nodes, taxonomy terms, users) without requiring the user to manually specify the path alias. This allows the administrator to have URL aliases like /category/my-node-title instead of /node/123.

Drupal assigns a unique id number to each node created, ex: /node/60. However, by using "URL Alias" a more readable URL alias can be generated, ex: /node/landing-page.

The aliases are based upon a "pattern" system that uses tokens that the administrator can change. In Drupal, you can specify a pattern to follow for different types of content. Which gives the ability to automatically generate or regenerate aliases for pre-existing content as well as using tokens.

Hint: This can be achieved by using the [Pathauto](https://www.drupal.org/project/pathauto) module which comes pre-installed with Varbase and is enabled by default.
