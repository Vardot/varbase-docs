# Development Components

## Varbase Development Module

Install the development tools if you're a developer and you're going to use Varbase to build a new project. This will install several modules that help you build your site, such as [**Devel**](https://www.drupal.org/project/devel), [**Database Logging**](https://www.drupal.org/docs/8/core/modules/dblog/overview), and UI modules such as **View UI**, and Configuration Update Reports.\


{% hint style="danger" %}
_Make sure to uninstall this module and its enabled modules when you go in production mode_.
{% endhint %}

{% content-ref url="varbase-development.md" %}
[varbase-development.md](varbase-development.md)
{% endcontent-ref %}

## Varbase Style Guide Module

Install Varbase custom styling guide if you want to have a full look for Varbase components, Bootstrap elements, and view mode style for content types. This will install several modules that help you on themeing and styling your site, such as [**Style Guide**](https://www.drupal.org/project/styleguide).

{% hint style="danger" %}
_Make sure to uninstall this module and its enabled modules when you go in production mode_.
{% endhint %}

{% content-ref url="../understanding-varbase/development-components/varbase-styleguide.md" %}
[varbase-styleguide.md](../understanding-varbase/development-components/varbase-styleguide.md)
{% endcontent-ref %}

## Reroute Email Module

Intercepts all outgoing emails from a Drupal site and reroutes them to a predefined configurable email address.

**Example use for rerouting emails :**

If a live production site was copied to a testing server for the purpose of development. The copied site should not send any emails to real users of the original production site.&#x20;

{% hint style="danger" %}
_Make sure to uninstall this module when you go in production mode_.
{% endhint %}

{% content-ref url="reroute-email.md" %}
[reroute-email.md](reroute-email.md)
{% endcontent-ref %}



##

