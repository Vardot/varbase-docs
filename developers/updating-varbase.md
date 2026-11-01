# Updating Varbase

How to update a Varbase 11.0.x site, and what an update does and does not change.

## Update Within Varbase 11.0.x

Varbase 11.0.x is updated with Composer, like any Drupal project:

```bash
ddev composer update --with-all-dependencies
ddev drush updatedb -y
ddev drush cache:rebuild
ddev drush config:export -y
```

Commit `composer.json`, `composer.lock` and the exported configuration together.

The project template pins Drupal core to `~11.4.0` and the Varbase profile to `~11.0.0`, so `composer update` stays on Drupal 11.4 and Varbase 11.0. A move to a newer Drupal core minor comes with a Varbase release that allows it.

## Recipes Are Applied Once

A recipe changes the site when it is applied. Updating a recipe package later downloads the new version into `recipes/`, but **does not apply it again**. Recipes have no update paths, as the [Drupal CMS 2.0.0 release notes](https://www.drupal.org/project/cms/releases/2.0.0) also point out. New configuration, permissions or content in a recipe update do not reach a site that already applied the recipe.

To pick up a change from a recipe update:

1. Read the recipe's release notes on its Drupal.org project page.
2. Make the change on your site by hand, or in your own update hook or recipe.
3. Or reapply the recipe. Project Browser shows **Reapply** for an installed recipe, and `ddev drush recipe ../recipes/<recipe_name>` does the same. Reapplying runs the recipe's config actions again, so try it on a copy of the site first.

The same is true for site templates such as **Varbase Starter**: they are applied once, during installation.

## Patches During Updates

The project sets `composer-exit-on-patch-failure: true`, so a patch that no longer applies stops `composer update`. When that happens, check whether the fix is already in the new release, then ignore the patch with `patches-ignore`. See [Varbase Patches](varbase-patches.md).

## Modules That Moved to the Varbase Profile

In Varbase 11.0.0, **Entity Clone**, **Rabbit Hole**, **Ultimate Cron** and **Advanced Text Formatter** moved from the base recipes to the **Varbase** profile, because they have no stable release yet ([#3621480](https://www.drupal.org/i/3621480)). A site that already has them keeps them. A new site gets the code but not the modules enabled.

## Upgrading From Varbase 10.x

No in-place upgrade path from Varbase 10.x to Varbase 11.0.x is published. Varbase 11 replaces the Varbase modules with recipes, so the recommended approach is to build a new Varbase 11 site and migrate the content with Drupal's Migrate API or another migration tool.

To keep a Varbase 10.x site up to date in the meantime, follow the update guides in the [Varbase 10.1.x documentation](https://docs.varbase.vardot.com/10.1.x/developers/updating-varbase).
