# Site Templates

A **site template** is a Drupal recipe of `type: Site`. It composes a whole site out of smaller recipes: the base recipes, a theme, the pages, and the demo content. Vardot's site templates work on both Drupal CMS and the Varbase project.

A site template is applied **during** the site installation. It is not applied with `drush recipe` on a site that is already installed.

## Available Site Templates

| Site template | Description | Latest release | Demo |
| ------------- | ----------- | -------------- | ---- |
| [Varbase Starter](varbase-starter.md) | The default site template of Varbase 11, on Vartheme BS5 | 1.0.4 | [Site](https://demo.varbase.vardot.com/), [Storybook](https://storybook.demo.varbase.vardot.com/) |
| [Educare](educare.md) | Education site template for schools, universities, academies, and e-learning, on Vartheme BS5 Educare | 1.0.5 | [Site](https://educare.demos.vardot.com/) |
| [Horizon Aid](horizon-aid.md) | NGO and humanitarian site template for nonprofits, charities, foundations, and aid organizations, on Vartheme BS5 Horizon Aid | 1.0.5 | [Site](https://horizonaid.demos.vardot.com/) |
| [The Rightup](the-rightup.md) | Media, news, and magazine site template for newsrooms, publishers, and editorial teams, on Vartheme BS5 Rightup | 1.0.0 | [Site](https://rightup.demos.vardot.com/) |

## Installing a Site Template

- **On Drupal CMS**: require the template with Composer, then install the site with `drush site:install ../recipes/<recipe>`. Each template's page has the DDEV steps under **Set Up Locally on Drupal CMS With DDEV**.
- **On the Varbase project**: require the template with Composer, then select it in the browser installer's **Choose a site template** step, which lists every site template recipe in the project. Varbase Starter comes with the Varbase project.

{% hint style="info" %}
The Drupal CMS browser installer only offers the site templates on its curated list. Adding all four Vardot site templates to that list is proposed in [#3591475](https://git.drupalcode.org/project/drupal_cms/-/work_items/3591475), [#3591477](https://git.drupalcode.org/project/drupal_cms/-/work_items/3591477), [#3591478](https://git.drupalcode.org/project/drupal_cms/-/work_items/3591478), and [#3591479](https://git.drupalcode.org/project/drupal_cms/-/work_items/3591479). None of them is merged yet.
{% endhint %}

## What a Site Template Owns

A site template composes the base recipes and adds what is its own: the theme, the pages, the patterns, and the demo content.

Shared content types come from the base recipes. [Varbase Page Base](../varbase-recipes/varbase-page-base.md), [Varbase Blog Base](../varbase-recipes/varbase-blog-base.md), [Varbase News Base](../varbase-recipes/varbase-news-base.md), [Varbase Events Base](../varbase-recipes/varbase-events-base.md), and [Varbase Podcasts Base](../varbase-recipes/varbase-podcasts-base.md) each provide a content type with its fields, its listing, and its Drupal Canvas content templates. A site template does not repeat them.

A site template may still add a content type that only its kind of site needs, and then it owns that content type: **Educare** adds **Program**, and **Horizon Aid** adds **Country** and **Program**. Each template's page lists what it owns.

## Writing Your Own

See [Creating your own recipe](../../extending-varbase/creating-your-own-recipe.md).
