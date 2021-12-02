# Requirements

> No hardware? No problem! [Try using Varbase in the Cloud](https://www.vardot.com/en-us/solutions/varbase#vbp-1518).\
> No installation required, request your access in 5 mins.\
> With an option to migrate to your own server later

## Client-side Requirements

| **Component** | **Description**                                                                                       |
| ------------- | ----------------------------------------------------------------------------------------------------- |
| **Browser**   | A browser with the ability to fully execute JavaScript from Varbase to access its full functionality. |

## Server-side Requirements for Evaluation or Development

The below requirements outline the minimum needed requirements. If you need help sizing your server, please contact us at [https://www.vardot.com/contact-us](https://www.vardot.com/contact-us) for consultation.

* **Disk space**: Minimum 300MB for codebase, 5GB for files, and 1GB for the database _(Will greatly depend on your application data and usage)_.
* **Memory**: Minimum of 2GB (for 1 host). Minimum PHP memory of 196MB _(might need to increase this as your Varbase site's functionalities increase)._
* **CPU**: Minimum of 2 CPUs is recommended (for 1 host).

| **Component**   | **Description**                                                                                                                                                                                                                                                    |
| --------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| PHP             | <p>PHP 7.3 or higher. PHP 7.4 is recommended.</p><p>PHP extensions: mysqli (for MySQL), pgsql (for PostgreSQL), xml, gd, openssl, json, curl, mbstring, date, dom, filter, hash, pcre, pdo, session, SimpleXML, SPL, tokenizer, mcrypt</p>                         |
| Applications    | <p>Composer</p><p>Drush 10 or higher</p><p>Git</p>                                                                                                                                                                                                                 |
| Web Server      | <p></p><p>Varbase works on any web server with PHP version of 7 or higher. <code>mod_rewrite</code> is required if you use Apache.</p><p><code>ngx_http_rewrite_module</code> if you use Nginx.</p>                                                                |
| Database Engine | <p>Varbase works on any multiple database engines. MySQL, MariaDB or Percona Server (Recommended)</p><ul><li>MySQL 8 is supported only on Varbase 8.6.x or higher</li><li>Required MySQL 5.5.3/MariaDB 5.5.20/Percona Server 5.5.8 or higher with InnoDB</li></ul> |

To deploy and run Varbase your web server must meet certain minimum requirements. We recommend sizing your application and considering your database size, files data, and expected traffic.

Your servers' requirements will greatly be impacted by the usage of your application. For example, if you have more logged-in users that anonymous users, you will need to consider higher requirements to serve non-cached requests.



## Server-side Requirements for Production

If you need help sizing your server, please contact us at [https://www.vardot.com/contact-us](https://www.vardot.com/contact-us) for consultation.

| **Component**   | **Description**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| --------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| PHP             | <p>PHP 7.3 or higher. PHP 7.4 is recommended.</p><p>PHP extensions: mysqli <em>(for MySQL)</em>, pgsql <em>(for PostgreSQL)</em>, xml, gd, openssl, json, curl, mbstring, date, dom, filter, hash, pcre, pdo, session, SimpleXML, SPL, tokenizer, mcrypt</p><p></p><p>For production environments, PHP memory of 256MB is recommended. In some memory-intensive pages, you can <a href="https://www.drupal.org/docs/7/managing-site-performance-and-scalability/changing-php-memory-limits#s-settingsphp">optionally increase memory using <code>ini_set()</code></a>.</p> |
| Applications    | <p>Composer</p><p>Drush 10 or higher</p><p>Git</p>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| Web Server      | <p>Varbase works on any web server with a PHP version of 7.3 or higher.<code>mod_rewrite</code> is required if you use Apache.<br><code>ngx_http_rewrite_module</code> if you use Nginx.</p>                                                                                                                                                                                                                                                                                                                                                                               |
| Database Engine | <p>Varbase works on multiple database engines. MySQL, MariaDB, or Percona Server (Recommended)</p><ul><li>MySQL 8 is supported only on Varbase 8.6.x or higher</li><li>Required MySQL 5.5.3/MariaDB 5.5.20/Percona Server 5.5.8 or higher with InnoDB</li></ul>                                                                                                                                                                                                                                                                                                            |
| Memcache        | <p>Memcached server daemon</p><p>PECL Memcache or PHP Memcached libraries</p>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| Varnish         | Varnish cache, an advanced and very fast reverse-proxy system.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| Solr Search     | The minimum support Solr version is Solr 6.4 and Solr 7 is supported.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
