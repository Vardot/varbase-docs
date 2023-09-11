# Integration of Varbase with Storybook

**Varbase** has been integrated with [**Storybook**](https://storybook.js.org/) to provide a listing of stories for [**Single Directory Components (SDC)**](https://www.drupal.org/docs/develop/theming-drupal/using-single-directory-components) components. This integration allows for easier development and testing of [**Varbase Components**](https://www.drupal.org/project/varbase\_components).

{% hint style="info" %}
#### Not for production!!, only for development or staging.
{% endhint %}

## Steps to Set up a Working Storybook for Varbase

* Enable the **`cl_server`** module on the site either through the site's interface or by running the command `./bin/drush en cl_server` with Drush. Note that the CL Server module should not be kept running on a production site.
* Navigate to **`"/admin/people/permissions/module/cl_server"`**  to give the `Use the CL Server endpoint` permission to all user roles. Check the  `Anonymous user` and `Authenticated user` checkbox and press **`Save permission`** submit button

<figure><img src="../../.gitbook/assets/varbase10--Module-Permissions-dev-varbase10c1storybook.png" alt=""><figcaption><p>Use the CL Server endpoint Module Permissions</p></figcaption></figure>

{% hint style="warning" %}
**Use the CL Server endpoint**

_**Warning:** Give to trusted roles only; this permission has security implications._

&#x20;Allows a user to access the Component Library: Server endpoint
{% endhint %}

* Add the following exclude of modules to the `settings.php` or `settings.local.php` only to the development environment:

```php
# Disable caches during development. This allows finding new components without clearing caches.
// $settings['cache']['bins']['component_registry'] = 'cache.backend.null';
# Then disallow exporting config for 'cl_server'. Instructions are at the bottom of the file.
$settings['config_exclude_modules'] = ['devel', 'stage_file_proxy', 'cl_server'];
```

* Change the following **Cross-Site HTTP requests (CORS)** in the **`development.services.yml`** file.

{% hint style="info" %}
```yaml
# Local development services.
#
# To activate this feature, follow the instructions at the top of the
# 'example.settings.local.php' file, which sits next to this file.
parameters:
  twig.config:
    debug: true
    cache: false
  http.response.debug_cacheability_headers: true
  cors.config:
    enabled: true
    # Specify allowed headers, like 'x-allowed-header'.
    allowedHeaders: ['*']
    # Specify allowed request methods, specify ['*'] to allow all possible ones.
    allowedMethods: []
    # Configure requests allowed from specific origins. Do not include trailing
    # slashes with URLs.
    allowedOrigins: ['*']
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
{% endhint %}

{% hint style="warning" %}
Not recommended to keep **`"cors.config"`** with **`"enabled: true"`** in production environments.

#### **Better to keep all changes in the `"development.services.yml"` file**
{% endhint %}

* Enable Twig debugging by `debug: true`  in the `development.services.yml` file.

Having a local services file. Make sure to have the right path for custom local development services file.  `sites/default/development.local.services.yml`

```php
$settings['container_yamls'][] = DRUPAL_ROOT . '/sites/default/development.local.services.yml';
```

Having a local settings `settings.local.php` file. When used in a local development environment, or in Development, Staging, or Demo hosts.

{% hint style="danger" %}
Enabling Twig debugging is not recommended in production environments.
{% endhint %}

* Disable the Twig cache by `cache: false`  in the `development.services.yml` file.

{% hint style="danger" %}
Disabling the Twig cache is not recommended in production environments.
{% endhint %}

{% hint style="info" %}
**Set up Storybook for your Drupal site.**

Please see the [@lullabot/storybook-drupal-addon](https://www.github.com/lullabot/storybook-drupal-addon#readme), which will make your Storybook aware of Drupal by connecting it to this module.


{% endhint %}

| [📋 Step-by-step tutorial 📋](https://git.drupalcode.org/project/cl\_server/-/blob/2.x/docs/storybook.md) |
| --------------------------------------------------------------------------------------------------------- |

#### Change the Local Development Domain

* Change `varbase.local` in the **`package.json`** file to the appropriate local or development domain name.
* Replace `http://varbase.local` in the **`preview.js`** file with the base URL of your project or an environment variable representing the local or development domain.
* Open a command terminal window and navigate to your project's directory.
* Run the **`yarn install`** command in the terminal to install the necessary dependencies.
* Run the **`yarn storybook:dev`** command to start the development site for the **Storybook**.
* The default browser will open, displaying the list of Default Varbase Components in the Storybook.

### Storybook Build

Building the storybook ones for the project, only for demos, staging, or hosted  development, when the other ports are not allowed.

Run the **`yarn storybook:build`** command to build the story, in the local or in at the dev, test, staging, or demo server.

{% hint style="danger" %}
#### Not for production!!, only for development or staging.
{% endhint %}

A domain name could point at the storybook folder.

**Example:**

1. An example development, staging or demo  `my-staging-varbase-site.com` domain name can point at the  `docroot` directory, which will bootstrap from **Varbase**
2. A sub domain `storybook.my-staging-varbase-site.com` domain name can point at the `storybook` directory, which will load the **Varbase Storybook**, and the **Component Library Server** will have requests from the `my-staging-varbase-site.com`

## Customizing Varbase Storybook for a Project:

### **Switching Between Themes**

To showcase a custom cloned generated theme, uncomment and modify the following line in the **`.storybook/preview.js`** file:

&#x20;`// mytheme: {title: 'My Custom Theme for a Project'}`&#x20;

### **Show Custom Vartheme BS5's Components**

To include components from **Vartheme BS5 Starterkit**, uncomment and modify the following line in the `.storybook/main.js` file:

```
"../docroot/themes/contrib/vartheme_ba5/components/**/*.mdx",
"../docroot/themes/contrib/vartheme_ba5/components/**/*.stories.@(json|yml)",
```

### Show Custom Theme**'s Components**

In case of having a custom theme for a project by

{% content-ref url="creating-your-own-theme.md" %}
[creating-your-own-theme.md](creating-your-own-theme.md)
{% endcontent-ref %}

To include components from a custom cloned generated theme, uncomment and modify the following line in the `.storybook/main.js` file:

```
"../docroot/themes/custom/mytheme/components/**/*.mdx",
"../docroot/themes/custom/mytheme/components/**/*.stories.@(json|yml)",
```

{% hint style="warning" %}
Please ensure that the path to the custom theme is correct. It should be located either in `"../docroot/themes"` or `"../docroot/themes/custom"`&#x20;
{% endhint %}

### Show Custom Module**'s Components**

To include components from a custom module, uncomment and modify the following line in the `.storybook/main.js` file:

```
"../docroot/modules/custom/my_custom_module/components/**/*.mdx",
"../docroot/modules/custom/my_custom_module/components/**/*.stories.@(json|yml)",
```

## More Information About Bootstrap \~5.3.0 Theme Color Modes

{% hint style="info" %}
In the `` main.js` `` file:\


* Add the attribute `data-bs-theme='dark'` to the body tag of the inner iframe in the canvas only when necessary. The default value is `data-bs-theme='light'`.
* Bootstrap now supports color modes, or themes, starting from version **\~5.3.0.** You can explore the default light color mode and the new dark mode, or create your own theme using Bootstrap's styles as a template.\
  [https://getbootstrap.com/docs/5.3/customize/color-modes/](https://getbootstrap.com/docs/5.3/customize/color-modes/)
{% endhint %}

<figure><img src="../../.gitbook/assets/Varbase-Components-Atoms-Progress-Bar-Progress-Bar-⋅-Storybook--light.png" alt=""><figcaption><p><strong>Varbase Components</strong> in <strong>Storybook</strong> with <strong>Bootstrap 5.3.0</strong> <code>"light"</code> theme color mode</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/Varbase-Components-Atoms-Progress-Bar-Progress-Bar-⋅-Storybook--dark.png" alt=""><figcaption><p><strong>Varbase Components</strong> in <strong>Storybook</strong> with <strong>Bootstrap 5.3.0</strong> <code>"dark"</code> theme color mode</p></figcaption></figure>



<figure><img src="../../.gitbook/assets/Varbase-Components-Organisms-Impressed-Card-Impressed-Card-⋅-Storybook.png" alt=""><figcaption><p>Example <strong>Impressed</strong> <strong>Card SDC Component</strong> and <strong>UI Pattern</strong> as a Story in <strong>Varbase Storybook</strong></p></figcaption></figure>

## Run Varbase Storybook in Platform.sh

Having a working Storybook for development, testing or staging.

{% hint style="danger" %}
**NOT** for production environments.
{% endhint %}

### Select The Varbase Template as The Project Type

Choose [**Vardot/platformsh-varbase**](https://github.com/Vardot/platformsh-varbase) from the pre-existing code base template to start a project with.

<figure><img src="../../.gitbook/assets/Select-project-type-Platform-sh.png" alt=""><figcaption><p>Click on Use a Template</p></figcaption></figure>



Select **Varbase** as the template, by default a **Varbase 10** will be built

<figure><img src="../../.gitbook/assets/Select-your-template-Platform-sh--select-Varbase.png" alt=""><figcaption><p>Select Varbase as the Template</p></figcaption></figure>

After creating the project and installing Varbase 10

### Edit the **`applications.yaml`**  File in the `.platform` Folder

```yaml
# -------------------------------------------------------------
#   Uncomment the following when start a storybook in development or staging
#         NOT for production environments.
#
#    Follow with Integration of Varbase with Storybook
#    https://docs.varbase.vardot.com/v/10.0.x/developers/theme-development-with-varbase/integration-of-varbase-with-storybook
#
#         This will allow for a start of a storybook:http upstream
# -------------------------------------------------------------
# -   name: storybook
#     type: 'nodejs:18'
#     source:
#         root: "/"
#     dependencies:
#         php:
#             "composer/composer": "~2.0"
#         nodejs:
#             npm: "^6.10"
#             node: "^18.17"
#             yarn: "^1.22"
#     disk: 512
#     build:
#         flavor: none
#     variables:
#         env:
#             NODE_OPTIONS: --max-old-space-size=4096
#             STORYBOOK_CL_SERVER_DOMAIN: 'varbase.local'
#     hooks:
#         build: |
#             set -e
#             cd $PLATFORM_APP_DIR
#             composer install --ignore-platform-reqs --no-scripts
#             yarn install --frozen-lockfile
#             yarn storybook:build
#         post_deploy: |
#             cd $PLATFORM_APP_DIR/.storybook/
#             export STORYBOOK_CL_SERVER_DOMAIN=$(node setup-storybook.js)
#             echo "STORYBOOK_CL_SERVER_DOMAIN: $STORYBOOK_CL_SERVER_DOMAIN"
#     web:
#         locations:
#             '/':
#                 root: 'storybook'
#                 passthru: true
#                 index: ["index.html"]
#                 allow: true
#                 headers:
#                     Access-Control-Allow-Origin: "*"
#                     Access-Control-Expose-Headers: "true"
#                     Access-Control-Max-Age: "false"
#                     Access-Control-Allow-Credentials: "true"
#         commands:
#             start: |
#                 sleep infinity
```

```yaml
# -------------------------------------------------------------
#   Uncomment the following when start a storybook in development or staging
#         NOT for production environments.
#
#    Follow with Integration of Varbase with Storybook
#    https://docs.varbase.vardot.com/v/10.0.x/developers/theme-development-with-varbase/integration-of-varbase-with-storybook
#
#         This will allow for origin
# -------------------------------------------------------------
#    headers:
#        Access-Control-Allow-Origin: "*"
#        Access-Control-Expose-Headers: "true"
#        Access-Control-Max-Age: "false"
#        Access-Control-Allow-Credentials: "true"

```

### Edit the **`routes.yaml`** File in the `.platform` Folder

```yaml
# ---------------------------------------------------------------------------
#   Uncomment the following when start a storybook in development or staging
#         NOT for production environments.
#
#    Follow with Integration of Varbase with Storybook
#    https://docs.varbase.vardot.com/v/10.0.x/developers/theme-development-with-varbase/integration-of-varbase-with-storybook
#
#         This will allow for a storybook sub domain to point
#         at the storybook:http upstream
# ---------------------------------------------------------------------------
# "https://storybook.{default}":
#     type: upstream
#     upstream: "storybook:http"
```

### Replace Site URL with an Environment URL

Edit the **`preview.js`** file in the **`.storybook`** folder

```json
    server: {
      // Replace this with your Drupal site URL, or an environment variable.
      url: process.env.STORYBOOK_CL_SERVER_DOMAIN,
    },
```

### Use 'development.local.services.yml' File

Have the following in the `settings.platformsh.php` file

```php
/*
 *   Use the 'development.local.services.yml' file for development or staging, and storybook.
 *        NOT for production environments.
 */
if (!$platformsh->onProduction() || !$platformsh->onDedicated()) {
  $settings['container_yamls'][] = $app_root . '/' . $site_path . '/development.local.services.yml';
}
```

Both files are in the  [**Vardot/platformsh-varbase**](https://github.com/Vardot/platformsh-varbase) project template.

After committing and starting the development environment for the development branch,

The Storybook link will work as follow

```yaml
https://storybook.{default}
```

## Related Integration Issues

* [Integrate Varbase Project with Storybook using Component Libraries: Theme Server for Varbase Components and Vartheme BS5 with and Bootstrap 5.3.0 #182](https://github.com/Vardot/varbase-project/issues/182)
* [#3372551: Integrate Varbase Components with Storybook using Component Libraries: Theme Server and Bootstrap 5.3.0](https://www.drupal.org/project/varbase\_components/issues/3372551)
* [#3372546: Integrate Vartheme BS5 with Storybook using Component Libraries: Theme Server for Varbase Components](https://www.drupal.org/project/vartheme\_bs5/issues/3372546)
