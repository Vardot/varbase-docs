# Disallow Oembed Media Links

Search engines are indexing the `media/oembed` links in websites. And the search results for the Oembed remote media can be viewed in search results. Then a landing page will open with only the content of the remote media in it.

> ### Current Status In Every Project&#x20;
>
> Developers add the following Oembed media link in the `robots.txt` to be disallowed
>
> ```php
> # Oembed media
> Disallow: /media/oembed
> Disallow: /en/media/oembed
> Disallow: /fr/media/oembed
> Disallow: /es/media/oembed
> Disallow: /ar/media/oembed
> ```
>
>

{% hint style="danger" %}
This is a repetitive issue that the support team faces when starting the handover process to push a site to production before launching a project.
{% endhint %}

**Drupal** core [robots.txt](https://git.drupalcode.org/project/drupal/-/blob/9.3.x/robots.txt) file does not have the `Disallow: /media/oembed`\
and only following with [http://www.robotstxt.org/robotstxt.html](http://www.robotstxt.org/robotstxt.html)

{% hint style="warning" %}
Waiting on the Drupal core issue [#3271222: Include Disallow Oembed media links in the robots.txt file for better Drupal SEO](https://www.drupal.org/project/drupal/issues/3271222) to be committed.
{% endhint %}

## Adding Disallow Media Oembed in Old Projects

As of **Varbase 9.0.6** and later do not need to do any work on this part.

If the project was built from **Varbase 9.0.5** and older versions need to do the following steps:

> Add line “`Disallow: /media/oembed`“ to be configured from Varbase to be always included in `robots.txt`\
> Regarding the other languages will be dealt with by the delivery team to add the variation according to the available languages on the website

* Add the following in `src/assets/varbase-robots-additions.txt` file

```php
# Varbase Robots additions to Robots.txt
# --------------------------------------
# Oembed media
Disallow: /media/oembed
Disallow: /*/media/oembed
```

* Add the following `append` for for the `file-mapping` in [**Varbase Project**](https://github.com/vardot/varbase-project) template. To make sure it will be added, even if the robots.txt was changed or updated.

```php
      "file-mapping": {
        "[web-root]/robots.txt": {
          "append": "docroot/profiles/varbase/src/assets/varbase-robots-additions.txt"
        }
      }
```

{% hint style="success" %}
**Projects may change the "append": `"docroot/profiles/varbase/src/assets/varbase-robots-additions.txt"` to their custom robots-additions.txt file.**
{% endhint %}

Updated the default Varbase Project with the [Include Disallow Oembed media link in the robots.txt for Varbase Project template #136](https://github.com/Vardot/varbase-project/issues/136) issue.

{% hint style="info" %}
When the Drupal core issue [#3271222: Include Disallow Oembed media links in the robots.txt file for better Drupal SEO](https://www.drupal.org/project/drupal/issues/3271222) is committed. The old setup could be changed to follow the new Drupal core standard rogots.txt&#x20;
{% endhint %}
