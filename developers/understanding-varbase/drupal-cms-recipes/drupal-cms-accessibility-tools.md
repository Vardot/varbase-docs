# Drupal CMS Accessibility Tools

## Description

The Drupal CMS Accessibility Tools recipe provides automated accessibility checks using the Editoria11y module. It helps content editors identify and fix accessibility issues directly within the content editing interface, promoting WCAG compliance across the site.

## Dependencies

- **drupal\_cms\_content\_type\_base** -- Basic content type tools required for content integration

## Modules Included

- **editoria11y** -- Automated accessibility checker that scans page content and highlights potential issues such as missing alt text, improper heading structure, low contrast text, and other WCAG violations. It provides inline alerts and guidance directly on the page for content editors.

## Installation

This recipe is typically installed as a dependency of the varbase\_starter recipe. To apply it independently:

```bash
drush recipe recipes/contrib/drupal_cms_accessibility_tools
```

## Usage

After installation, Editoria11y automatically scans pages as content editors view them. Accessibility issues are highlighted with inline indicators that editors can click for detailed explanations and remediation guidance. This continuous feedback loop helps editors create accessible content as they work, rather than relying on separate auditing tools after the fact.

Common issues detected include:

- Missing or empty image alt text
- Incorrect heading hierarchy (e.g., skipping heading levels)
- Empty links or buttons
- Potential contrast issues
- Missing document language attributes
