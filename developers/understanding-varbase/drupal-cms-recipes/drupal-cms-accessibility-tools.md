# Drupal CMS Accessibility Tools

## Description

The Drupal CMS Accessibility Tools recipe provides automated accessibility checks using the Editoria11y module. It helps content editors identify and fix accessibility issues directly within the content editing interface, promoting WCAG compliance across the site.

## Recipe Dependencies

Depends on the following recipes:

| Recipe | Description |
|---|---|
| [**Drupal CMS Content Type Base**](drupal-cms-content-type-base.md) | Basic content type tools required for content integration. |

## Included Modules

Brings in the following core and contributed modules to your site:

| Module | Purpose |
|---|---|
| [**Editoria11y**](https://www.drupal.org/project/editoria11y) | Checks for accessibility in page content. |
| **Views** *(in Drupal core)* | Provides a framework to fetch information from the database and to display it in different formats. |

## Installation

Apply the recipe using Drush:

```bash
ddev drush recipe ../recipes/drupal_cms_accessibility_tools
```

## Usage

After installation, Editoria11y automatically scans pages as content editors view them. Accessibility issues are highlighted with inline indicators that editors can click for detailed explanations and remediation guidance. This continuous feedback loop helps editors create accessible content as they work, rather than relying on separate auditing tools after the fact.

Common issues detected include:

- Missing or empty image alt text
- Incorrect heading hierarchy (e.g., skipping heading levels)
- Empty links or buttons
- Potential contrast issues
- Missing document language attributes
