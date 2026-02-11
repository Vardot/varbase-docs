# Drupal CMS Google Analytics

## Description

The Drupal CMS Google Analytics recipe integrates Google Analytics and Google Tag Manager tracking into your Drupal site. It works with the privacy module to ensure that tracking respects visitor consent preferences.

## Dependencies

- **drupal\_cms\_privacy\_basic** -- Basic privacy features for consent management, ensuring tracking scripts are only loaded when visitors have given consent

## Included Modules

Brings in the following core and contributed modules to your site:

| Module | Purpose |
|---|---|
| [**Google Tag**](https://www.drupal.org/project/google_tag) | Sets up Google Tag. |

## Configuration Input

This recipe accepts the following configuration input during installation:

- **property\_id** -- Your Google Tag Manager property ID. Supported formats:
  - `GT-xxxxxx` -- Google Tag
  - `G-xxxxxxxx` -- Google Analytics 4 measurement ID
  - `AW-xxxxxxxxx` -- Google Ads conversion ID
  - `GTM-xxxxxxxx` -- Google Tag Manager container ID
  - `DC-xxxxxxxx` -- Floodlight (Campaign Manager) tag

## Installation

Apply the recipe using Drush:

```bash
drush recipe recipes/contrib/drupal_cms_google_analytics
```

## Usage

After installation, configure your Google Tag Manager property ID through the site configuration. The tracking code is automatically injected into all pages, but only activates after visitors provide consent through the Klaro consent manager (installed by the privacy dependency). This ensures compliance with privacy regulations such as GDPR.
