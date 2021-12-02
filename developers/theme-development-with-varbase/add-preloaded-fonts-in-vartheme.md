# Add Preloaded Fonts in Vartheme



{% hint style="info" %}
* [Preload critical assets to improve loading speed](https://web.dev/preload-critical-assets/)
* [Preload W3C Candidate Recommendation 26 June 2019](https://www.w3.org/TR/preload/)
{% endhint %}

Following the new way in the new **Drupal** default front end theme [**Olivero**](https://www.drupal.org/project/olivero)\
`{% include '@olivero/includes/preload.twig' with { olivero_path: olivero_path } only %}`

{% hint style="info" %}
Check the code on [**Olivero**](https://www.drupal.org/project/olivero)&#x20;

The **html.html.twig** file [https://git.drupalcode.org/project/drupal/-/blob/9.2.x/core/themes/olivero/templates/layout/html.html.twig#L43](https://git.drupalcode.org/project/drupal/-/blob/9.2.x/core/themes/olivero/templates/layout/html.html.twig#L43)

The **preload.twig** file [https://git.drupalcode.org/project/drupal/-/blob/9.2.x/core/themes/olivero/templates/includes/preload.twig](https://git.drupalcode.org/project/drupal/-/blob/9.2.x/core/themes/olivero/templates/includes/preload.twig)
{% endhint %}

Having the following in **Vartheme BS4** and **VARTHEM\_BS4\_SUBTHEME**. And the include.

```
{%- include '@vartheme_bs4/includes/preload.twig' with { vartheme_bs4_path: vartheme_bs4_path, html_dir: html_attributes['dir'] } only -%}

```

```
{%- include '@VARTHEME_BS4_SUBTHEME/includes/preload.twig' with { VARTHEME_BS4_SUBTHEME_path: VARTHEME_BS4_SUBTHEME_path, html_dir: html_attributes['dir'] } only -%}
```

\
Custom Vartheme Sub Themes are able to add their preloaded assets on demand.

## Steps to Add a New Web Font

### 1. Add Web Font Files in the Fonts Folder

**Example:** The [**Lora**](https://fonts.google.com/specimen/Lora) font

* Go to the [**Lora**](https://fonts.google.com/specimen/Lora) web font page and Download the family.

{% hint style="info" %}
Download directly from [fonts.google.com](https://fonts.google.com/specimen/Lora#glyphs) or from the source in [github.com](https://github.com/cyrealtype/Lora-Cyrillic)

[https://github.com/cyrealtype/Lora-Cyrillic](https://github.com/cyrealtype/Lora-Cyrillic)
{% endhint %}

* Check the license before using the web font

> These fonts are licensed under the [Open Font License](https://scripts.sil.org/cms/scripts/page.php?site\_id=nrsi\&id=OFL).
>
> You can use them freely in your products & projects - print or digital, commercial or otherwise.
>
> This isn't legal advice, please consider consulting a lawyer and see the full license for all details.

{% hint style="danger" %}
**Not recommended to use not licensed font!**

Buy a license if it was possible and budget for a unique branded font.

Or hire a typography font designer.
{% endhint %}

* Copy the list of web font files to `"PROJECT_PATH/themes/custom/MYTHEME/fonts/lora/webfonts"`
* Create the `"PROJECT_PATH/themes/custom/MYTHEME/fonts/lora/css/lora.css"` file
* Define the `@font-face` for the Lora font.&#x20;

```
/*
 * Lora https://fonts.google.com/specimen/Lora
 */
 @font-face {
  font-family: 'Lora';
  font-style: normal;
  font-weight: 400;
  src: url(../webfonts/Lora-Regular.ttf) format('truetype');
}
@font-face {
  font-family: 'Lora';
  font-style: normal;
  font-weight: 700;
  src: url(../webfonts/Lora-Bold.ttf) format('truetype');
}
```

Having more file formats if that was available by [web font conversion tools](https://www.google.com/search?q=webfont+converter+tools\&newwindow=1\&client=ubuntu\&biw=1864\&bih=851\&sxsrf=ALeKk01rUKpiornNNqbuM8ibJ2Rhr7aaIw%3A1629794566305\&ei=BrEkYd74Eb2C9u8Puc6ouAM\&oq=webfont+converter+tools\&gs\_lcp=Cgdnd3Mtd2l6EAM6BwgAEEcQsANKBAhBGABQpUpYpUpgoV1oAXACeACAAZEBiAGKApIBAzAuMpgBAKABAcgBCMABAQ\&sclient=gws-wiz\&ved=0ahUKEwjek7nxocnyAhU9gf0HHTknCjcQ4dUDCA8\&uact=5)

```
  src: url(../webfonts/Lora-Regular.eot);
  src: url(../webfonts/Lora-Regular.eot?#iefix) format('embedded-opentype'),
       url(../webfonts/Lora-Regular.woff2) format('woff2'),
       url(../webfonts/Lora-Regular.woff) format('woff'),
       url(../webfonts/Lora-Regular.ttf) format('truetype');
```

{% hint style="danger" %}
For sure including a remote web font, But issues with preloading may start follow up
{% endhint %}

### 2. Add the @font-face CSS File to a Library

**Example:** The [**Lora**](https://fonts.google.com/specimen/Lora) font

* List the `"PROJECT_PATH/themes/custom/MYTHEME/fonts/lora/css/lora.css"` file in libraries to be activated in the theme

```
global-styles:
  css:
    theme:
      fonts/lora/css/lora.css: {}
```

### 3. Add the Font to The preload.twig File

{% hint style="success" %}
Recommended to add for faster loading of font in pages
{% endhint %}

* Edit the `"PROJECT_PATH/themes/custom/MYTHEME/templates/includes/preload.twig"` file. Add the link rel preload and the patch to the font file with `as="font"` and `type`

```
<link rel="preload" href="/{{ vartheme_bs4_path }}/fonts/lora/Lora-Regular.ttf" as="font" type="font/tff" crossorigin="anonymous">
```

### 4. Clear Cache And Test The Font

## Content of the Preload.twig File

{% hint style="success" %}
Change the logic in this file in the generated theme for the project. To match the need of your website.
{% endhint %}

### Available Variables

* **`vartheme_bs4_path`**: Returns the path to the Vartheme BS4 theme. In the Vartheme Sub theme, the variable could be `mythemename_path`
* **`html_dir`:** contains the language direction. It will either be 'ltr' or 'rtl'.

{% hint style="info" %}
### **Example of logic:**

* Multilingual websites may use a language selection for preloaded assets.
* Sections of the website may have a custom prelead assets for CSS/JS.
* Have a look at "Preload critical assets to improve loading speed" [https://web.dev/preload-critical-assets/](https://web.dev/preload-critical-assets/) for more ideas on what/when/where to use preload.
{% endhint %}

### Links to Learn by Example

{% hint style="info" %}
Check the following links:&#x20;

Vartheme **Fonts** folder:

[https://git.drupalcode.org/project/vartheme\_bs4/-/tree/9.0.x/fonts](https://git.drupalcode.org/project/vartheme\_bs4/-/tree/9.0.x/fonts)

**Vartheme html.html.twig file:** [https://git.drupalcode.org/project/vartheme\_bs4/-/blob/9.0.x/templates/includes/preload.twig](https://git.drupalcode.org/project/vartheme\_bs4/-/blob/9.0.x/templates/includes/preload.twig)

**Vartheme  preload.twig file:** [https://git.drupalcode.org/project/vartheme\_bs4/-/blob/9.0.x/templates/includes/preload.twig](https://git.drupalcode.org/project/vartheme\_bs4/-/blob/9.0.x/templates/includes/preload.twig)
{% endhint %}
