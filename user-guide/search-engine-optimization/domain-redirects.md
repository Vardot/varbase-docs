# Domain Redirects

### What Is Domain Redirects?

The domain redirect is accessed through Domain Redirects. The user can add the domain redirects through the domain redirect table which consists of the domain from which it needs to be redirected, the subpath, and the complete URL destination to which it needs to be redirected. The module also supports the usage of wildcard redirecting, thus many requests can be handled with one instance of domain redirect.

### Who Can Manage the URL Redirects?

By default on Varbase, there are default roles that can manage URL Redirects and they are:

* Super Admin
* SEO Admin
* Site Admin

### How to Manage the Domain Redirects?

As a Super Admin, Site Admin, or SEO Admin, please navigate to **Administration \ Configurations \ Search and metadata \ Redirect \ **_**Domain Redirects**_.

![Managing URL redirects](<../../.gitbook/assets/image (51).png>)

Follow these steps on how to manage the domain redirects:

1. Fill in the _From domain_ field
2. Fill in the _sub path_ fields - _add "/\*" that means any path_
3. Fill in the _Destination _field
4. Click the _Save _button

When filling in the _From domain_ field, you are just simply saying from where the users will be redirected to the _Destination._

Example:&#x20;

example.com/\* => redirected.com
