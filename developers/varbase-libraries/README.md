# Varbase Libraries

Varbase 11.0.x installs the front-end libraries that its modules need with **Composer**. Each library is a `drupal-library` package, and the project template puts it in `web/libraries/{$name}`. No Node.js step is needed to get them.

{% hint style="info" %}
Before Varbase 11.0.0, the libraries came from NPM or Yarn and a `drupal-libraries-sync` script. That script was dropped in Varbase 11.0.0 ([#3620357](https://www.drupal.org/i/3620357)). See [NPM/YARN with drupal-libraries-sync](npm-yarn-drupal-libraries-sync.md) if you maintain a site built before that.
{% endhint %}

## Libraries and the Recipes That Require Them

| Library package | Folder in `web/libraries/` | Required by |
| --- | --- | --- |
| [`vardot/ace`](https://github.com/Vardot/ace) | `ace` | **Ace Editor** module |
| [`vardot/aos`](https://github.com/Vardot/aos) | `aos` | **Varbase Content Base** |
| [`vardot/ckeditor5-anchor-drupal`](https://github.com/Vardot/ckeditor5-anchor-drupal) | `ckeditor5-anchor-drupal` | **Anchor Link** module |
| [`vardot/ckeditor5-media-embed-drupal`](https://github.com/Vardot/ckeditor5-media-embed-drupal) | `ckeditor5` | **Varbase Editor Base** |
| [`vardot/dropzone`](https://github.com/Vardot/dropzone) | `dropzone` | **Varbase Media Base** |
| [`vardot/jquery.fancytree`](https://github.com/Vardot/jquery.fancytree) | `jquery.fancytree` | **Varbase Admin Base** |
| [`vardot/swagger-ui`](https://github.com/Vardot/swagger-ui) | `swagger-ui` | **Varbase API Base** |

Other libraries come from their own modules, for example `drupal/klaro_js` for **Klaro** and `drupal/nouislider_js` for **Better Exposed Filters** sliders.

Source: the `composer.json` of each recipe and the `composer.lock` of a Varbase 11.0.0 project.

## Where the Libraries Go

The project template maps the package type to the folder:

```json
"installer-paths": {
    "web/libraries/{$name}": [
        "type:drupal-library"
    ]
}
```

## Updating a Library

Libraries update with the rest of the project:

```bash
ddev composer update "vardot/*" --with-dependencies
ddev drush cache:rebuild
```

## Adding Your Own Library

Require a package of type `drupal-library` and it lands in `web/libraries/`. If the library has no such package, add a `package` repository to your root `composer.json` that points at the library's release archive.

## Sections

### [NPM/YARN with drupal-libraries-sync](npm-yarn-drupal-libraries-sync.md)

The NPM and Yarn workflow used before Varbase 11.0.0.
