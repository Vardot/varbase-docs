# Extending Varbase

Varbase 11.0.x is designed to be extended and customized to meet the specific needs of your project. The recipe-based architecture makes it straightforward to add new functionality, override existing configurations, and build custom features on top of the Varbase foundation.

## Extension Approaches

There are several ways to extend a Varbase site:

### Custom Recipes

Create your own Drupal recipes that build on Varbase recipes to add project-specific functionality. Custom recipes are ideal for packaging reusable sets of modules, configuration, and permissions that your organization uses across multiple projects.

### Custom Modules

Develop custom Drupal modules to implement functionality that goes beyond what recipes and contributed modules provide. Custom modules can hook into Drupal's plugin system, define new entity types, and extend existing functionality.

### Configuration Overrides

Override Varbase's default configurations through `settings.php` or custom configuration management to adjust behaviors without modifying the original recipe configurations.

### Contributed Modules

Install additional contributed modules from Drupal.org to add features not included in the default Varbase recipes.

## Sections

### [Creating Your Own Recipe](creating-your-own-recipe.md)

Step-by-step guide to creating a custom Drupal recipe that builds on Varbase, including recipe structure, dependencies, config actions, and permissions.

### [Overriding Varbase](overriding-varbase.md)

How to override Varbase configurations and behaviors using settings.php overrides, custom modules, and hooks.
