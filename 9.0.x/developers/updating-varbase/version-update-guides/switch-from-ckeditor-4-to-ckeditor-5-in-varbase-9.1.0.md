# Switch from CKEditor 4 to CKEditor 5 in Varbase \~9.1.0

{% hint style="danger" %}
[**CKEditor 4 - WYSIWYG HTML editor**](https://www.drupal.org/project/ckeditor)\
Project not supported: This project is no longer supported, and is no longer available for download. Disabling everything included by this project is strongly recommended!
{% endhint %}

<figure><img src="../../../.gitbook/assets/Available-updates-test-varbase91t1.png" alt=""><figcaption><p>Not Supported Message in Old Sites, Which Still Using CKEditor 4</p></figcaption></figure>

## Follow with steps to update to Varbase \~9.1.0

{% content-ref url="updating-varbase-9.0-to-drupal-10.md" %}
[updating-varbase-9.0-to-drupal-10.md](updating-varbase-9.0-to-drupal-10.md)
{% endcontent-ref %}

## Complete update to Drupal 10 with CKEditor 4

Use `"Vardot/varbase-patches": "~9.1.0"` in the **root** `composer.json` file.

> with **Varbase `~9.1.0`** **CKEditor `4`** and **Drupal `10`**

{% hint style="info" %}
**To keep using CKEditor 4** you need the following in the **root** `composer.json` file

`"vardot/varbase-patches": "~9.1.0"`

`"drupal/varbase_editor": "~9.1.0"`
{% endhint %}

## Switch Varbase Patches from \~9.1.0 to \~9.2.0

Use `"Vardot/varbase-patches": "~9.2.0"` in the **root** `composer.json` file.

> with **Varbase `~9.1.0`** **CKEditor `5`** and **Drupal `10`**

{% hint style="info" %}
Make sure to have the following in your system:

`"vardot/varbase-patches": "~9.2.0"`

&#x20;`"drupal/varbase_editor": "~9.2.0"`
{% endhint %}

Default **Varbase `9.1.x`** is using **Varbase `9.2.x`** with **CKEditor 5**

{% hint style="success" %}
✅ Released [**varbase\_editor-9.2.0**](https://www.drupal.org/project/varbase\_editor/releases/9.2.0)



* Issue [#3442752](https://www.drupal.org/i/3442752): Started a new `9.2.x` branch for **Varbase Editor** to support **CKEditor 5** and drop support for CKEditor 4
* having the following
  * <mark style="color:blue;">Started a new</mark> <mark style="color:blue;"></mark><mark style="color:blue;">`9.2.x`</mark> <mark style="color:blue;"></mark><mark style="color:blue;">branch for</mark> <mark style="color:blue;"></mark><mark style="color:blue;">**Varbase Editor**</mark>
  * <mark style="color:blue;">Switched to</mark> <mark style="color:blue;"></mark><mark style="color:blue;">**CKEditor 5**</mark> <mark style="color:blue;"></mark><mark style="color:blue;">and drop support for</mark> <mark style="color:blue;"></mark><mark style="color:blue;">**CKEditor 4**</mark>
  * <mark style="color:blue;">Enabled the</mark> <mark style="color:blue;"></mark><mark style="color:blue;">**CKEditor 5**</mark> <mark style="color:blue;"></mark><mark style="color:blue;">module</mark> <mark style="color:blue;"></mark> <mark style="color:blue;"></mark><mark style="color:blue;">`- drupal:ckeditor5`</mark>
  * <mark style="color:blue;">Removed</mark> <mark style="color:blue;"></mark><mark style="color:blue;">`"drupal/ckeditor": "~1",`</mark> <mark style="color:blue;"></mark><mark style="color:blue;">from the</mark> <mark style="color:blue;"></mark><mark style="color:blue;">`composer.json`</mark> <mark style="color:blue;"></mark><mark style="color:blue;">file.</mark>
  * <mark style="color:blue;">Changed to</mark> <mark style="color:blue;"></mark><mark style="color:blue;">`"vardot/varbase-patches": "~9.2.0",`</mark>
  * <mark style="color:blue;">Changed to</mark> <mark style="color:blue;"></mark><mark style="color:blue;">`"drupal/anchor_link": "~3",`</mark>
  * <mark style="color:blue;">Changed to</mark> <mark style="color:blue;"></mark><mark style="color:blue;">`"drupal/ckeditor_media_embed": "~2",`</mark>
* Issue [#3414834](https://www.drupal.org/i/3414834): Switched default config for **Rich editor** and **Simple editor** from **CKEditor 4** to **CKEditor 5**
*   Issue [#3442854](https://www.drupal.org/i/3442854): Added **CKEditor 5 Paste Filter** module to Varbase Editor&#x20;

    > Filter content pasted into the CKEditor 5 visual editor by searching and replacing with the power of regular expressions.

    This is a CKEditor 5 version of [CKEditor Paste Filter](https://www.drupal.org/project/ckeditor\_paste\_filter) with additional features, most notably that the filters are fully configurable via a form interface and the filters can be configured individually for each text format. This module has been created as a separate project so that sites that are transitioning over to CKEditor 5 can have both modules installed easily, and to allow this project to evolve without needing to maintain compatibility with both CKEditor 4 and 5.
* Issue [#3445309](https://www.drupal.org/i/3445309): Removed **CKEditor 4** `dependencies`/`install` for full switch to **CKEditor 5** in **Varbase Editor**
  * Removed CKEditor 4 dependencies or any install
  * Removed `"drupal/ckeditor_paste_filter": "~1",` from the `composer.json` file.
  * Removed`"drupal/image_resize_filter": "~1",` from the `composer.json` file.
*   Issue [#3445408](https://www.drupal.org/i/3445408): Added **CKEditor 5** and **ACE** libraries using [asset-packagist.org](https://asset-packagist.org/) in **Varbase Editor**

    <pre class="language-php"><code class="lang-php">"npm-asset/ace-builds": "~1",
    "npm-asset/northernco--ckeditor5-anchor-drupal": "^0.4.0",
    "npm-asset/ckeditor--ckeditor5-media-embed": "*"

    <a data-footnote-ref href="#user-content-fn-1">Old projects needs to add the following under</a>
    <a data-footnote-ref href="#user-content-fn-2"> "installer-paths": { </a>
    <a data-footnote-ref href="#user-content-fn-3"> in the root composer.json file for the project</a>

    "docroot/libraries/ace": ["npm-asset/ace-builds"],
    "docroot/libraries/ckeditor5-anchor-drupal": ["npm-asset/northernco--ckeditor5-anchor-drupal"],
    "docroot/libraries/ckeditor5/plugins/media-embed": ["npm-asset/ckeditor--ckeditor5-media-embed"],

    <a data-footnote-ref href="#user-content-fn-4">Also needs to add the following under</a>
    <a data-footnote-ref href="#user-content-fn-5"> "drupal-libraries": {</a>

    {"name": "ace", "package": "npm-asset/ace-builds"},
    {"name": "ckeditor5-anchor-drupal", "package": "npm-asset/northernco--ckeditor5-anchor-drupal"},
    {"name": "ckeditor5-media-embed", "package": "npm-asset/ckeditor--ckeditor5-media-embed"}
    </code></pre>
{% endhint %}

[^1]: 

[^2]: 

[^3]: 

[^4]: 

[^5]: 
