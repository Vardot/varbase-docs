# What's New in Varbase 11

Varbase 11.0.x represents a **major architectural shift** for the Varbase distribution. This release moves away from the traditional modules-based architecture to a modern **recipes-based architecture**, aligning with the direction of the broader Drupal ecosystem.

## Recipes-Based Architecture

The most significant change in Varbase 11 is the adoption of **Drupal Recipes** as the primary building block for the distribution.

- **From profiles to recipes**: The `varbase_starter` recipe replaces the old Varbase installation profile. Instead of a monolithic profile that installs everything at once, Varbase now uses composable recipes that can be applied individually or as a group.
- **Module-to-recipe conversion**: Each former Varbase module has been converted into a corresponding Varbase recipe. This provides greater flexibility, easier maintenance, and better alignment with upstream Drupal standards.
- **Three-layer recipe stack**: Varbase 11 builds on three layers of recipes:
  1. **Drupal Core** recipes
  2. **Drupal CMS 2.0** recipes
  3. **Varbase-specific** recipes

## Built on Drupal 11

Varbase 11.0.x is built on **Drupal 11**, taking full advantage of the latest Drupal core features, performance improvements, and API enhancements.

## Drupal CMS 2.0 Alignment

Varbase 11 integrates with the **Drupal CMS 2.0 initiative**, incorporating its recipes for common website functionality:

- **Admin UI**: Improved administrative experience
- **Anti-spam**: CAPTCHA and spam prevention
- **Authentication**: User login and authentication handling
- **Forms**: Enhanced form building and management
- **Media**: Core media management capabilities
- **Privacy**: GDPR and privacy compliance tools
- **SEO**: Search engine optimization configuration
- **Accessibility**: WCAG compliance and accessibility tooling

## AI Integration Recipes

Varbase 11 introduces a suite of **AI integration recipes** that bring artificial intelligence capabilities into the CMS:

- **Varbase AI Base**: Foundation recipe that installs the core AI modules and bundles the AI feature recipes
- **Varbase AI Editor Assistant**: AI-powered assistance in the CKEditor 5 rich-text editor
- **Varbase AI Image Alt**: AI-generated alternative text for images
- **Varbase AI Taxonomy Tagging**: AI-powered taxonomy tagging for content
- **Varbase AI Context**: Starter brand, editorial, and safety context items for all AI agents
- **Varbase AI Safety**: Prompt safety and PII guardrails, AI logging, and AI observability
- **Varbase AI Figma Base** _(add-on)_: Builds Drupal Canvas pages from Figma designs with the Drupal Canvas AI assistant

## Easy Email Recipes

The old email configuration approach has been replaced with **Easy Email recipes**, providing a streamlined way to configure email delivery, templates, and transactional email handling.

## ECA (Event-Condition-Action) Integration

**ECA** is now deeply integrated into Varbase 11, providing a powerful no-code automation framework. ECA allows site builders to define automated workflows based on events, conditions, and actions without writing custom PHP code.

## Gin Admin Theme

Varbase 11 adopts the **Gin admin theme** as the default administration theme, delivering:

- A modern, clean administrative interface
- Improved **toolbar** for better navigation
- Enhanced **login screens** with a polished user experience
- **Gin Everywhere** support for a consistent admin look across all backend pages

## Trash Module for Soft Delete

The **Trash** module is now included, enabling **soft-delete** functionality for content. Instead of permanently removing content, items are moved to a trash bin where they can be restored or permanently deleted at a later time.

## Summary of Changes

| Area | Varbase 10.x and Earlier | Varbase 11.0.x |
|---|---|---|
| Architecture | Modules and installation profile | Recipes-based |
| Drupal version | Drupal 9 / 10 | Drupal 11 |
| Entry point | Varbase installation profile | `varbase_starter` recipe |
| Admin theme | Claro / Seven | Gin |
| Email | Custom email modules | Easy Email recipes |
| AI | Not included | AI recipes suite |
| Automation | Limited | ECA deeply integrated |
| Content deletion | Permanent | Soft-delete via Trash |
