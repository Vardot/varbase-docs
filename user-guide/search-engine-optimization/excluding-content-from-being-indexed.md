# Prevent a Single Content From Being Indexed

This article will walk you through how to exclude a specific piece of content from being indexed in search engines. To achieve this, you'll need to:

1. Set `noindex` value for `robots` meta tag when adding or editing the content
2. Prevent the content from being added to the XML sitemap

So let's see below how we can achieve this:

## Set `noindex` value for `robots` meta tag when adding or editing the content

1. Navigate to any content for example filter the content page with Basic page
2. Edit a certain basic page
3. From the right hand side look for “Meta tags” section.

![Meta tags section for every node page](../../.gitbook/assets/meta.png)

4. Open _Meta tags_ section and scroll down into the "Advanced" tab.  
5. Look for "Robots" title, and check on "noindex - Prevents search engines from indexing this page."

![Check the nonindex option under Robots section](../../.gitbook/assets/robot.png)

## Prevent the content from being added to the XML sitemap

1. Navigate to any content for example filter the content page with Basic page
2. Edit a certain basic page
3. Look for “Simple XML Sitemap” and click the item that can be located in the sidebar \(the node settings\)

![Sitemap section under basic page](../../.gitbook/assets/create-basic-page-test-qa-varbase-8-8-x-development-13-07-2020.png)

 4. You will be seeing two options, “Do not index this basic page” or by default, it is selected “Index this Basic page”

![Update sitemap section using this option](../../.gitbook/assets/sitemap.png)

5. To exclude this page from being indexed please select “Do not index this Basic page entity in variant Default”

You can apply this setting before creating any content by just visiting the “Simple XML Sitemap” settings if it is enabled.

{% hint style="info" %}
Some of the content types will be disabled by default like Hero Slider, Testimonials.  In another way, any content type that doesn't have a node page will not be indexed.
{% endhint %}

![Hero Slider content type in site map is disabled by default ](../../.gitbook/assets/create-hero-slider-test-qa-varbase-8-8-x-development-13-07-2020.png)

