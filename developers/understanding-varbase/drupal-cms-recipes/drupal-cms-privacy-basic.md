# Drupal CMS Privacy Basic

## Description

The Drupal CMS Privacy Basic recipe provides basic privacy features including consent management and remote content blocking. It helps sites comply with privacy regulations by giving visitors control over cookies and external content loading.

## Dependencies

- **drupal\_cms\_content\_type\_base** -- Basic content type tools (required for menu and content integration)

## Modules Included

- **klaro** -- Consent management platform that provides a user-friendly cookie consent dialog, allowing visitors to selectively accept or reject different categories of cookies and tracking
- **menu\_link\_attributes** -- Adds custom attributes to menu links, used for privacy-related link annotations
- **eca\_base** -- ECA base framework for event-driven privacy automation
- **eca\_misc** -- ECA miscellaneous event handlers
- **eca\_ui** -- ECA user interface for managing privacy-related rules
- **bpmn\_io** -- BPMN.io integration for workflow visualization
- **modeler\_api** -- API for workflow modelers

## Installation

This recipe is typically installed as a dependency of other Drupal CMS recipes (such as Drupal CMS Media and Drupal CMS Google Analytics). To apply it independently:

```bash
drush recipe recipes/contrib/drupal_cms_privacy_basic
```

## Usage

After installation, visitors will see a consent management dialog (powered by Klaro) that allows them to choose which cookies and external services they permit. Remote content (such as embedded videos or analytics scripts) is blocked until the visitor provides explicit consent. Site administrators can configure consent categories and customize the dialog through the Klaro settings.
