---
description: Drupal Libraries Management
---

# Varbase Libraries

## The NPM/Yarn Method

List of needed libraries for Varbase Projects which uses packages with NPM/YARN.

NPM/Yarn dynamic way of managing packages as libraries.

By adding all needed libraries in `"dependencies"` and `"drupal-libraries"` in the [package.json](https://github.com/Vardot/varbase-project/blob/9.1.x/package.json) file in projects.

## Available Drupal Libraries Sync Commands

| Command                               | Description                                         |
| ------------------------------------- | --------------------------------------------------- |
| `yarn drupal-libraries-sync`          | Sync libraries using Yarn  NPM/Yarn.                |
| `npm run drupal-libraries-sync`       | Sync libraries using.                               |
| `composer drupal-libraries-sync`      | Sync libraries via Composer (uses Yarn by default). |
| `composer drupal-libraries-yarn-sync` | Sync libraries via Composer using Yarn.             |
| `composer drupal-libraries-npm-sync`  | Sync libraries via Composer using NPM.              |

## Adding New Libraries

Search for packages in [https://www.npmjs.com](https://www.npmjs.com/)

### 1. Add to package.json Dependencies

```json
{
  "dependencies": {
    "npm-package-to-start-using": "^1.0.0"
  }
}
```

### 2. Configure Library Mapping

Add the library mapping to the `drupal-libraries` section:

```json
{
  "drupal-libraries": {
    "libraries": [
      { "name": "new-library", "package": "new-library" }
    ]
  }
}
```

### 3. Install and Sync

```bash
yarn install
```

{% hint style="success" %}
The `yarn install` will do the equivalent of running `yarn drupal-libraries-sync` in the `postinstall` event, when the installation of packages in `node_modules` finishes.
{% endhint %}

> #### Example:
>
> 1- Let us imagine that we need the [**chart.js**](https://www.npmjs.com/package/chart.js) npm library in a project, to be used with the [**Chart**](https://www.drupal.org/project/charts)  **module** along with the [**C3**](https://www.npmjs.com/package/c3) and [**D3**](https://www.npmjs.com/package/d3) npm libraries. (Search for packages in [https://www.npmjs.com](https://www.npmjs.com/))
>
>
>
> 2- Add the following in `"dependencies"`
>
> ```bash
>     "chart.js": "~4",
>     "d3": "~5",
>     "c3": "0.7.*",
> ```
>
> 3- Add the following in `drupal-libraries.libraries`
>
> ```json
>   {"name": "chartjs", "package": "chart.js"},
>   {"name": "c3", "package": "c3"},
>   {"name": "d3", "package": "d3"},
> ```
>
> 4- Run the following script to sync selected drupal libraries from node\_module to docroot/libraries.
>
> <pre class="language-bash"><code class="lang-bash"><strong>yarn install
> </strong></code></pre>
>
> 5- Check that you do have the new libraries in your `docroot/libraries` folder.
>
> 6- Notice that the package `chart.js` was copied from `node_modules` and when the `chartjs` name, as the [**Chart**](https://www.drupal.org/project/charts) **module** was developed to locate the `chartjs` folder in libraries.

{% hint style="warning" %}
Make sure that you commit the libraries with git. It is **no longer ignored** in the `.gitignore` file
{% endhint %}

For more examples have a look at `"dependencies"` and `"drupal-libraries"` in the [package.json](https://github.com/Vardot/varbase-project/blob/9.1.x/package.json)

## Removing No Longer Needed Libraries

### 1. Remove from the package.json file.

Remove the library from both `dependencies` and `drupal-libraries.libraries` sections.

### 2. Clean Up Files

<pre class="language-bash" data-title="Remove the library directory from libraries"><code class="lang-bash"><strong>rm -rf docroot/libraries/used-npm-package
</strong></code></pre>

## Troubleshooting

### Libraries Not Appearing

1. Verify `package.json` syntax is valid
2. Check that the library mapping in `drupal-libraries.libraries` is correct
3. Ensure the sync script exists at `./docroot/profiles/contrib/varbase/scripts/drupal-libraries-sync.js`
4. Run sync command manually: `yarn drupal-libraries-sync`

### Permission Issues

{% code title="Fix permissions if needed" overflow="wrap" %}
```bash
chmod +x ./docroot/profiles/contrib/varbase/scripts/drupal-libraries-sync.js
```
{% endcode %}

## Switch from Asset Packagist to NPM/Yarn

{% content-ref url="varbase-libraries/migrating-existing-projects-to-npm-yarn-with-drupal-libraries-sync.md" %}
[migrating-existing-projects-to-npm-yarn-with-drupal-libraries-sync.md](varbase-libraries/migrating-existing-projects-to-npm-yarn-with-drupal-libraries-sync.md)
{% endcontent-ref %}

{% content-ref url="varbase-libraries/the-composer-method-deprecated.md" %}
[the-composer-method-deprecated.md](varbase-libraries/the-composer-method-deprecated.md)
{% endcontent-ref %}
