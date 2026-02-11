# Varbase Auth Base

The **Varbase Auth Base** recipe provides Social Single Sign-On with default social authentication capabilities for Varbase sites.

## Drupal.org Project

[https://www.drupal.org/project/varbase\_auth\_base](https://www.drupal.org/project/varbase_auth_base)

## Included Modules

Brings in the following core and contributed modules to your site:

| Module | Purpose |
|---|---|
| [**Social Auth**](https://www.drupal.org/project/social_auth) | Allows user authentication with different services. |
| [**Social Auth Google**](https://www.drupal.org/project/social_auth_google) | Social Auth integration for Google. |
| [**Varbase Social Single Sign-On**](https://www.drupal.org/project/varbase_auth) | Adds single sign-on using existing information from a social networking service. Such as Facebook, Twitter, LinkedIn, or Google. Built using Social API. |

## Installation

Apply the recipe using Drush:

```bash
drush recipe recipes/contrib/varbase_auth_base
```

## Configuration

After applying the recipe, configure your social authentication providers by navigating to **Administration > Configuration > People > Social Auth** and entering the required API credentials for each provider (such as Google OAuth Client ID and Secret).
