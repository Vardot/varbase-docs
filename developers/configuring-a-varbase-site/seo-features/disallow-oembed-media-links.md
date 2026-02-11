# Disallow Oembed Media Links

When Drupal's media system handles oEmbed content (such as YouTube or Vimeo videos), it creates internal URLs at paths like `/media/oembed` that serve as intermediary endpoints. These URLs are not intended to be indexed by search engines and can create duplicate content issues or pollute search results if they are crawled.

## The Problem

oEmbed media URLs typically follow patterns such as:

```
/media/oembed?url=...
```

These endpoints serve the embedded content for rendering within your pages but do not contain meaningful page content on their own. If search engines index these URLs, they may:

- Create duplicate content signals
- Waste crawl budget on non-content pages
- Appear as low-quality pages in search results

## Solution 1: Using robots.txt

The simplest approach is to add a disallow rule to your site's `robots.txt` file to prevent search engine crawlers from accessing oEmbed paths.

Add the following lines to your `robots.txt` file:

```
# Disallow oEmbed media links
Disallow: /media/oembed
```

If your site uses the **RobotsTxt** module for managing `robots.txt` through the admin interface, navigate to **Configuration > Search and metadata > Robots.txt** and add the disallow rule there.

## Solution 2: Using Rabbit Hole Module

The **Rabbit Hole** module provides more granular control over how entity pages behave. It can be configured to prevent direct access to media entity pages entirely, redirecting visitors or returning a 403/404 response instead.

To configure Rabbit Hole for media entities:

1. Install and enable the Rabbit Hole module if it is not already enabled:

```bash
composer require drupal/rabbit_hole
drush en rabbit_hole rabbit_hole_media -y
```

2. Navigate to **Configuration > Content authoring > Rabbit Hole settings**.
3. Configure the behavior for **Media** entities.
4. Set the default action to **Page not found** or **Page redirect** to prevent direct access to media entity pages.

## Solution 3: Using Metatag noindex

You can also use the **Metatag** module to add a `noindex` meta tag to media entity pages:

1. Navigate to **Configuration > Search and metadata > Metatag**.
2. Edit the defaults for the **Media** entity type.
3. Under the **Advanced** section, set **Robots** to include `noindex, nofollow`.
4. Save the configuration.

This tells search engines not to index these pages even if they discover them through crawling.

## Recommended Approach

For most Varbase sites, combining the `robots.txt` disallow rule with the Metatag `noindex` approach provides the most robust protection. The `robots.txt` rule prevents crawlers from wasting crawl budget, while the `noindex` meta tag serves as a fallback if a crawler reaches the page through another path.
