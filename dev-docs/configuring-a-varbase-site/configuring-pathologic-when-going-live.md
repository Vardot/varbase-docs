# Configuring Pathologic When Going Live

This module [Pathologic](https://www.drupal.org/project/pathologic) is already installed and configured within Varbase. The main purpose of this module is to fix all URLs that should redirect to the production site if it was redirected to the internal contents.

To navigate to the Pathologic configuration page: **Administration \ Configuration \ Content authoring \** _**Pathologic configuration**_

There are three type of URL formats:

* Full URL \(http://example.com/foo/bar\):  This option is best for stopping broken images and links in syndicated content \(such as in RSS feeds\), but will likely lead to problems if your site is accessible by both HTTP and HTTPS.
* Protocol relative URL \(//example.com/foo/bar\):  Paths output with the _Protocol relative URL_ option will avoid such problems, but feed readers and other software not using up-to-date standards may be confused by the paths.
* Path relative to server root \(/foo/bar\):  The _Path relative to server root_ option will avoid problems with sites accessible by both HTTP and HTTPS with no compatibility concerns, but will absolutely not fix broken images and links in syndicated content.

{% hint style="info" %}
We recommend to use the "Path relative to server root" option. That is if your website's URL does not live inside a directory that appears in the URL.
{% endhint %}

![Pathologic configuration section](../../.gitbook/assets/image%20%2838%29.png)

As you have noticed from the above screenshot in the text area field "All base paths for this site", we have inserted the base URLs as example links acting as testing environments and the production environment:

* https://www.example.com/
* http://www.example1.com/ 
* https://dev.example.com/ 
* http://dev.example.com/ 
* https://stg.example.com/
* http://stg.example.com/

We will test this for example let us create new Basic page content and insert text with hyperlinks:

* "Link" is linked to "https://www.example.com/test"
* "Link1" is linked to "https://www.example1.com/test"
* "Link2" is linked to "https://www.example2.com/test"

![Creating new Basic page with linked contents](../../.gitbook/assets/image%20%2835%29.png)

After we created the Basic page content, let us know how the links are showing on the frontend by using the inspect element \(DevTool\)

![](../../.gitbook/assets/image%20%2841%29.png)

As you can see from the screenshot above, notice "Link2" how it is linked and the rest links are being stripped out from the base URL, this is because "https://www.example2.com/" is not listed within the "All base paths for this site" field.

