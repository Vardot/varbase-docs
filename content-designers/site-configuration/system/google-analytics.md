# Google Analytics

While installing Varbase, the developers had a step to install [**Google Analytics**](https://www.drupal.org/project/google_analytics) and [**Google Tags Manager**](https://www.drupal.org/project/google_tag).

<figure><img src="../../../.gitbook/assets/image (7).png" alt=""><figcaption><p>Site Installation List</p></figcaption></figure>

### Google Analytics:

### How to Navigate the Google Analytics:

1. Form **Configuration/ Web services/&#x20;**_**Google Analytics.**_

<figure><img src="../../../.gitbook/assets/image (4).png" alt=""><figcaption><p>Navigate Google Analytics</p></figcaption></figure>

2. You'll find the settings to add and control the site Google Analytics.
   1. Add your site id in the **Web Property ID(s)** field.
      1. From [Google Analytics](https://marketingplatform.google.com/about/analytics/), Add your business plan to access the Google Councol
      2. Copy your ID and add it to the **Web Property ID(s)** field.
   2. Fill the information in the following tabs:
      * **Domains:** The domain you want to track.
      * **Pages:** To extract specific pages from tracking.
      * **Roles:** Add tracking for specific roles.
      * **Users:** Allow users to customize tracking on their account page.
      * **Links and downloads:** Outbound links, Mailto links, Downloads, Colorbox enabled.
      * **Messages:** Track messages of type \[Warning, Error, Status].
      * **Search and Advertising:** Tracking search and advertising.
      * **Privacy:** Anonymize IP enabled.
      * **Dimensions and Metrics:** Custom dimensions and metrics.
      * **Advanced:** Some additional settings such as caching and Custom JavaScript code.
3. Click on **Save Configuration** button.

<figure><img src="../../../.gitbook/assets/image (6).png" alt=""><figcaption><p>Google Analytics Page</p></figcaption></figure>

***

### Google Tags:

In Google Tags, you can add tags to track components inside the page e.g. Block.

### How to Navigate the Google Tags:

1. Form **Configuration/ Web services/&#x20;**_**Google Tags.**_

<figure><img src="../../../.gitbook/assets/image (8).png" alt=""><figcaption><p>Navigate Google Tag</p></figcaption></figure>

2. You'll find the settings to add and control the site Google Tags.
   1. Add your site id in the **Google Tag ID(s)** field - _**Get from your developer**_&#x46;ill the information in the following tabs:

Event tabs:

* **Custom event:** Enable event custom event.
* **Generate lead:** Enable event Generate lead
* **Login:** Enable event Login
* **Search:** Enable event Search
* **User registration:** Enable event User registration
* **Purchase (Webform):** Enable event Purchase (Webform)

Conditions tabs:

* **Response Code:** Specify response codes.
* **Request Path:** Specify pages by using their paths.
* **Response status:** Shows the block on pages with any matching response status.
* **User Role:** Add tracking for specific roles.
* **Webforms:** Select 'Webform from URL' to display this block, when the current request's path contains the selected webform.
* **Content type:** Add tracking to specific content type.
* **Vocabulary:** Add tracking to specific vocabulary.
* **Webform:** Add tracking to specific Webform.
* **Advanced:** Enforce Privacy Consent Policy.

3. Click on **Save.**

<figure><img src="../../../.gitbook/assets/image (9).png" alt=""><figcaption><p>Default Tag Settings Page</p></figcaption></figure>

{% hint style="info" %}
Google Tag has the same practical method as Google Analytics but within the same page.
{% endhint %}

{% hint style="info" %}
For additional information See: [Varbase SEO](../../../developers/understanding-varbase/core-components/varbase-seo.md) and [Configuring SEO Features](../../../developers/configuring-a-varbase-site/configuring-seo-features/)
{% endhint %}
