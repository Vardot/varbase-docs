# Managing URL Aliases

After configuring Pathauto patterns, you may need to manage existing URL aliases -- including bulk generating aliases for existing content, deleting outdated aliases, or manually editing individual aliases.

## Accessing URL Alias Management

Navigate to **Configuration > URL aliases** in the Drupal admin interface, or go directly to:

```
/admin/config/search/path
```

## Viewing Existing Aliases

The URL aliases listing page displays all current aliases on the site. You can:

- **Filter** aliases by path or alias text to find specific entries.
- **Edit** individual aliases by clicking the edit link next to each entry.
- **Delete** individual aliases that are no longer needed.

## Bulk Generating Aliases

If you have added or changed Pathauto patterns and need to generate aliases for existing content that does not yet have one, use the bulk generation tool:

1. Navigate to **Configuration > URL aliases > Bulk generate**, or go to:

```
/admin/config/search/path/update_bulk
```

2. Select the entity types for which you want to generate aliases (for example, Content, Taxonomy terms, Users).
3. Choose whether to generate aliases only for entities that do not already have one, or regenerate all aliases.
4. Click **Update** to start the bulk generation process.

{% hint style="warning" %}
Regenerating all aliases will overwrite any manually customized aliases. Use this option with caution on production sites.
{% endhint %}

## Bulk Deleting Aliases

To remove all automatically generated aliases:

1. Navigate to **Configuration > URL aliases > Delete aliases**, or go to:

```
/admin/config/search/path/delete_bulk
```

2. Select the entity types for which you want to delete aliases.
3. Choose whether to delete all aliases or only automatically generated ones.
4. Click **Delete aliases** to proceed.

## Manually Editing an Alias

You can override the automatic alias for any individual piece of content:

1. Edit the content node (or taxonomy term, user, etc.).
2. Expand the **URL alias** section in the sidebar or at the bottom of the form.
3. Uncheck **Generate automatic URL alias**.
4. Enter the desired custom alias.
5. Save the content.

The custom alias will persist even when Pathauto patterns change, unless you re-enable automatic alias generation for that entity.

## Redirect Handling

When a URL alias is changed, the **Redirect** module (installed by the Varbase SEO Base recipe) can automatically create a redirect from the old alias to the new one. This preserves any existing links or bookmarks pointing to the old URL.

Redirect settings can be configured at **Configuration > URL aliases > Redirect settings**:

```
/admin/config/search/redirect/settings
```
