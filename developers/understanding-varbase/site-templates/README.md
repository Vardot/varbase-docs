# Site Templates

A **site template** is a Drupal recipe of `type: Site`. It is the recipe you choose in the browser installer's **Choose a site template** step, and it composes a whole site out of smaller recipes: the base recipes, a theme, the pages, and the demo content.

A site template is applied **during** the site installation. It is not applied with `drush recipe` on a site that is already installed.

## Available Site Templates

| Site template                                            | Description                                                                                          |
| -------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| [Varbase Starter](varbase-starter.md) | Main site template recipe that orchestrates the full Varbase installation                            |
| [Educare](educare.md)                                    | Education site template for schools, universities, academies, and e-learning, on Vartheme BS5 Educare |
| [Horizon Aid](horizon-aid.md)                            | NGO and humanitarian site template for nonprofits, charities, foundations, and aid organizations, on Vartheme BS5 Horizon Aid |

## What a Site Template Owns

A site template composes the base recipes and adds what is its own: the theme, the pages, the patterns, and the demo content.

Content types come from the base recipes. [Varbase Page Base](../varbase-recipes/varbase-page-base.md), [Varbase Blog Base](../varbase-recipes/varbase-blog-base.md), [Varbase News Base](../varbase-recipes/varbase-news-base.md), and [Varbase Events Base](../varbase-recipes/varbase-events-base.md) each provide a content type with its fields, its listing, and its Drupal Canvas content templates. A site template does not repeat them.

## Writing Your Own

See [Creating your own recipe](../../extending-varbase/creating-your-own-recipe.md).
