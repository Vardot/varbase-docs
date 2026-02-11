# Configuring URL Aliases

Pathauto uses patterns to automatically generate URL aliases for new and updated content. Each pattern defines a template that Pathauto uses to construct the alias, using tokens to insert dynamic values such as the content title, content type, or date.

## Accessing Pathauto Patterns

Navigate to **Configuration > URL aliases > Patterns** in the Drupal admin interface, or go directly to:

```
/admin/config/search/path/patterns
```

## Creating a Pathauto Pattern

1. Navigate to **Configuration > URL aliases > Patterns**.
2. Click **Add Pathauto pattern**.
3. Select the **pattern type** (Content, Taxonomy term, User, or other entity type).
4. Enter the **path pattern** using tokens.
5. Optionally restrict the pattern to specific **bundles** (for example, a specific content type).
6. Set the **label** for the pattern.
7. Save the pattern.

## Common Token Patterns

Pathauto uses the Drupal token system to insert dynamic values into URL aliases. Some commonly used patterns include:

### Content (Nodes)

| Pattern | Example Output |
| --- | --- |
| `[node:title]` | `my-page-title` |
| `blog/[node:title]` | `blog/my-blog-post` |
| `[node:content-type]/[node:title]` | `article/my-article` |
| `[node:created:custom:Y]/[node:created:custom:m]/[node:title]` | `2026/01/my-page` |

### Taxonomy Terms

| Pattern | Example Output |
| --- | --- |
| `[term:vocabulary]/[term:name]` | `tags/drupal` |
| `category/[term:name]` | `category/technology` |

### Users

| Pattern | Example Output |
| --- | --- |
| `users/[user:account-name]` | `users/admin` |
| `team/[user:account-name]` | `team/john-doe` |

## Browsing Available Tokens

When creating or editing a pattern, click the **Browse available tokens** link below the pattern field. This opens a token browser that lists all available tokens organized by category.

## Pattern Precedence

When multiple patterns could apply to the same entity (for example, one pattern for all content and another for a specific content type), Pathauto evaluates patterns based on their weight. More specific patterns should be placed above more general patterns so they take precedence.

You can reorder patterns by dragging them on the patterns administration page.

## Transliteration and Cleaning

Pathauto automatically cleans generated aliases by:

- Converting text to lowercase
- Replacing spaces with hyphens
- Removing special characters and punctuation
- Transliterating non-ASCII characters to their ASCII equivalents

These settings can be adjusted under **Configuration > URL aliases > Settings**:

```
/admin/config/search/path/settings
```
