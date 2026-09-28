# Site Templates

A **site template** is a Drupal recipe of `type: Site`. It is what you choose in the installer's **Choose a site template** step, and it composes a whole site out of smaller recipes: the base recipes, a theme, the pages, and the demo content. Vardot's site templates work on both Drupal CMS and the Varbase project.

A site template is applied **during** the site installation. It is not applied with `drush recipe` on a site that is already installed.

## Available Site Templates

| Site template | Description | Latest release | Demo |
| ------------- | ----------- | -------------- | ---- |
| [Varbase Starter](varbase-starter.md) | The default site template of Varbase 11, on Vartheme BS5 | 1.0.4 | [Site](https://demo.varbase.vardot.com/), [Storybook](https://storybook.demo.varbase.vardot.com/) |
| [Educare](educare.md) | Education site template for schools, universities, academies, and e-learning, on Vartheme BS5 Educare | 1.0.5 | [Site](https://educare.demos.vardot.com/) |
| [Horizon Aid](horizon-aid.md) | NGO and humanitarian site template for nonprofits, charities, foundations, and aid organizations, on Vartheme BS5 Horizon Aid | 1.0.5 | [Site](https://horizonaid.demos.vardot.com/) |
| [The Rightup](the-rightup.md) | Media, news, and magazine site template for newsrooms, publishers, and editorial teams, on Vartheme BS5 Rightup | 1.0.0 | [Site](https://rightup.demos.vardot.com/) |

## Installing a Site Template

- **On Drupal CMS**: all four are listed in the Drupal CMS installer. Create a Drupal CMS project, open it in the browser, and choose the template on the **Choose a site template** step. Each card is **Created by Vardot** and links to Learn more, Demo and Documentation. Varbase Starter's card is named **Varbase**.
- **Scripted or CI installs**: require the template with Composer, then install the site with `drush site:install ../recipes/<recipe>`.
- **On the Varbase project**: require the template with Composer, then select it in the Varbase installer's **Choose a site template** step, which lists every site template recipe in the project. Varbase Starter comes with the Varbase project.

Each template's page has the DDEV steps for all three.

```bash
mkdir my-drupal-site && cd my-drupal-site
ddev config --project-type=drupal11 --docroot=web
ddev composer create-project drupal/cms
ddev launch
```

<figure><img src="../../../.gitbook/assets/Site Templates - Drupal CMS Installer - Choose a Site Template.png" alt="The Choose a site template step of the Drupal CMS installer, with the Blank, Starter and Byte templates at the top"><figcaption><p>The Choose a Site Template Step in the Drupal CMS Installer</p></figcaption></figure>

<figure><img src="../../../.gitbook/assets/Site Templates - Drupal CMS Installer - Vardot Site Templates.png" alt="The Varbase, The Rightup, Educare and Horizon Aid cards in the Drupal CMS installer, each created by Vardot, next to other site templates"><figcaption><p>The Vardot Site Templates in the Drupal CMS Installer</p></figcaption></figure>

## What a Site Template Owns

A site template composes the base recipes and adds what is its own: the theme, the pages, the patterns, and the demo content.

Shared content types come from the base recipes. [Varbase Page Base](../varbase-recipes/varbase-page-base.md), [Varbase Blog Base](../varbase-recipes/varbase-blog-base.md), [Varbase News Base](../varbase-recipes/varbase-news-base.md), [Varbase Events Base](../varbase-recipes/varbase-events-base.md), and [Varbase Podcasts Base](../varbase-recipes/varbase-podcasts-base.md) each provide a content type with its fields, its listing, and its Drupal Canvas content templates. A site template does not repeat them.

A site template may still add a content type that only its kind of site needs, and then it owns that content type: **Educare** adds **Program**, and **Horizon Aid** adds **Country** and **Program**. Each template's page lists what it owns.

## Writing Your Own

See [Creating your own recipe](../../extending-varbase/creating-your-own-recipe.md).
