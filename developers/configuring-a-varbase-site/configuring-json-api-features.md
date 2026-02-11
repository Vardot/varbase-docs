# Configuring JSON:API Features

Varbase 11.0.x provides a fully configured JSON:API interface through the **Varbase API Base** recipe. This enables headless and decoupled front-end architectures by exposing Drupal content and configuration as JSON:API endpoints, complete with authentication, authorization, and interactive API documentation.

## Overview

The Varbase API Base recipe installs and configures the following components:

- **JSON:API**: Drupal's built-in JSON:API implementation for exposing entities as RESTful API endpoints.
- **JSON:API Extras**: Extends JSON:API with resource configuration, field aliasing, and the ability to enable or disable specific resources.
- **Simple OAuth (OAuth2)**: Provides OAuth 2.0 authentication for API consumers, including support for client credentials, authorization code, and password grant types.
- **OpenAPI**: Generates API documentation following the OpenAPI (Swagger) specification.
- **OpenAPI UI**: Provides an interactive Swagger UI for browsing and testing API endpoints.

## JSON:API Configuration

### Accessing JSON:API Settings

JSON:API settings are managed through the JSON:API Extras module. Navigate to **Configuration > Web services > JSON:API > Extras**, or go to:

```
/admin/config/services/jsonapi/extras
```

### Enabling and Disabling Resources

By default, JSON:API exposes all entity types as API resources. You can control which resources are available:

1. Navigate to **Configuration > Web services > JSON:API > Resource overrides**, or go to:

```
/admin/config/services/jsonapi/resource_types
```

2. Review the list of available resources.
3. Click on a resource to configure it:
   - **Disable** the resource entirely to prevent it from being exposed via the API.
   - **Rename** the resource type or individual fields for cleaner API naming.
   - **Disable individual fields** within a resource to control which data is exposed.
4. Save the configuration.

### JSON:API Endpoints

JSON:API endpoints follow the pattern:

```
/jsonapi/{entity_type}/{bundle}
```

For example:

| Endpoint | Description |
| --- | --- |
| `/jsonapi/node/article` | List all article nodes |
| `/jsonapi/node/article/{uuid}` | Get a specific article by UUID |
| `/jsonapi/media/image` | List all image media entities |
| `/jsonapi/taxonomy_term/tags` | List all tag taxonomy terms |

## Configuring Simple OAuth

Simple OAuth provides OAuth 2.0 authentication for API consumers. This is essential for protecting write operations and securing access to restricted content.

### Creating an OAuth Consumer

1. Navigate to **Configuration > People > Simple OAuth**, or go to:

```
/admin/config/people/simple_oauth
```

2. Generate or upload the **public and private keys** required for OAuth token signing.
3. Navigate to **People > OAuth Consumers**, or go to:

```
/admin/config/services/consumer
```

4. Click **Add consumer**.
5. Configure the consumer:
   - **Label**: A descriptive name for the API consumer (for example, "Mobile App", "React Frontend").
   - **Client ID**: A unique identifier (auto-generated or custom).
   - **New Secret**: A secret key for client authentication.
   - **Scopes/Roles**: Assign Drupal roles that determine the permissions granted to this consumer.
   - **Redirect URI**: The callback URL for authorization code grants.
6. Save the consumer.

### Obtaining an Access Token

API consumers obtain access tokens by making a POST request to the token endpoint:

```bash
curl -X POST /oauth/token \
  -d "grant_type=client_credentials" \
  -d "client_id=YOUR_CLIENT_ID" \
  -d "client_secret=YOUR_CLIENT_SECRET"
```

The response includes an access token that should be included in subsequent API requests:

```bash
curl -H "Authorization: Bearer YOUR_ACCESS_TOKEN" \
  /jsonapi/node/article
```

## API Documentation with OpenAPI

Varbase API Base configures OpenAPI and Swagger UI to provide interactive API documentation.

### Accessing the API Documentation

Navigate to **Configuration > Web services > OpenAPI**, or go to:

```
/admin/config/services/openapi
```

The Swagger UI provides:

- A complete list of all available API endpoints.
- Request and response schemas for each endpoint.
- An interactive "Try it out" feature for testing API calls directly from the browser.
- Authentication support for testing protected endpoints.

### OpenAPI Documentation URL

The generated OpenAPI specification is available at:

```
/openapi/jsonapi
```

This specification can be imported into API development tools such as Postman, Insomnia, or code generation tools.

## Best Practices

### Security

- Always use HTTPS for API communication.
- Use OAuth 2.0 authentication for any write operations or access to restricted content.
- Disable JSON:API resources that do not need to be exposed.
- Review field-level access to ensure sensitive data is not inadvertently exposed.

### Performance

- Use JSON:API's built-in **sparse fieldsets** (`fields[node--article]=title,body`) to request only the fields you need.
- Use **include** parameters (`include=field_image,field_tags`) to reduce the number of API requests by side-loading related resources.
- Enable Drupal's page cache and consider using a CDN for caching API responses.

### CORS Configuration

If your front-end application runs on a different domain, you need to configure Cross-Origin Resource Sharing (CORS) in your Drupal `services.yml` file:

```yaml
cors.config:
  enabled: true
  allowedHeaders: ['Content-Type', 'Authorization']
  allowedMethods: ['GET', 'POST', 'PATCH', 'DELETE', 'OPTIONS']
  allowedOrigins: ['https://your-frontend-domain.com']
  maxAge: 3600
```
