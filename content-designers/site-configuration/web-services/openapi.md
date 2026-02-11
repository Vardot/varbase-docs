# OpenAPI

**OpenAPI** (also known as Swagger) provides interactive, machine-readable documentation for the API endpoints available on your Varbase site. It allows developers to explore, test, and understand the available API operations.

## What Is OpenAPI?

OpenAPI is a specification for describing RESTful APIs. When configured on your Drupal site, it generates documentation that describes:

- All available API endpoints (URLs).
- The HTTP methods supported by each endpoint (GET, POST, PATCH, DELETE).
- The parameters required for each request.
- The structure of request and response data.
- Authentication requirements.

This documentation is useful for developers who need to integrate with your site's API.

## Accessing OpenAPI Documentation

1. Navigate to **Configuration > Web services > OpenAPI**, or go to the OpenAPI configuration page provided by your site's setup.
2. The OpenAPI documentation is presented through a **Swagger UI** interface, which provides:
   - A list of all available API endpoints, organized by resource type.
   - Interactive "Try it out" buttons that allow developers to test API calls directly from the browser.
   - Detailed schemas showing the structure of request and response data.

## Available API Resources

The OpenAPI documentation typically covers the following resource types:

- **Content (Nodes)**: Create, read, update, and delete content items via the API.
- **Media**: Access and manage media entities.
- **Taxonomy Terms**: Access and manage taxonomy terms and vocabularies.
- **Users**: Access user information (subject to permissions).
- **Blocks**: Access block content.
- **Files**: Upload and manage files.

The specific resources available depend on the modules enabled and the API configuration on your site.

## Who Uses OpenAPI?

OpenAPI documentation is primarily used by:

- **Developers** building external applications that integrate with your Drupal site.
- **Mobile app developers** who need to understand the API structure for building mobile applications.
- **Third-party integrators** connecting your site with external services.

Content editors and administrators typically do not need to interact with OpenAPI directly, but may find it useful to understand that this documentation exists for technical stakeholders.

## Tips

- If you need access to the OpenAPI documentation, ask your site administrator to provide the URL.
- The OpenAPI specification can be downloaded as a JSON or YAML file for use with API development tools.
- API access respects Drupal's permission system. Developers testing API calls through Swagger UI will only see data they are authorized to access.
- Coordinate with your development team if you need new content types or fields to be available through the API.
