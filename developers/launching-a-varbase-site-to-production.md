# Launching a Varbase Site to Production

It is important to follow with the pre-lunch or pre-deployment checklist on the event of deployment for a project to the live production site.

## Checklist to Check Before Going Live

### Varbase Development Module

Varbase Development enables number of needed development tools, But they should not be enabled on production sites.

{% content-ref url="development-components/varbase-development.md" %}
[varbase-development.md](development-components/varbase-development.md)
{% endcontent-ref %}

* [ ] **Varbase Development**&#x20;
* [ ] Reroute Email
* [ ] Migrate Drupal UI
* [ ] Database Log
* [ ] Views UI
* [ ] Configuration Update UI
* [ ] Web Profiler
* [ ] Display Suite Devel
* [ ] Webform Devel
* [ ] Devel Generate
* [ ] Devel
* [ ] Tour UI
* [ ] Blazy Ui
* [ ] Slick UI

```
drush pm:uninstall varbase_development
drush pm:uninstall reroute_email
drush pm:uninstall migrate_drupal_ui
drush pm:uninstall dblog
drush pm:uninstall views_ui
drush pm:uninstall config_update_ui
drush pm:uninstall webprofiler
drush pm:uninstall ds_devel
drush pm:uninstall webform_devel
drush pm:uninstall devel_generate
drush pm:uninstall devel
drush pm:uninstall tour_ui
drush pm:uninstall blazy_ui
drush pm:uninstall slick_ui
```

### **Varbase Style Guide Module**

Varbase Style Guide module enables a styling and theming tools. But they should not be enabled on production sites.

{% content-ref url="understanding-varbase/development-components/varbase-styleguide.md" %}
[varbase-styleguide.md](understanding-varbase/development-components/varbase-styleguide.md)
{% endcontent-ref %}

* [ ] **Varbase Style Guide**
* [ ] Style Guide

```
drush pm:uninstall varbase_styleguide
drush pm:uninstall styleguide
```

