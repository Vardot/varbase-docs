# Requirements

> No hardware? No problem! [Try using Varbase in the Cloud](https://www.vardot.com/products-services/product-info/varbase-enterprise-website-platform#block-webform-request-free-demo).  
> No installation required, request your access in 5 mins.  
> With an option to migrate to your own server later

## Client-side Requirements

| **Component** | **Description** |
| :--- | :--- |
| **Browser** | A browser with ability to fully execute JavaScript from Varbase to access its full functionality. |

## Server-side Requirements for Evaluation or Development

The below requirements outline the minimum needed requirements. If you need help sizing your server, please contact us at [https://www.vardot.com/contact-us](https://www.vardot.com/contact-us) for consultation.

* **Disk space**: Minimum 300MB for codebase, 5GB for files, and 1GB for database _\(Will greatly depend on your application data and usage\)_.
* **Memory**: Minimum of 2GB \(for 1 host\).
* **CPU**: Minimum of 2 CPUs is recommended \(for 1 host\).

<table>
  <thead>
    <tr>
      <th style="text-align:left"><b>Component</b>
      </th>
      <th style="text-align:left"><b>Description</b>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">PHP</td>
      <td style="text-align:left">
        <p>PHP 7 or higher. PHP 7.2 is recommended.</p>
        <p>PHP extensions: mysqli <em>(for MySQL)</em>, pgsql <em>(for PostgreSQL)</em>,
          xml, gd, openssl, json, curl, mbstring, date, dom, filter, hash, pcre,
          pdo, session, SimpleXML, SPL, tokenizer, mcrypt</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Applications</td>
      <td style="text-align:left">
        <p>Composer</p>
        <p>Drush 9 or higher</p>
        <p>Git</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Web Server</td>
      <td style="text-align:left">Varbase works on any web server with PHP version of 5.6 or higher.<code>mod_rewrite</code> is
        required if you use Apache.
        <br /><code>ngx_http_rewrite_module</code> if you use Nginx.</td>
    </tr>
    <tr>
      <td style="text-align:left">Database Engine</td>
      <td style="text-align:left">
        <p>Varbase works on any multiple database engines. MySQL, MariaDB or Percona
          Server (Recommended)</p>
        <ul>
          <li>MySQL 8 is supported only on Varbase 8.6.x or higher</li>
          <li>Required MySQL 5.5.3/MariaDB 5.5.20/Percona Server 5.5.8 or higher with
            InnoDB</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>## Server-side Requirements for Production

To deploy and run Varbase your web server must meet certain minimum requirements. We recommend sizing your application and considering your database size, files data, and expected traffic.

Your servers' requirements will greatly be impacted by the usage of your application. For example, if you have more logged-in users that anonymous users, you will need to consider higher requirements to serve non-cached requests.

If you need help sizing your server, please contact us at [https://www.vardot.com/contact-us](https://www.vardot.com/contact-us) for consultation.

<table>
  <thead>
    <tr>
      <th style="text-align:left"><b>Component</b>
      </th>
      <th style="text-align:left"><b>Description</b>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">PHP</td>
      <td style="text-align:left">
        <p>PHP 7 or higher. PHP 7.2 is recommended.</p>
        <p>PHP extensions: mysqli <em>(for MySQL)</em>, pgsql <em>(for PostgreSQL)</em>,
          xml, gd, openssl, json, curl, mbstring, date, dom, filter, hash, pcre,
          pdo, session, SimpleXML, SPL, tokenizer, mcrypt</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Applications</td>
      <td style="text-align:left">
        <p>Composer</p>
        <p>Drush 9 or higher</p>
        <p>Git</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Web Server</td>
      <td style="text-align:left">Varbase works on any web server with PHP version of 5.6 or higher.<code>mod_rewrite</code> is
        required if you use Apache.
        <br /><code>ngx_http_rewrite_module</code> if you use Nginx.</td>
    </tr>
    <tr>
      <td style="text-align:left">Database Engine</td>
      <td style="text-align:left">
        <p>Varbase works on any multiple database engines. MySQL, MariaDB or Percona
          Server (Recommended)</p>
        <ul>
          <li>MySQL 8 is supported only on Varbase 8.6.x or higher</li>
          <li>Required MySQL 5.5.3/MariaDB 5.5.20/Percona Server 5.5.8 or higher with
            InnoDB</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>### Additional Recommended Components for Production Use

<table>
  <thead>
    <tr>
      <th style="text-align:left"><b>Component</b>
      </th>
      <th style="text-align:left"><b>Description</b>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">Memcache</td>
      <td style="text-align:left">
        <p>Memcached server daemon</p>
        <p>PECL Memcache or PHP Memcached libraries</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Varnish</td>
      <td style="text-align:left">Varnish cache, an advanced and very fast reverse-proxy system.</td>
    </tr>
  </tbody>
</table>### Solr Search Requirements _\(If You Use Search API Solr\)_

| **Component** | **Description** |
| :--- | :--- |
| Solr Search | The minimum support Solr version is Solr 6.4 and Solr 7 is supported. |

