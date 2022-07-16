# Understanding The Vartheme Base Theme

## Vartheme BS4: Varbase Theme (Bootstrap 4 - SASS)

A base theme for [**Varbase**](https://www.drupal.org/project/varbase) standard websites.

Based on the [**Bootstrap Barrio**](https://www.drupal.org/project/bootstrap\_barrio) theme (**Bootstrap 4** - SASS).

Mostly base Varbase layouts and styling of components are managed in the **Vartheme BS4** base theme.

Customizing for a project? keep using the **Vartheme BS4** base theme by:

{% content-ref url="creating-your-own-theme.md" %}
[creating-your-own-theme.md](creating-your-own-theme.md)
{% endcontent-ref %}

A sub theme could be generated automatically to start with. Installed and set as default theme for a website. Changes over coloring, theming, having custom web components, adding more libraries would be managed under the new sub theme, without changing the base theme.

This way a guaranteed full integration between **Varbase components** and **Varbase themes**.

## Varbase Components and SMACSS

All **Varbase** components organize CSS files under libraries with full use of [SMACSS](http://smacss.com/book/) in mind.

> ### [Scalable and Modular Architecture for CSS](http://smacss.com/)
>
> #### A flexible guide to developing sites small and large.
>
> SMACSS (pronounced “smacks”) is more style guide than rigid framework. There is no library within here for you to download or install. SMACSS is a way to examine your design process and as a way to fit those rigid frameworks into a flexible thought process. It is an attempt to document a consistent approach to site development when using CSS.

{% hint style="info" %}
Inspected for Varbase components with basic or no styling to look better when Vartheme BS4 or a sub theme of it was the default theme for the site.
{% endhint %}

## Vartheme BS4 theme and SMACSS

**Vartheme BS4** too organize CSS files under libraries with full use of [SMACSS](http://smacss.com/book/) in mind.

{% hint style="info" %}
Have a look at the **SCSS** and **CSS** folders

**SCSS:** [https://git.drupalcode.org/project/vartheme\_bs4/-/tree/9.0.x/scss](https://git.drupalcode.org/project/vartheme\_bs4/-/tree/9.0.x/scss)

**CSS:** [https://git.drupalcode.org/project/vartheme\_bs4/-/tree/9.0.x/css](https://git.drupalcode.org/project/vartheme\_bs4/-/tree/9.0.x/css)
{% endhint %}



## Drupal SMACSS

**Drupal** follows a **SMACSS-style** categorization of its CSS rules:

1. **Base** — CSS reset/normalize plus HTML element styling.
2. **Layout** — macro arrangement of a web page, including any grid systems.
3. **Component** — discrete, reusable UI elements.
4. **State** — styles that deal with client-side changes to components.
5. **Theme** — purely visual styling (“look-and-feel”) for a component.



{% hint style="info" %}
Refer to Drupal.org standards for CSS file organization (for Drupal 9)

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
Browse the list of all **Bootstrap 4** components

[https://getbootstrap.com/docs/4.6/components](https://getbootstrap.com/docs/4.6/components)
{% endhint %}

## Vartheme BS4 Theme Custom Components CSS Classes

* ``[**.bs-callout**](https://git.drupalcode.org/project/vartheme\_bs4/-/blob/9.0.x/scss/components/bs-callouts.component.scss) : Bootstrap callouts. Have the Bootstrap styling for call outs component.
* ``[**.vb-tags**](https://git.drupalcode.org/project/vartheme\_bs4/-/blob/9.0.x/scss/components/vb-tags.component.scss) : Styles a list of tags, which much looks like the pager with rounded borders.

## Vartheme BS4 Theme Custom Layouts CSS Classes

* ****[**.bg-edge2edge**](https://git.drupalcode.org/project/vartheme\_bs4/-/blob/9.0.x/scss/layout/edge2edge.layout.scss) : Edge to Edge layout for content.
* ****[**.equal-height**](https://git.drupalcode.org/project/vartheme\_bs4/-/blob/9.0.x/scss/layout/equal-height.layout.scss) **** : **** Equal height layout for bootstrap rows. ( variations with _**`-sm`**_, **`-md`**, **`-lg`**, and **`-xl`** ) will work within the Bootstrap default breakpoints for the theme.



## Example Varbase Custom Components

* `.varbase-heroslider-media` : [**Varbase Hero slider media**](https://www.drupal.org/project/varbase\_heroslider\_media) style.
* ****[**View Modes Inventory - Bootstrap Ready**](https://www.drupal.org/project/vmi) **:** Number of view mode components, layouts, and themes, which you can copy from the module and custom for each content type. ( Have a look at [Using the VMI ](../configuring-a-varbase-site/using-view-modes-inventory.md))
