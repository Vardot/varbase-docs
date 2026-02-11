# Drupal CMS Google Analytics

## Description

The Drupal CMS Google Analytics recipe integrates Google Analytics and Google Tag Manager tracking into your Drupal site. It works with the privacy module to ensure that tracking respects visitor consent preferences.

## Dependencies

- **drupal\_cms\_privacy\_basic** -- Basic privacy features for consent management, ensuring tracking scripts are only loaded when visitors have given consent

## Modules Included

- **google\_tag** -- Provides Google Tag Manager integration, supporting multiple tag container types for analytics and marketing

## Configuration Input

This recipe accepts the following configuration input during installation:

- **property\_id** -- Your Google Tag Manager property ID. Supported formats:
  - `GT-xxxxxx` -- Google Tag
  - `G-xxxxxxxx` -- Google Analytics 4 measurement ID
  - `AW-xxxxxxxxx` -- Google Ads conversion ID
  - `GTM-xxxxxxxx` -- Google Tag Manager container ID
  - `DC-xxxxxxxx` -- Floodlight (Campaign Manager) tag

## Installation

This recipe is typically installed as a dependency of the varbase\_starter recipe. To apply it independently:

```bash
drush recipe recipes/contrib/drupal_cms_google_analytics
```

## Usage

After installation, configure your Google Tag Manager property ID through the site configuration. The tracking code is automatically injected into all pages, but only activates after visitors provide consent through the Klaro consent manager (installed by the privacy dependency). This ensures compliance with privacy regulations such as GDPR.
