# Varbase Application Installation and Setup Requirements

> No hardware? No problem! [Try using Varbase in the Cloud](https://www.vardot.com/products-services/product-info/varbase-enterprise-website-platform#block-webform-request-free-demo).  
> No installation required, request your access in 5 mins.  
> With an option to migrate to your own server later

---

## Client-side requirements

| **Component** | **Description** |
| :--- | :--- |
| **Browser** | A browser with ability to fully execute JavaScript from Varbase to access its full functionality. |

## 

## Server-side requirements for evaluation
| **Component** | **Description** |
| :--- | :--- |
| PHP | <ul><li>PHP version 5.6 or higher. PHP 7 is recommended.</li><li>PHP extensions: `mysqli` <em>(for MySQL)</em>, `pgsql` <em>(for PostgreSQL)</em>, `xml`, `gd`, `openssl`, `json`, `curl`, `mbstring`, `date`, `dom`, `filter`, `hash`, `pcre`, `pdo`, `session`, `SimpleXML`, `SPL`, `tokenizer`, `mcrypt`</li></ul> |
| Applications | <ul><li>Composer</li><li>Drush 9 or higher</li></ul> |
| Web Server | Varbase works on any web server with PHP version of 5.6 or higher.<ul><li>Apache 2.x <em>(recommended)</em></li><li>Nginx</li><li>Microsoft IIS</li></ul>`mod_rewrite` is required if you use Apache.<br />`ngx_http_rewrite_module` if you use Nginx. |
| Database Engine | Varbase works on any multiple database engines: <ul><li>MySQL (or an equivalent such as MariaDB or Percona Server) <em>(recommended)</em></li><li>PostgreSQL 9.1.2 or higher</li><li>SQLite 3.6.8 or higher</li></ul> |

## 

## Server-side requirements for production

| **Component** | **Description** |
| :--- | :--- |
| PHP | <ul><li>PHP version 5.6 or higher. PHP 7 is recommended.</li><li>PHP extensions: mysqli <em>(for MySQL)</em>, pgsql <em>(for PostgreSQL)</em>, xml, gd, openssl, json, curl, mbstring, date, dom, filter, hash, pcre, pdo, session, SimpleXML, SPL, tokenizer, mcrypt</li></ul> |
| Applications | <ul><li>Composer</li><li>Drush 9 or higher</li></ul> |
| Web Server | Varbase works on any web server with PHP version of 5.6 or higher.<ul><li>Apache 2.x <em>(recommended)</em></li><li>Nginx</li><li>Microsoft IIS</li></ul>`mod_rewrite` is required if you use Apache.<br />`ngx_http_rewrite_module` if you use Nginx. |
| Database Engine | Varbase works on any multiple database engines: <ul><li>MySQL (or an equivalent such as MariaDB or Percona Server) <em>(recommended)</em></li><li>PostgreSQL 9.1.2 or higher</li></ul> |



##### Additional recommended components for production use

| **Component** | **Description** |
| :--- | :--- |
| Memcache | <ul><li>Memcached server daemon</li><li>PECL Memcache or PHP Memcached libraries</li></ul> |
| Varnish | Varnish cache, an advanced and very fast reverse-proxy system. |
| Database Engine | Varbase works on any multiple database engines: <ul><li>MySQL (or an equivalent such as MariaDB or Percona Server) <em>(recommended)</em></li><li>PostgreSQL 9.1.2 or higher</li></ul> |



##### Solr Search requirements (if you use search)

| **Component** | **Description** |
| :--- | :--- |
| Solr Search | Solr search server. Versions 4.x, 5.x or 6.x are all compatible. |