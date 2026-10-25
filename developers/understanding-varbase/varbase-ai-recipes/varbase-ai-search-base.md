# Varbase AI Search Base

The **Varbase AI Search Base** recipe builds a vector index of the site's own content. It is the retrieval half of **Ask AI**, and Varbase never applies it by default. It indexes every published node and Canvas page, in all languages, into the site's default vector database. **Varbase AI Chatbot Base** and **Varbase AI Answers Base** answer from this index.

## Recipe Type

Varbase AI

## Drupal.org Project

[https://www.drupal.org/project/varbase\_ai\_search\_base](https://www.drupal.org/project/varbase_ai_search_base)

{% hint style="warning" %}
**Alpha release.** AI Search is an experimental module. This recipe is not covered by the Drupal security advisory policy. Try it on a development site first.
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
ddev composer require drupal/varbase_ai_search_base:~1
ddev drush cr
ddev drush recipe ../recipes/varbase_ai_search_base
ddev drush cr
```

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

## Checking the Index

```bash
ddev drush search-api:status content_vector
ddev drush search-api:search content_vector "mobile first websites"
```

The status must reach 100%. No results with the index at 100% means the vector database is not answering: check the provider settings and the Search API server's status page.

After changing the chunk settings or the embeddings model, run `search-api:clear`, then `search-api:index`.

## Known Limitations

- The index has no language field yet, so search cannot filter by language.
- Unpublished content is not indexed.
- With the **MariaDB** provider, saving a search index that has no server yet fails. Apply **Varbase Search Base** before installing the provider. A Varbase site already has it.
- With the **Milvus** provider, clearing the index drops the collection from the default Milvus database, not from `varbase_ai_search`. Vectors of removed content can stay.

## Design Notes

- **Provider agnostic.** The index uses the site's default vector database. The recipe does not name a provider, so another provider works without changing it.
- **One recipe per vector database.** **Varbase AI VDB: MariaDB** and **Varbase AI VDB: Milvus** are separate recipes, so this one stays independent of them. Each can run in DDEV or against a remote server.
- **MariaDB** is the only provider with a stable release. It needs MariaDB 11.7 or later and no extra service.
- **Milvus** was the first backend chosen. It needs no PHP extension, but runs as a separate service, since common hosting has no Milvus service.
- **Not offered:** PostgreSQL with pgvector (including the amazee.io managed database) needs the `pdo_pgsql` extension, which the Varbase hosting templates do not load. The released SQLite provider fails every vector search. The Qdrant provider requires an AI Search version that collides with the one in **AI Core**.
