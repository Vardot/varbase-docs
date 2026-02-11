# Overriding Varbase

There are situations where you need to change Varbase's default behavior or configuration without modifying the original recipes or contributed modules. Drupal provides several mechanisms for overriding configurations and behaviors, all of which work with Varbase.

## Configuration Overrides in settings.php

Drupal's configuration override system allows you to change any configuration value through `settings.php` without modifying the stored configuration. These overrides take precedence over the database configuration and are not exported with `drush config:export`.

### Basic Configuration Override

Add overrides to your `settings.php` or `settings.local.php` file:

```php
// Override the site name
$config['system.site']['name'] = 'My Custom Site';

// Override the site email
$config['system.site']['mail'] = 'admin@example.com';

// Override a specific module setting
$config['system.performance']['css']['preprocess'] = FALSE;
$config['system.performance']['js']['preprocess'] = FALSE;
```

### Environment-Specific Overrides

Use configuration overrides to set different values for different environments:

```php
// In settings.local.php for development
$config['system.performance']['cache']['page']['max_age'] = 0;
$config['system.logging']['error_level'] = 'verbose';
$config['smtp.settings']['smtp_host'] = 'mailhog';
```

```php
// In settings.php for production
$config['system.performance']['cache']['page']['max_age'] = 3600;
$config['system.logging']['error_level'] = 'hide';
```

### Disabling Modules via Configuration

You can override module-specific settings to effectively disable certain behaviors:

```php
// Disable Google Analytics tracking in development
$config['google_analytics.settings']['account'] = '';
```

## Custom Modules

For more complex overrides that cannot be achieved through configuration alone, create a custom module.

### Creating a Custom Module

Create a minimal module structure:

```
modules/custom/my_overrides/
  my_overrides.info.yml
  my_overrides.module
```

The `my_overrides.info.yml` file:

```yaml
name: 'My Overrides'
type: module
description: 'Project-specific overrides for Varbase.'
core_version_requirement: ^10.3 || ^11
package: Custom
dependencies:
  - drupal:node
```

### Using Hooks

Hooks allow you to alter Drupal's behavior at specific points in the request lifecycle.

#### Alter Forms

```php
/**
 * Implements hook_form_alter().
 */
function my_overrides_form_alter(&$form, \Drupal\Core\Form\FormStateInterface $form_state, $form_id) {
  // Modify the article node form
  if ($form_id === 'node_article_edit_form') {
    // Hide a field from certain users
    $current_user = \Drupal::currentUser();
    if (!$current_user->hasPermission('administer nodes')) {
      $form['field_internal_notes']['#access'] = FALSE;
    }
  }
}
```

#### Alter Views

```php
/**
 * Implements hook_views_pre_render().
 */
function my_overrides_views_pre_render(\Drupal\views\ViewExecutable $view) {
  if ($view->id() === 'content' && $view->current_display === 'page_1') {
    // Modify the view before rendering
  }
}
```

#### Alter Entity Access

```php
/**
 * Implements hook_entity_access().
 */
function my_overrides_entity_access(\Drupal\Core\Entity\EntityInterface $entity, $operation, \Drupal\Core\Session\AccountInterface $account) {
  // Add custom access logic
  return \Drupal\Core\Access\AccessResult::neutral();
}
```

### Using Event Subscribers

For Symfony-based event handling, create an event subscriber service:

`my_overrides.services.yml`:

```yaml
services:
  my_overrides.event_subscriber:
    class: Drupal\my_overrides\EventSubscriber\MyOverridesSubscriber
    tags:
      - { name: event_subscriber }
```

`src/EventSubscriber/MyOverridesSubscriber.php`:

```php
<?php

namespace Drupal\my_overrides\EventSubscriber;

use Symfony\Component\EventDispatcher\EventSubscriberInterface;
use Symfony\Component\HttpKernel\Event\RequestEvent;
use Symfony\Component\HttpKernel\KernelEvents;

class MyOverridesSubscriber implements EventSubscriberInterface {

  public static function getSubscribedEvents() {
    return [
      KernelEvents::REQUEST => ['onRequest', 100],
    ];
  }

  public function onRequest(RequestEvent $event) {
    // Custom request handling logic
  }

}
```

## Theme Overrides

Override Varbase theme templates and styles through your custom sub-theme. See [Creating Your Own Theme](../theme-development-with-varbase/creating-your-own-theme.md) for details.

### Twig Template Overrides

Copy templates from Varbase modules or the Vartheme BS5 theme into your sub-theme's `templates/` directory and modify them. Drupal automatically uses the most specific template available.

### Preprocess Functions

Add preprocess functions in your theme's `.theme` file:

```php
/**
 * Implements hook_preprocess_node().
 */
function my_custom_theme_preprocess_node(&$variables) {
  $node = $variables['node'];
  if ($node->getType() === 'article') {
    // Add custom template variables
    $variables['custom_class'] = 'article-featured';
  }
}
```

## Overriding ECA Workflows

ECA workflows provided by Varbase recipes can be modified through the ECA modeler interface at **Configuration > Workflow > ECA**. You can:

- Disable workflows you do not need.
- Modify existing workflows to change conditions or actions.
- Clone a workflow and customize the copy.

## Best Practices

1. **Use the lightest touch possible**: Start with configuration overrides in `settings.php`. Only create custom modules when configuration overrides are insufficient.
2. **Never modify contributed code**: Always use hooks, events, or configuration overrides instead of modifying Varbase recipes, contributed modules, or Drupal core directly.
3. **Document all overrides**: Keep clear records of what has been overridden and why, so future developers can understand the project-specific changes.
4. **Test overrides during updates**: After updating Varbase or its dependencies, verify that your overrides still work correctly with the new versions.
5. **Keep custom modules minimal**: Place only override-specific code in your custom modules. Avoid duplicating functionality that Varbase already provides.
