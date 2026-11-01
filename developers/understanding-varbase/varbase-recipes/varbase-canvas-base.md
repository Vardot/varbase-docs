# Varbase Canvas Base

The **Varbase Canvas Base** recipe installs **Drupal Canvas** and **Canvas Override** on a Varbase site. It installs modules only: no content types, no fields and no permissions.

## Drupal.org Project

[https://www.drupal.org/project/varbase\_canvas\_base](https://www.drupal.org/project/varbase_canvas_base)

## Overview

Varbase Canvas Base was added to **Varbase Starter** in Varbase 11.0.0 ([#3620193](https://www.drupal.org/i/3620193)) and is applied right after **Varbase Content Base** ([#3621018](https://www.drupal.org/i/3621018)).

Related pieces stay in the recipes that own them:

* The Canvas page and component library permissions are granted by **Varbase Content Base**, because a Canvas page is content.
* **Canvas Translate** comes with **Varbase Internationalization Base**.
* **Canvas Icon Picker** comes with **Varbase Admin Base**.
* The Canvas text format permissions come with **Varbase Editor Base**.

The Vardot site templates (**Educare**, **Horizon Aid**, **The Rightup**) do not require this recipe. They get the `canvas` module from **Varbase Media Base**, which they apply directly.

## Included Modules

| Module | Purpose |
| --- | --- |
| [**Drupal Canvas**](https://www.drupal.org/project/canvas) | The visual page builder: Canvas pages, the component library, patterns, content templates and page templates. |
| [**Canvas Override**](https://www.drupal.org/project/canvas_override) | Per-item Canvas layouts on the full view mode of selected content types. Off by default for every content type. |

## Installation

Apply the recipe using Drush:

```bash
ddev drush recipe ../recipes/varbase_canvas_base
```

This recipe is applied automatically by the **Varbase Starter** site template.

## Related

* [Drupal Canvas](../../theme-development-with-varbase/drupal-canvas/README.md)
* [Component Reference: Vartheme BS5 in Drupal Canvas](../../theme-development-with-varbase/drupal-canvas/vartheme-bs5-components-in-drupal-canvas.md)
