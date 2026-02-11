# Drupal CMS Privacy Basic

## Description

The Drupal CMS Privacy Basic recipe provides basic privacy features including consent management and remote content blocking. It helps sites comply with privacy regulations by giving visitors control over cookies and external content loading.

## Recipe Dependencies

Depends on the following recipes:

| Recipe | Description |
|---|---|
| [**Drupal CMS Content Type Base**](drupal-cms-content-type-base.md) | Basic content type tools for menu and content integration. |

## Included Modules

Brings in the following core and contributed modules to your site:

| Module | Purpose |
|---|---|
| [**BPMN.iO Modeler**](https://www.drupal.org/project/bpmn_io) | BPMN modeler, integrated into Drupal's admin UI. |
| [**ECA Base**](https://www.drupal.org/project/eca) | Base events, conditions and actions. |
| [**ECA Config**](https://www.drupal.org/project/eca) | Config events. |
| [**ECA Content**](https://www.drupal.org/project/eca) | Content entity events, conditions and actions. |
| [**ECA User**](https://www.drupal.org/project/eca) | User events, conditions and actions. |
| [**ECA UI**](https://www.drupal.org/project/eca) | Provides a user interface for managing ECA models. |
| [**Klaro Cookie & Consent Manager**](https://www.drupal.org/project/klaro) | Implements the Klaro Consent Manager into Drupal. |
| [**Menu Link Attributes**](https://www.drupal.org/project/menu_link_attributes) | Allows you to add attributes to menu links. |
| **Custom Menu Links** *(in Drupal core)* | Allows users to create menu links. |
| [**Modeler API**](https://www.drupal.org/project/modeler_api) | Provides an API for modules to use modelers like BPMN.iO. |

## Installation

Apply the recipe using Drush:

```bash
ddev drush recipe ../recipes/drupal_cms_privacy_basic
```

## Usage

After installation, visitors will see a consent management dialog (powered by Klaro) that allows them to choose which cookies and external services they permit. Remote content (such as embedded videos or analytics scripts) is blocked until the visitor provides explicit consent. Site administrators can configure consent categories and customize the dialog through the Klaro settings.
