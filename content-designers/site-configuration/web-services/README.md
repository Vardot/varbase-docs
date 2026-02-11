# Web Services

Varbase supports web services that enable programmatic access to site content and configuration through APIs. These capabilities allow external applications, mobile apps, and frontend frameworks to interact with your Drupal site.

## Overview

### JSON:API

Drupal core includes **JSON:API**, which provides a standards-compliant API for accessing and manipulating content entities (nodes, media, taxonomy terms, users, etc.). JSON:API follows the JSON:API specification and provides:

- Read access to published content.
- Create, update, and delete operations (for authenticated users with appropriate permissions).
- Filtering, sorting, and pagination of content listings.
- Relationship handling between entities.

JSON:API is enabled by default in Drupal and does not require additional configuration for basic read access to published content.

### OpenAPI

**OpenAPI** (formerly Swagger) provides machine-readable documentation of your site's API endpoints. It generates a complete specification of available API routes, parameters, and response formats.

See [OpenAPI](openapi.md) for details.

## Accessing Web Services Configuration

Navigate to **Configuration > Web services** in the admin navigation sidebar, or go to `/admin/config/services`.

## Security Considerations

- API access respects Drupal's permission system. Users can only access content through the API that they are permitted to access through the regular admin interface.
- Anonymous API access is typically limited to reading published content.
- Authenticated API access requires valid credentials and is subject to the user's role permissions.
- Your development team should review and configure API permissions to ensure sensitive data is not exposed.

## Who Uses Web Services?

Web services are primarily used by:

- **Frontend developers** building decoupled (headless) applications that consume Drupal content.
- **Mobile app developers** who need to access site content in their applications.
- **Integration developers** connecting your Drupal site with external systems (CRMs, marketing tools, etc.).
- **Content editors** typically do not interact with web services directly, but may benefit from understanding that they exist for technical integrations.
