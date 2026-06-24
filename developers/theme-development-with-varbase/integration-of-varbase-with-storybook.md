# Integration of Varbase with Storybook

**Varbase** has been integrated with [**Storybook**](https://storybook.js.org/) to provide a listing of stories for [**Single Directory Components (SDC)**](https://www.drupal.org/docs/develop/theming-drupal/using-single-directory-components) components. This integration allows for easier development and testing of [**Varbase Components**](https://www.drupal.org/project/varbase_components).

> **Warning:** Not for production. Only use for development or staging environments.

## Prerequisites

Follow the Varbase installation guide to build and install Varbase with DDEV before initializing Storybook.

{% content-ref url="../installing-varbase/installing-varbase-with-ddev.md" %}
[installing-varbase-with-ddev.md](../installing-varbase/installing-varbase-with-ddev.md)
{% endcontent-ref %}

## The `ddev storybook` command

Varbase ships a single DDEV command to manage Storybook. Run `ddev storybook help` to see everything it does (alias: `ddev sb`).

```bash
ddev storybook <command>
```

The `ddev storybook` command is a convenience wrapper. The underlying `yarn` scripts still work, so if you have **not** updated to the new command yet you can keep using the equivalents in the right column.

| Command | What it does | `yarn` equivalent |
| --- | --- | --- |
| `ddev storybook init` | Full first-time setup (same as `ddev init-storybook`). | `ddev init-storybook` |
| `ddev storybook enable` | Turn **on** the development local services (CORS + Twig debug) so the `storybook.*` subdomain can render stories. | — |
| `ddev storybook disable` | Turn them **off** and keep them off across restarts. | — |
| `ddev storybook list` | Print the Storybook URLs / domains to open. | — |
| `ddev storybook status` | Show module / dev-services / daemon / port / CORS health. | — |
| `ddev storybook stats` | Show how many stories are served, grouped by component group. | — |
| `ddev storybook doctor` | Diagnose common problems and print the exact command to fix each. | — |
| `ddev storybook gen` | Regenerate `*.stories.json` from Twig. | `ddev yarn storybook:gen` (or `storybook:gen-new`) |
| `ddev storybook build` | Build a static Storybook into `./storybook`. | `ddev yarn storybook:build` |
| — (manual dev server) | Run a foreground dev server on port `6006`. | `ddev yarn storybook:dev` / `ddev yarn storybook:ddev` |
| — (free port 6006) | Kill a running Storybook process. | `ddev yarn storybook:kill` |

> **Note:** The Storybook **dev server runs automatically** as a DDEV `web_extra_daemon` (see `web_extra_daemons` in `.ddev/config.yaml`). You do **not** need to start it by hand — after `ddev storybook init` it is already serving on port `6006` and on the Storybook subdomain. All `yarn` scripts are defined in `package.json` and can also be run on the host without DDEV (`yarn storybook:build`, `yarn storybook:dev`, …).

## Initialize Storybook for DDEV

### 1. Initialize Storybook for Varbase

```bash
ddev init-storybook
```

or

```bash
ddev storybook init
```

Either command runs the same full first-time setup, which:

* Installs Node.js dependencies via `yarn install`
* Enables the `storybook` Drupal module
* Grants `render storybook stories` permission to anonymous and authenticated users
* Copies `development.local.services.yml` to `web/sites/default/`
* Enables the development services include in `settings.ddev.php` / `settings.platformsh.php` (via `ddev storybook enable`)
* Configures the `storybook.<project>.ddev.site` subdomain (`additional_fqdns` + the Apache proxy)
* Writes `.env.storybook` with `STORYBOOK_SERVER_URL` and `STORYBOOK_SERVER_RENDER_URL` pointing at the active Drupal site URL, used by the Storybook dev server and middleware to reach Drupal

Have a look at the content of the [storybook](https://github.com/Vardot/varbase-project/blob/11.0.x/.ddev/commands/web/storybook) and [init-storybook](https://github.com/Vardot/varbase-project/blob/11.0.x/.ddev/commands/web/init-storybook) commands.

> **Tip:** If `init` changed the subdomain or routing, run `ddev restart` once to apply it.

### 2. Generate Stories

Generate all stories using either command:

```bash
ddev storybook gen
```

or

```bash
ddev yarn storybook:gen
```

Both run the Drush command:

```bash
ddev drush storybook:generate-all-stories --omit-server-url --force
```

To generate only new stories (without overwriting existing ones):

```bash
ddev yarn storybook:gen-new
```

### 3. Open Varbase Storybook

The dev server is already running (as a `web_extra_daemon`). Print the URLs:

```bash
ddev storybook list
```

```
Storybook URLs for this project:
   • Subdomain:     https://storybook.varbase.ddev.site/
   • Direct port:   https://varbase.ddev.site:6006/
   • Drupal render: https://varbase.ddev.site/storybook/stories/render
   403 stories currently served.
```

Open the **subdomain** URL in your browser. The `:6006` direct URL also works.

To check everything is healthy:

```bash
ddev storybook status
```

If a story fails to render (for example a CORS error in the browser console), run the doctor — it tells you exactly what to fix:

```bash
ddev storybook doctor
```

### 4. Restarting DDEV

Story rendering keeps working across `ddev stop` / `ddev start` / `ddev restart`. DDEV regenerates `settings.ddev.php` on every start, so a `post-start` hook re-applies the development services (CORS) include automatically by running `ddev storybook enable --boot`.

To turn Storybook's development services off for a while (and keep them off across restarts):

```bash
ddev storybook disable
```

Re-enable them with:

```bash
ddev storybook enable
```

### Starting the dev server manually

You normally never need this — the daemon already runs it. To run a fresh foreground dev server (for example to watch its log), use the yarn script:

```bash
ddev yarn storybook:ddev
```

This binds to `0.0.0.0` so the subdomain proxy can reach it. To free port `6006`:

```bash
ddev yarn storybook:kill
```

## How Storybook Connects to Drupal <a href="#how-storybook-connects-to-drupal" id="how-storybook-connects-to-drupal"></a>

Storybook runs on its own port (`6006`) but renders SDC components by calling the Drupal site. Two pieces glue this together:

### `.storybook/middleware.js` <a href="#storybook-middleware-js" id="storybook-middleware-js"></a>

An Express middleware that proxies Drupal static assets (CSS, JS, fonts, images) through the Storybook dev server. The Storybook iframe runs at `:6006`, but Drupal assets are served from a different origin (e.g. `:8443`); browsers block cross-origin sub-resources loaded via `innerHTML` because static files have no CORS headers. The middleware routes paths under `/themes/`, `/modules/`, `/core/`, `/libraries/`, `/sites/`, and `/storybook/` to the Drupal base URL read from `process.env.STORYBOOK_SERVER_URL` so the browser sees them as same-origin requests.

### `.storybook/preview.ts` `fetchStoryHtml` <a href="#storybook-preview-ts-fetchstoryhtml" id="storybook-preview-ts-fetchstoryhtml"></a>

Custom fetch function for `@storybook/server` that:

* Cleans up Drupal SDC params before sending — strips `undefined`/`null` values and converts bare `#` URI values to empty strings (Drupal SDC validation rejects both)
* In development, relies on `middleware.js` to proxy assets — no rewriting needed
* In production (static `storybook:build` export), rewrites relative root-relative `href`/`src`/`action` attributes to absolute Drupal URLs so assets load from the live Drupal server instead of 404-ing on the static host

## When Adding or Changing Stories

Run `ddev storybook gen` (or `ddev yarn storybook:gen`) whenever stories are added or changed to regenerate all stories.

## Manual Setup (Without DDEV Commands)

If you prefer to set up Storybook manually instead of using the `ddev storybook init` command:

### Enable the Storybook Module

Enable the `storybook` module through the site interface or with Drush:

```bash
drush pm:enable storybook
```

> **Warning:** The Storybook module should not be kept running on a production site.

### Grant Permissions

Navigate to `/admin/people/permissions/module/storybook` to grant the `Render storybook stories` permission, or use Drush:

```bash
drush role:perm:add anonymous 'render storybook stories'
drush role:perm:add authenticated 'render storybook stories'
```

> **Warning:** Give to trusted roles only; this permission has security implications. Allows a user to access the Twig Storybook endpoint to render a template with stories.

To revoke the permission later:

```bash
drush role:perm:remove anonymous 'render storybook stories'
drush role:perm:remove authenticated 'render storybook stories'
```

### Configure Development Services

Create or update the `development.local.services.yml` file in `web/sites/default/` with the following content:

```yaml
# Local development services.
#
# To activate this feature, follow the instructions at the top of the
# 'settings.platformsh.php' or 'settings.local.php' file, which sits next to this file.
parameters:
  twig.config:
    debug: true
    cache: false
  http.response.debug_cacheability_headers: true
  storybook.development: true
  cors.config:
    enabled: true
    # Specify allowed headers, like 'x-allowed-header'.
    allowedHeaders: ['*']
    # Specify allowed request methods, specify ['*'] to allow all possible ones.
    allowedMethods: ['*']
    # Configure requests allowed from specific origins. Do not include trailing
    # slashes with URLs.
    allowedOrigins: ['*']
    # Configure requests allowed from origins, matching against regex patterns.
    allowedOriginsPatterns: ['*']
    # Sets the Access-Control-Expose-Headers header.
    exposedHeaders: false
    # Sets the Access-Control-Max-Age header.
    maxAge: false
    # Sets the Access-Control-Allow-Credentials header.
    supportsCredentials: true
services:
  cache.backend.null:
    class: Drupal\Core\Cache\NullBackendFactory
```

> **Warning:** Not recommended to keep `cors.config` with `enabled: true` in production environments. Keep all changes in the `development.local.services.yml` file.

### Include the Development Services File

Add the following to `settings.local.php` or `settings.ddev.php`:

```php
// Enable the development local services for Storybook.
$settings['container_yamls'][] = $app_root . '/' . $site_path . '/development.local.services.yml';
```

> **Note:** With DDEV, `settings.ddev.php` is regenerated on every start, which would drop this line. The `ddev storybook` command handles that for you by re-adding it from a `post-start` hook — prefer `ddev storybook enable` over editing `settings.ddev.php` by hand.

### Install Dependencies and Start

1. Run `yarn install` to install dependencies
2. Run `yarn storybook:gen` to generate all stories
3. Run `yarn storybook:dev` to start Storybook on port 6006

## Customizing Varbase Storybook for a Project

### Switching Between Themes

To showcase a custom cloned generated theme, uncomment and modify the following line in the `.storybook/preview.ts` file:

```typescript
// mytheme: {title: 'My Custom Theme for a Project'}
```

### Show Vartheme BS5 Components

By default, the `.storybook/main.ts` file includes components from Vartheme BS5:

```typescript
"../web/themes/contrib/vartheme_bs5/components/**/*.mdx",
"../web/themes/contrib/vartheme_bs5/components/**/*.stories.@(json)",
```

### Show Custom Theme Components

To include components from a custom cloned generated theme, uncomment and modify the following lines in the `.storybook/main.ts` file:

{% content-ref url="creating-your-own-theme.md" %}
[creating-your-own-theme.md](creating-your-own-theme.md)
{% endcontent-ref %}

```typescript
"../web/themes/custom/mytheme/components/**/*.mdx",
"../web/themes/custom/mytheme/components/**/*.stories.@(json)",
```

Ensure the path to the custom theme is correct. It should be located in `../web/themes/custom/`.

### Show Custom Module Components

To include components from a custom module, uncomment and modify the following lines in the `.storybook/main.ts` file:

```typescript
"../web/modules/custom/my_custom_module/components/**/*.mdx",
"../web/modules/custom/my_custom_module/components/**/*.stories.@(json)",
```

### Bootstrap Color Modes

Varbase Storybook supports Bootstrap 5.3+ color modes. Use the root attributes addon in the Storybook toolbar to switch between Light and Dark themes, as well as LTR and RTL text direction.

## Storybook Build

Build a static version of Storybook for demos, staging, or hosted development environments using either command:

```bash
ddev storybook build
```

or

```bash
ddev yarn storybook:build
```

> **Danger:** Not for production environments. Only for development, staging, or demo.

This outputs the built Storybook to the `storybook` directory. A subdomain can then point to this directory:

* `my-staging-site.com` points at the `web` directory (Varbase site)
* `storybook.my-staging-site.com` points at the `storybook` directory (Storybook)

## Run Varbase Storybook on UPSUN

For development, testing, or staging environments on Platform.sh:

> **Danger:** NOT for production environments.

### Select the Varbase Template

Use the TEMP development for [**Vardot/upsun-varbase11x00**](https://github.com/Vardot/upsun-varbase11x00) from the pre-existing code base template to start a project.

### Use Development Services

Add the following to `settings.platformsh.php`:

```php
// Enable the development local services for Storybook.
if (isset($platformsh->branch)) {
  if (!$platformsh->onProduction() || !$platformsh->onDedicated()) {
    $settings['container_yamls'][] = $app_root . '/' . $site_path . '/development.local.services.yml';
  }
}
```

After committing and starting the development environment, the Storybook link will be available at:

```
https://storybook.{default}
```
