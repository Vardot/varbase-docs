# Updating from Varbase 10.x to 11.x

There is currently **no supported update or upgrade path** from Varbase 10.x to Varbase 11.x.

## Why There Is No Migration Path

Varbase 11.x represents a fundamental architectural shift from a **module-based** system (using traditional Drupal modules and an installation profile) to a **recipe-based** system (using Drupal's composable recipes). This change is too significant to support an automated in-place migration.

Key differences that prevent a direct upgrade:

- **Drupal 10 to Drupal 11**: Major Drupal core version change with removed deprecated APIs.
- **Modules to Recipes**: Varbase modules (`varbase_core`, `varbase_media`, `varbase_editor`, etc.) have been replaced by Varbase recipes (`varbase_content_base`, `varbase_media_base`, `varbase_editor_base`, etc.).
- **Installation Profile to Recipes**: The Varbase installation profile is no longer used; site setup is handled through recipes.
- **Easy Email replaces Varbase Email**: The email system has been completely replaced.
- **ECA replaces custom workflow code**: Workflow automation now uses ECA instead of custom module code.

## Recommended Approach

For sites currently running Varbase 10.x, the recommended approach is:

1. **Start a new Varbase 11.x site** using the [installation guide](../installing-varbase/installing-varbase-with-ddev.md).
2. **Migrate your content** from the 10.x site to the new 11.x site using Drupal's Migrate API or other content migration tools.
3. **Recreate custom configuration** on the new site, adapting to the recipe-based architecture.
4. **Port custom modules and themes** to Drupal 11, updating code for API changes.

## Continuing with Varbase 10.x

Varbase 10.x remains supported. You can continue to receive updates for your 10.x site by following the standard update workflow described in the [Updating a Varbase Site](README.md) guide.
