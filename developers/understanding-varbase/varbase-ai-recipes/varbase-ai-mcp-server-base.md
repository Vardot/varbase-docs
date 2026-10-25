# Varbase AI MCP Server Base

The **Varbase AI MCP Server Base** recipe lets external AI assistants, such as Claude, read the site and draft blog posts and pages through the Model Context Protocol (MCP). Nothing it writes is published. Publishing stays a human action in Drupal.

## Recipe Type

Varbase AI

## Drupal.org Project

[https://www.drupal.org/project/varbase\_ai\_mcp\_server\_base](https://www.drupal.org/project/varbase_ai_mcp_server_base)

{% hint style="warning" %}
**Alpha release.** Version 1.0.0-alpha1. The MCP and OAuth modules it uses are not stable yet. This recipe is not covered by the Drupal security advisory policy. Try it on a development site first.
{% endhint %}

## What It Adds

- An MCP server at `/mcp`, protected with OAuth 2.1.
- Eight read tools and four draft tools.
- An `mcp_agent` role that can create and edit its own blog posts and pages as drafts only.
- Scopes `mcp:read` and `mcp:write`. No token can publish.

## Before You Apply

This recipe does not need **Varbase AI Base** or an AI provider. It needs the PHP `openssl` and `sodium` extensions.

## Installation

Add the recipe with Composer, then apply it with Drush:

```bash
ddev composer require drupal/varbase_ai_mcp_server_base:~1.0.0@alpha
ddev drush cr
ddev drush recipe ../recipes/varbase_ai_mcp_server_base
ddev drush cr
```

Add `drupal/varbase_ai_mcp_server_base` to the recipe unpack ignore list first, as described in [Installing the Alpha Recipes](README.md#installing-the-alpha-recipes).

## After You Apply

Create the signing keys outside the docroot, never in Git, and give the role to the people who may connect an assistant:

```bash
ddev exec mkdir -p /var/www/html/keys
ddev drush simple-oauth:generate-keys /var/www/html/keys
ddev drush config:set simple_oauth.settings public_key /var/www/html/keys/public.key -y
ddev drush config:set simple_oauth.settings private_key /var/www/html/keys/private.key -y
ddev drush user:role:add mcp_agent <username>
ddev drush mcp:status
```

People then add `https://<site>/mcp` as a connector in their assistant, log in to Drupal and approve.

{% hint style="warning" %}
Do not run `drush mcp:setup`. It exposes the publish tool.
{% endhint %}
