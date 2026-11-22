# Varbase Auth

**Varbase Auth** (Varbase Social Single Sign-On) lets people sign in and register with an account they already have, such as Google, Facebook or LinkedIn. It is built on **Social API** and **Social Auth**, and styles the sign-in buttons for Varbase.

## Module Type

Varbase

## Drupal.org Project

[https://www.drupal.org/project/varbase\_auth](https://www.drupal.org/project/varbase_auth)

## Used By

The [**Varbase Auth Base**](../../varbase-recipes/varbase-auth-base.md) recipe requires it. That recipe ships in the project's `recipes/` folder and is applied on demand.

## What It Provides

- Requires **Social Auth** with the **Google**, **Facebook** and **LinkedIn** providers.
- On the **Log in** and **Create new account** pages, tells the theme whether any social sign-in provider is enabled, so the theme shows the social buttons only when there is one.
- Provider icons for the **Log in with** buttons (`login-with.html.twig`) and a block template for the Social Auth login block (`block--social-auth.html.twig`).
- Under the **Gin** admin theme, replaces the Social Auth icon styles with its own (`varbase_auth/auth-icons`).

## Installation

Apply the **Varbase Auth Base** recipe:

```bash
ddev drush recipe ../recipes/varbase_auth_base
```

## Configuration

Set up each provider at **Administration** \ **Configuration** \ **People** \ _**Social Auth**_ with the app credentials from that service, such as a Google OAuth client ID and secret.

## Related Pages

- [Varbase Auth Base](../../varbase-recipes/varbase-auth-base.md)
- [Varbase Modules](../README.md)
