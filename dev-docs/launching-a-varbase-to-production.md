# Launching a Varbase to Production



## Checklist to Check Before Going Live

### 1. Uninstall Development Modules&#x20;

* [ ] **Varbase Development **
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

* [ ] **Varbase Style Guide**
* [ ] Style Guide

```
drush pm:uninstall varbase_styleguide
drush pm:uninstall styleguide
```

