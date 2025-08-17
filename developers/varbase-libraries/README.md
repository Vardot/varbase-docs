---
description: Drupal Libraries Management
---

# Varbase Libraries

## The NPM/Yarn Method

List of needed libraries for Varbase Projects which uses packages with NPM/YARN.

NPM/Yarn dynamic way of managing packages as libraries.

### Available Drupal Libraries Sync Commands

| Command                               | Description                                         |
| ------------------------------------- | --------------------------------------------------- |
| `yarn drupal-libraries-sync`          | Sync libraries using Yarn  NPM/Yarn.                |
| `npm run drupal-libraries-sync`       | Sync libraries using.                               |
| `composer drupal-libraries-sync`      | Sync libraries via Composer (uses Yarn by default). |
| `composer drupal-libraries-yarn-sync` | Sync libraries via Composer using Yarn.             |
| `composer drupal-libraries-npm-sync`  | Sync libraries via Composer using NPM.              |

### Adding New Libraries

#### 1. Add to package.json Dependencies

```json
{
  "dependencies": {
    "new-library": "^1.0.0"
  }
}
```

#### 2. Configure Library Mapping

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

> #### Example:
>
> 1- Let us imagine that we need the [**chart.js**](https://www.npmjs.com/package/chart.js) npm library in a project, to be used with the [**Chart module**](https://www.drupal.org/project/charts) along with the [**C3**](https://www.npmjs.com/package/c3) and [**D3**](https://www.npmjs.com/package/d3) npm libraries. (Search for packages in [https://www.npmjs.com](https://www.npmjs.com/))
>
>
>
> 2- Run the following commands
>
> ```
> yarn add chart.js
> yarn add c3
> yarn add d3
> ```
>
> 3- Add the following in `drupal-libraries.libraries`
>
> ```
>   {"name": "chartjs", "package": "chart.js"},
>   {"name": "c3", "package": "c3"},
>   {"name": "d3", "package": "d3"},
> ```
>
> 4- Run the follwoing to sync drupal libraries.
>
> ```
> yarn drupal-libraries-sync
> ```
>
> or
>
> ```
> composer drupal-libraries-sync
> ```
>
> 5- Check that you do have the new libraries in your `docroot/libraries` folder.

{% hint style="warning" %}
Make sure that you commit the libraries with git. It is **no longer ignored** in the `.gitignore` file
{% endhint %}

#### 3. Install and Sync

```bash
yarn install
yarn drupal-libraries-sync
```

### Removing No Longer Needed Libraries

#### 1. Remove from the package.json file.

Remove the library from both `dependencies` and `drupal-libraries.libraries` sections.

#### 2. Clean Up Files

```bash
# Remove the library directory
rm -rf docroot/libraries/obsolete-library

# Reinstall to ensure clean state
yarn install
yarn drupal-libraries-sync
```

### Troubleshooting

#### Libraries Not Appearing

1. Verify `package.json` syntax is valid
2. Check that the library mapping in `drupal-libraries.libraries` is correct
3. Ensure the sync script exists at `./docroot/profiles/contrib/varbase/scripts/drupal-libraries-sync.js`
4. Run sync command manually: `yarn drupal-libraries-sync`

#### Permission Issues

```bash
# Fix permissions if needed
chmod +x ./docroot/profiles/contrib/varbase/scripts/drupal-libraries-sync.js
```



{% content-ref url="migrating-existing-projects-to-npm-yarn-with-drupal-libraries-sync.md" %}
[migrating-existing-projects-to-npm-yarn-with-drupal-libraries-sync.md](migrating-existing-projects-to-npm-yarn-with-drupal-libraries-sync.md)
{% endcontent-ref %}

{% content-ref url="the-composer-method-deprecated.md" %}
[the-composer-method-deprecated.md](the-composer-method-deprecated.md)
{% endcontent-ref %}

