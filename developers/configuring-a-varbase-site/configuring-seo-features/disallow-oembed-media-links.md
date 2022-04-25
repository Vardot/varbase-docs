# Disallow Oembed media links

Search engines are indexing the `media/oembed` links in websites\
And the search results for the oembed remote media can be viewed in search results\
Then a landing page will open with only the content of the remote media in it.

> Include Oembed media link in the `robots.txt` to be disallowed
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
> This is a repetitive issue that the support team faces when starting the handover process

Drupal core [robots.txt](https://git.drupalcode.org/project/drupal/-/blob/9.3.x/robots.txt) file dose not have the `Disallow: /media/oembed`\
and only following with [http://www.robotstxt.org/robotstxt.html](http://www.robotstxt.org/robotstxt.html)



Waiting on the Drupal core [#3271222: Include Disallow Oembed media links in the robots.txt file for better Drupal SEO](https://www.drupal.org/project/drupal/issues/3271222) to be committed.

## Add line Disallow Media Oembed in Old Projects

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

* Add the following `append` for for the `file-mapping` in [**Varbase Project**](https://github.com/vardot/varbase-project) template

```php
      "file-mapping": {
        "[web-root]/robots.txt": {
          "append": "docroot/profiles/varbase/src/assets/varbase-robots-additions.txt"
        }
      }
```

* **Projects may change the "append": `"docroot/profiles/varbase/src/assets/varbase-robots-additions.txt"` to their custom robots-additions.txt file.**

[Include Disallow Oembed media link in the robots.txt for Varbase Project template #136](https://github.com/Vardot/varbase-project/issues/136)

* File an issue to Drupal core to add `Disallow: /media/oembed` in the [robots.txt](https://git.drupalcode.org/project/drupal/-/blob/9.3.x/robots.txt) file
