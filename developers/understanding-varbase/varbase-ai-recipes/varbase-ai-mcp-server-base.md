# Varbase AI MCP Server Base

The **Varbase AI MCP Server Base** recipe lets external AI assistants, such as Claude, read the site and draft blog posts and pages through the Model Context Protocol (MCP). Nothing it writes is published. Publishing stays a human action in Drupal.

## Recipe Type

Varbase AI

## Drupal.org Project

[https://www.drupal.org/project/varbase\_ai\_mcp\_server\_base](https://www.drupal.org/project/varbase_ai_mcp_server_base)

{% hint style="warning" %}
**Alpha release.** The MCP and OAuth modules it uses are not stable yet. This recipe is not covered by the Drupal security advisory policy. Try it on a development site first.
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
ddev composer require drupal/varbase_ai_mcp_server_base:~1
ddev drush cr
ddev drush recipe ../recipes/varbase_ai_mcp_server_base
ddev drush cr
```

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

To connect a headless agent, create a client-credentials client. Give it `mcp:read` to read, or `mcp:read,mcp:write` to draft. Its service user needs the `mcp_agent` role. The secret is printed once:

```bash
ddev drush mcp:client:create reporting-agent --scopes=mcp:read --label="Reporting agent"
```

## What an Assistant Can Do

- **Read** (`mcp:read`): explain the content model and read content the person may see.
- **Draft** (`mcp:write`): create a blog post or page, saved unpublished as a draft. Or edit one the person owns, which adds a pending revision and leaves the live version as it is.
- **Never**: publish, archive, delete, or change the content model.

Four layers stop a publish, each enough on its own:

1. No token can carry `mcp:publish`: every grant for it is off.
2. The `mcp_agent` role has only the **Create New Draft** workflow transition.
3. The **MCP** module refuses to save a published item without `mcp:publish`.
4. Delete, one-step create and update, and publish tools are not exposed.

A token never gets more than both the person and the `mcp_agent` role allow. A person reviews and publishes drafts in Drupal as usual.

## Known Limitations

- User 1 bypasses every scope. Connect with a real account.
- `/oauth/register` accepts anonymous requests with no rate limit. A registered client gets nothing until a person with the `mcp_agent` role logs in and approves it. Add a rate limit at the edge (a WAF or CDN) if needed.
- The discovery documents still list the `plain` PKCE method.
- Access tokens last 300 seconds per client by default.
- Search over the vector index and Canvas tools are not included.

## Design Notes

**OAuth 2.1, not Basic auth.** With Basic auth, every assistant shares one site login, sent with every request. A leaked password is a full site login, and changing it breaks every client. With OAuth 2.1:

- Each person connects their own assistant and approves it once.
- A token works only for `/mcp`, expires in minutes, and never carries more than the person behind it.
- One client can be revoked on its own, and every call names its client and user.
- Interactive assistants, such as Claude, connect through the standard MCP sign-in flow.

The cost is more moving parts: several modules that are not stable yet, and signing keys on disk. The scopes are enforced by the **MCP** module, which is why the recipe installs it while skipping its setup command.

Since an assistant can now write drafts, text hidden in content could lead it to draft something unwanted. It still cannot publish, and the server instructions ask the assistant to show a diff and get agreement before each save.
