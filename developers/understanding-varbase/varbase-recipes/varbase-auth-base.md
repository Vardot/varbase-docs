# Varbase Auth Base

The **Varbase Auth Base** recipe provides Social Single Sign-On with default social authentication capabilities for Varbase sites.

## Drupal.org Project

[https://www.drupal.org/project/varbase\_auth\_base](https://www.drupal.org/project/varbase_auth_base)

## Features

- **Social Auth** -- Framework for integrating social authentication providers, enabling users to log in using their existing social media or third-party accounts
- **Social Auth Google** -- Google authentication provider allowing users to sign in with their Google accounts
- **Varbase Auth** -- Varbase-specific authentication enhancements and configuration that tie the social authentication system into the broader Varbase user management workflow

## Modules Installed

- `social_auth`
- `social_auth_google`
- `varbase_auth`

## Installation

1. Require the package via Composer:

```bash
composer require drupal/varbase_auth_base:~1.0.0
```

2. Apply the recipe using Drush:

```bash
drush recipe recipes/contrib/varbase_auth_base
```

## Configuration

After applying the recipe, configure your social authentication providers by navigating to **Administration > Configuration > People > Social Auth** and entering the required API credentials for each provider (such as Google OAuth Client ID and Secret).
