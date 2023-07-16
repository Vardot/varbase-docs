# Understanding The Vartheme Starterkit Theme

## Vartheme BS5: Varbase Theme (Bootstrap 5 - SASS)

A starterkit theme for [**Varbase**](https://www.drupal.org/project/varbase) standard websites.

A new generation of theming based on [**Bootstrap \~5.3.0**](https://getbootstrap.com/), [**Single Directory Components (SDC)**](https://www.drupal.org/docs/develop/theming-drupal/using-single-directory-components) with [**Drupal `~10.1.0`**](https://www.drupal.org/project/drupal/releases/10.1.0-alpha1), and [**UI Patterns**](https://www.drupal.org/project/ui\_patterns) **`2.0.x-dev`**.

[**Varbase Components**](https://www.drupal.org/project/varbase\_components) provides component management system for **Varbase** and **Vartheme BS5**.

Customizing for a project? keep generate a clone of the **Vartheme BS5 starterkit** theme by:

{% content-ref url="creating-your-own-theme.md" %}
[creating-your-own-theme.md](creating-your-own-theme.md)
{% endcontent-ref %}

A generated cloned theme could be generated automatically to start with. Installed and set as default theme for a website. Changes over coloring, theming, having custom web components, adding more libraries would be managed under the new sub theme, without changing the base theme.

This way a guaranteed full integration between **Varbase Components** and **Varbase Themes**.

## Varbase Components module, SDC and SMACSS

All **Varbase** components organize CSS files under libraries with full use of [SMACSS](http://smacss.com/book/) in mind.

> ### [Scalable and Modular Architecture for CSS](http://smacss.com/)
>
> #### A flexible guide to developing sites small and large.
>
> SMACSS (pronounced “smacks”) is more style guide than rigid framework. There is no library within here for you to download or install. SMACSS is a way to examine your design process and as a way to fit those rigid frameworks into a flexible thought process. It is an attempt to document a consistent approach to site development when using CSS.

{% hint style="info" %}
Inspected for **Varbase Components** with basic or no styling to look better when **Vartheme BS5** or a generated clone theme of it was the default theme for the site.
{% endhint %}

## Vartheme BS5 starterkit theme, SDC and SMACSS

**Vartheme BS5** too organize CSS files under libraries with full use of [SMACSS](http://smacss.com/book/) in mind.

{% hint style="info" %}
Have a look at the **SCSS** and **CSS** folders

**SCSS:** [https://git.drupalcode.org/project/vartheme\_bs5/-/tree/3.0.x/scss](https://git.drupalcode.org/project/vartheme\_bs5/-/tree/3.0.x/scss)

**CSS:** [https://git.drupalcode.org/project/vartheme\_bs5/-/tree/3.0.x/css](https://git.drupalcode.org/project/vartheme\_bs5/-/tree/3.0.x/css)
{% endhint %}

{% hint style="info" %}
NOTE: **Components** was moved to be included with **Single Directory Components (SDC)** components folder.

Using the default components from [**Varbase Components**](https://www.drupal.org/project/varbase\_components).

Copy components from Varbase Components to have a custom change over the template, style, or script.
{% endhint %}



## Drupal SMACSS

**Drupal** follows a **SMACSS-style** categorization of its CSS rules:

1. **Base** — CSS reset/normalize plus HTML element styling.
2. **Layout** — macro arrangement of a web page, including any grid systems.
3. **Component** — discrete, reusable UI elements.
4. **State** — styles that deal with client-side changes to components.
5. **Theme** — purely visual styling (“look-and-feel”) for a component.



{% hint style="info" %}
Refer to Drupal.org standards for CSS file organization (for Drupal 10)

[https://www.drupal.org/docs/develop/standards/css/css-file-organization-for-drupal-9](https://www.drupal.org/docs/develop/standards/css/css-file-organization-for-drupal-9)
{% endhint %}

{% hint style="info" %}
Refer to Drupal.org standards for CSS architecture

[https://www.drupal.org/docs/develop/standards/css/css-architecture-for-drupal-9](https://www.drupal.org/docs/develop/standards/css/css-architecture-for-drupal-9)
{% endhint %}

## Bootstrap Framework

Build fast, responsive sites with Bootstrap.

Quickly design and customize responsive mobile-first sites with Bootstrap, the world’s most popular front-end open source toolkit, featuring Sass variables and mixins, responsive grid system, extensive prebuilt components, and powerful JavaScript plugins.

{% hint style="info" %}
Browse the list of all **Bootstrap \~5.3.0** components

[https://getbootstrap.com/docs/5.3/components](https://getbootstrap.com/docs/5.3/components)
{% endhint %}



## Vartheme BS5 Theme Custom Layouts CSS Classes

* [**.bg-edge2edge**](https://git.drupalcode.org/project/vartheme\_bs5/-/blob/3.0.x/scss/layout/edge2edge.layout.scss) : Edge to Edge layout for content.
* [**.equal-height**](https://git.drupalcode.org/project/vartheme\_bs5/-/blob/3.0.x/scss/layout/equal-height.layout.scss) : Equal height layout for bootstrap rows. ( variations with _**`-sm`**_, **`-md`**, **`-lg`**, and **`-xl`** ) will work within the Bootstrap default breakpoints for the theme.
