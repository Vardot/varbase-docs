# Varbase AI Readable Base

The **Varbase AI Readable Base** recipe makes the site easier for AI tools to read. It serves `/llms.txt`, built from the site name, slogan, main menu and footer menu. It also serves a Markdown version of every content item and taxonomy term, at `<path>.md`. The HTML pages do not change.

## Recipe Type

Varbase AI

## Drupal.org Project

[https://www.drupal.org/project/varbase\_ai\_readable\_base](https://www.drupal.org/project/varbase_ai_readable_base)

{% hint style="warning" %}
**Alpha release.** The modules it installs, **llms.txt** and **Markdownify**, are stable. This recipe is not covered by the Drupal security advisory policy. Try it on a development site first.
{% endhint %}

## What It Adds

- Installs **llms.txt** and **Markdownify**, with Markdown at a path alias plus `.md`.
- Builds `/llms.txt` from the main and footer menus.
- Lets **SEO Admin** and **Site Admin** manage the `llms.txt` content.

## Before You Apply

It needs no AI provider or key. **Varbase AI Base** is not required.

## Installation

Add the recipe with Composer, then apply it with Drush:

```bash
ddev composer require drupal/varbase_ai_readable_base:~1
ddev drush cr
ddev drush recipe ../recipes/varbase_ai_readable_base
ddev drush cr
```

{% hint style="warning" %}
**One line in `settings.php` is required.** Varbase ships **Fast 404**, which answers every `.txt` path with a 404. Add `/llms.txt` as an exception:

```php
$settings['fast404_exts'] = '/^(?!\/robots)^(?!\/llms\.txt$)^(?!\/system\/files).*\.(txt|png|gif|jpe?g|css|js|ico|swf|flv|cgi|bat|pl|dll|exe|asp)$/i';
```

Check it with a real request: `curl -sI https://<site>/llms.txt`.
{% endhint %}

Drupal Canvas pages and Views have no Markdown version yet. They are listed in `/llms.txt` as links.

## What a Site Answers

| Request | Answer |
|---|---|
| `/llms.txt` | Markdown, listing the main and footer menu links. |
| `/node/<nid>.md`, `/<alias>.md`, or a content or term page asked for with `Accept: text/markdown` | Markdown, marked `noindex` for search engines. |
| The same page without that header | HTML, as before. |
| `/robots.txt` | Unchanged. |
| Any other `.txt` path | Still a fast 404. |

Pages, book pages and announcements are turned into Markdown from their `search_index` view mode, the content without the page layout. Other content types use the full view mode, so their Markdown can include page parts such as the breadcrumb and share links.

## Troubleshooting

- Clear the cache before applying, or the apply fails with `"llms_txt" is not a known module or theme`.
- `/llms.txt` answers 404 until the `settings.php` line above is in.
- Asking for Markdown of a Canvas page or a View answers 406.
