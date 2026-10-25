# Varbase AI VDB: Milvus

The **Varbase AI VDB: Milvus** recipe connects the site to a **Milvus** vector database for AI search. Milvus can run inside the same DDEV project, on Zilliz Cloud, or on a server of your own.

It is one of two vector database recipes for [**Varbase AI Search Base**](varbase-ai-search-base.md). Apply one of them, not both.

## Recipe Type

Varbase AI

## Drupal.org Project

[https://www.drupal.org/project/varbase\_ai\_vdb\_milvus](https://www.drupal.org/project/varbase_ai_vdb_milvus)

{% hint style="warning" %}
**Alpha release.** The Milvus VDB provider has no stable release yet. This recipe is not covered by the Drupal security advisory policy. Try it on a development site first.
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
ddev composer require drupal/varbase_ai_vdb_milvus:~1
ddev drush cr
ddev drush recipe ../recipes/varbase_ai_vdb_milvus
ddev drush cr
```

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

{% hint style="warning" %}
The local DDEV Milvus has no authorization. Keep it on the private DDEV network and never publish its ports.
{% endhint %}

## Where Milvus Runs

| | Local: DDEV | Zilliz Cloud | Your Own Server |
|---|---|---|---|
| `MILVUS_SERVER` | `http://milvus` (the default) | `https://<cluster>.zillizcloud.com` | `https://milvus.example.com` |
| `MILVUS_PORT` | `19530` (the default) | `443` | `19530`, or `443` behind TLS |
| `MILVUS_API_KEY` | Not set | The Zilliz API token | `root:<password>` |
| `api_key` input | Empty (the default) | `milvus_api_key` | `milvus_api_key` |

For a remote server, set the three variables in the environment of the web server, never in configuration. In DDEV, use `web_environment` in `.ddev/config.local.yaml`. Then apply with the key:

```bash
ddev drush recipe ../recipes/varbase_ai_vdb_milvus --input=varbase_ai_vdb_milvus.api_key=milvus_api_key
```

On a remote server, create the `varbase_ai_search` database the same way as in DDEV, at `<server>:<port>/v2/vectordb/databases/create`, with `-H "Authorization: Bearer $MILVUS_API_KEY"` when the server has authorization.

{% hint style="warning" %}
Do not pass `api_key=milvus_api_key` while `MILVUS_API_KEY` is unset. The provider then fails with `TypeError: setApiKey(): Argument #1 must be of type string, null given`. Leave `api_key` empty only for a Milvus without authorization.
{% endhint %}

**Zilliz Cloud:** create a cluster, and copy its public endpoint and API token from the Zilliz console. Zilliz Cloud serverless has no database name to choose; enter any name, such as `default`.

**Your own server:** the DDEV service file is a working starting point. Before it faces anything else, turn on authorization (`COMMON_SECURITY_AUTHORIZATIONENABLED: "true"`) and change the default `root` password. Publish only the REST port, behind a TLS reverse proxy that allows only the site's addresses.

## Different Milvus per Environment

The recipe stores the server and port in configuration, which moves between environments. To use the DDEV Milvus locally and a remote one on the live site, read them from the environment in `settings.php`, which wins over stored configuration:

```php
$config['ai_vdb_provider_milvus.settings']['server'] = getenv('MILVUS_SERVER') ?: 'http://milvus';
$config['ai_vdb_provider_milvus.settings']['port'] = (int) (getenv('MILVUS_PORT') ?: 19530);
$config['ai_vdb_provider_milvus.settings']['api_key'] = getenv('MILVUS_API_KEY') ? 'milvus_api_key' : '';
```

## Known Limitations

- Clearing a search index drops the collection from the default Milvus database, not from `varbase_ai_search`, so old vectors can stay.
- A DDEV project that switches to the single-container Milvus service file starts with an empty Milvus. Create the `varbase_ai_search` database again, then index the content again.
