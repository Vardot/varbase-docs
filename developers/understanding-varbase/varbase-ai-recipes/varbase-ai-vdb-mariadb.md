# Varbase AI VDB: MariaDB

The **Varbase AI VDB: MariaDB** recipe uses MariaDB's built-in vector type as the vector database for AI search. The vectors live in the site's own database, so no extra service is needed. A separate MariaDB server also works.

It is one of two vector database recipes for [**Varbase AI Search Base**](varbase-ai-search-base.md). Apply one of them, not both.

## Recipe Type

Varbase AI

## Drupal.org Project

[https://www.drupal.org/project/varbase\_ai\_vdb\_mariadb](https://www.drupal.org/project/varbase_ai_vdb_mariadb)

{% hint style="warning" %}
**Alpha release.** The MariaDB vector provider it installs has a stable release. This recipe is not covered by the Drupal security advisory policy. Try it on a development site first.
{% endhint %}

## What It Adds

- Installs **AI**, **AI Search** and the **MariaDB VDB Provider**.
- Keeps the provider on the site's own database connection.
- Makes MariaDB the site's default vector database, which **Varbase AI Search Base** reads.

It does not create a search index. That is the job of **Varbase AI Search Base**.

## Before You Apply

- Apply [**Varbase AI Base**](varbase-ai-base.md) first.
- The database must run **MariaDB 11.7 or later**. DDEV with MariaDB 11.8 works. Check it at **Administration** \ **Reports** \ _**Status report**_.
- **Varbase Search Base** must already be applied (a Varbase site has it). The provider fails on a search index with no server, which that recipe creates.

## Installation

Add the recipe with Composer, then apply it with Drush:

```bash
ddev composer require drupal/varbase_ai_vdb_mariadb:~1
ddev drush cr
ddev drush recipe ../recipes/varbase_ai_vdb_mariadb
ddev drush cr
```

**Varbase AI Search Base** stores its vectors in a database called `varbase_ai_search`. It must exist and the site's database user must have access to it. On DDEV:

```bash
ddev exec "mysql -hdb -uroot -proot -e \"CREATE DATABASE IF NOT EXISTS varbase_ai_search; GRANT ALL PRIVILEGES ON varbase_ai_search.* TO 'db'@'%'; FLUSH PRIVILEGES;\""
```

On a hosted site, a database administrator does this step.

## A Separate MariaDB Server

Use a separate server when the vectors should not share the site's database, for example for a high volume of vector writes.

1. Run **MariaDB 11.7 or later** on the server. Create a database, and a user with all privileges on that database only.
2. Add the connection to `settings.php`, and read the values from the environment. A recipe cannot write `settings.php`, and the password must never be stored in configuration:

```php
$config['ai_vdb_provider_mariadb.settings'] = [
  'use_drupal_database' => FALSE,
  'host' => getenv('VDB_MARIADB_HOST'),
  'port' => 3306,
  'username' => getenv('VDB_MARIADB_USER'),
  'password' => getenv('VDB_MARIADB_PASSWORD'),
  'database' => getenv('VDB_MARIADB_DATABASE'),
];
```

{% hint style="warning" %}
The provider has no TLS option, so keep the server on a private network. With a separate server, vector changes no longer roll back with content changes. The status report checks only the site's own database for MariaDB 11.7, never the separate server.
{% endhint %}

## Hosted Sites

A hosted database below MariaDB 11.7 has no vector type: the status report shows an error, and creating a collection fails. Upgrade the database service first. On most hosts an upgrade is one way, and a downgrade deletes the data, so back up before you upgrade.
