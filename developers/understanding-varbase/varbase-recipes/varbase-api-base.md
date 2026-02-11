# Varbase API Base

The **Varbase API Base** recipe provides JSON:API with authentication, authorization, and OpenAPI documentation for building decoupled and headless applications with Varbase.

## Drupal.org Project

[https://www.drupal.org/project/varbase\_api\_base](https://www.drupal.org/project/varbase_api_base)

## Features

- **JSON:API** -- Drupal core's JSON:API implementation for exposing content and configuration as a standards-compliant API
- **JSON:API Extras** -- Additional configuration options for JSON:API resources, including field aliasing, resource disabling, and response customization
- **JSON:API Defaults** -- Set default includes and filters for JSON:API endpoints to simplify client-side queries
- **Simple OAuth** -- OAuth 2.0 authentication provider for secure API access with token-based authentication
- **REST UI** -- Administrative interface for configuring and managing REST resources
- **OpenAPI** -- OpenAPI (Swagger) specification generation for documenting the site's API
- **OpenAPI JSON:API** -- OpenAPI documentation specifically for JSON:API endpoints
- **OpenAPI REST** -- OpenAPI documentation for REST endpoints
- **OpenAPI UI ReDoc** -- ReDoc-based interactive API documentation viewer
- **OpenAPI UI Swagger** -- Swagger UI-based interactive API documentation and testing interface

## Modules Installed

- `jsonapi`
- `openapi`
- `openapi_jsonapi`
- `openapi_rest`
- `openapi_ui_redoc`
- `openapi_ui_swagger`
- `simple_oauth`
- `restui`
- `jsonapi_extras`
- `jsonapi_defaults`

## Installation

1. Require the package via Composer:

```bash
composer require drupal/varbase_api_base:~1.0.0
```

2. Apply the recipe using Drush:

```bash
drush recipe recipes/contrib/varbase_api_base
```
