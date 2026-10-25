# Varbase AI Search Base

The **Varbase AI Search Base** recipe builds a vector index of the site's own content. It indexes every published node and Canvas page, in all languages, into the site's default vector database. **Varbase AI Chatbot Base** and **Varbase AI Answers Base** answer from this index.

## Recipe Type

Varbase AI

## Drupal.org Project

[https://www.drupal.org/project/varbase\_ai\_search\_base](https://www.drupal.org/project/varbase_ai_search_base)

{% hint style="warning" %}
**Alpha release.** Version 1.0.0-alpha1. AI Search is an experimental module. This recipe is not covered by the Drupal security advisory policy. Try it on a development site first.
{% endhint %}

## What It Adds

- Applies **Varbase Search Base** first.
- Adds a `search_index` display per content type, which renders content to clean text for indexing.
- Creates the `content_vector` Search API server and index on the site's default vector database.
- Stops before changing anything when no default embeddings model is set.

Content is indexed again when it is saved and on cron.

## Before You Apply

1. Apply [**Varbase AI Base**](varbase-ai-base.md). It sets the default chat and embeddings models.
2. Apply **one** vector database recipe: [**Varbase AI VDB: MariaDB**](varbase-ai-vdb-mariadb.md) or [**Varbase AI VDB: Milvus**](varbase-ai-vdb-milvus.md). It must be the site's default vector database, and the `varbase_ai_search` database must exist.

## Installation

Add the recipe with Composer, then apply it with Drush:

```bash
ddev composer require drupal/varbase_ai_search_base:~1.0.0@alpha
ddev drush cr
ddev drush recipe ../recipes/varbase_ai_search_base
ddev drush cr
```

Add `drupal/varbase_ai_search_base` to the recipe unpack ignore list first, as described in [Installing the Alpha Recipes](README.md#installing-the-alpha-recipes).

Then index the content and check it:

```bash
ddev drush search-api:index content_vector
ddev drush search-api:status content_vector
```

{% hint style="info" %}
Every indexed chunk costs one call to the embeddings provider. Review the provider pricing before indexing a large site.
{% endhint %}

{% hint style="warning" %}
The recipe can be applied once. To apply it again, delete the `content_vector` index and server first at **Administration** \ **Configuration** \ **Search and metadata** \ _**Search API**_.
{% endhint %}
