# Varbase AI VDB: Milvus

The **Varbase AI VDB: Milvus** recipe connects the site to a **Milvus** vector database for AI search. Milvus can run inside the same DDEV project, on Zilliz Cloud, or on a server of your own.

It is one of two vector database recipes for [**Varbase AI Search Base**](varbase-ai-search-base.md). Apply one of them, not both.

## Recipe Type

Varbase AI

## Drupal.org Project

[https://www.drupal.org/project/varbase\_ai\_vdb\_milvus](https://www.drupal.org/project/varbase_ai_vdb_milvus)

{% hint style="warning" %}
**Alpha release.** Version 1.0.0-alpha1. The Milvus VDB provider has no stable release yet. This recipe is not covered by the Drupal security advisory policy. Try it on a development site first.
{% endhint %}

## What It Adds

- Installs **Key**, **AI**, **AI Search** and the **Milvus VDB Provider**.
- Creates a `milvus_api_key` key that reads the `MILVUS_API_KEY` environment variable.
- Points the provider at the Milvus server and port from the recipe inputs.

It does not create a search index. That is the job of **Varbase AI Search Base**.

## Install-Time Inputs

| Input | Default | Purpose |
|---|---|---|
| `server` | `MILVUS_SERVER`, otherwise `http://milvus` | The Milvus address, with the scheme and without the port. |
| `port` | `MILVUS_PORT`, otherwise `19530` | The REST port. Zilliz Cloud uses `443`. |
| `api_key` | empty | The key that holds the token. Leave it empty for the local DDEV Milvus. Use `milvus_api_key` for a remote server. |

## Before You Apply

- Apply [**Varbase AI Base**](varbase-ai-base.md) first.
- Have a Milvus 2.6 server. For local work, the recipe ships a DDEV service file.

## Installation

Add the recipe with Composer, then apply it with Drush:

```bash
ddev composer require drupal/varbase_ai_vdb_milvus:~1.0.0@alpha
ddev drush cr
ddev drush recipe ../recipes/varbase_ai_vdb_milvus
ddev drush cr
```

Add `drupal/varbase_ai_vdb_milvus` to the recipe unpack ignore list first, as described in [Installing the Alpha Recipes](README.md#installing-the-alpha-recipes).

For a local Milvus in DDEV, add the service before applying the recipe:

```bash
cp recipes/varbase_ai_vdb_milvus/ddev/docker-compose.milvus.yaml .ddev/
ddev restart
```

This recipe does not change the site's default vector database. Make Milvus the default, so **Varbase AI Search Base** uses it:

```bash
ddev drush cset ai.settings default_vdb_provider milvus -y
```

Then create the `varbase_ai_search` database that **Varbase AI Search Base** uses:

```bash
ddev exec 'curl -s http://milvus:19530/v2/vectordb/databases/create -X POST -H "Content-Type: application/json" -d "{\"dbName\":\"varbase_ai_search\"}"'
```

For a remote server, set `MILVUS_SERVER`, `MILVUS_PORT` and `MILVUS_API_KEY` in the environment, then apply with `--input=varbase_ai_vdb_milvus.api_key=milvus_api_key`.

{% hint style="warning" %}
The local DDEV Milvus has no authorization. Keep it on the private DDEV network and never publish its ports.
{% endhint %}
