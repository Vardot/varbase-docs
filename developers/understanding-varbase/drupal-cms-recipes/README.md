# Drupal CMS Recipes

## Overview

Varbase 11.0.x builds on top of **Drupal CMS 2.0** recipes. These recipes provide foundational features, such as administration UI, SEO, media handling, search, and accessibility, that Varbase extends with its own specialized recipes.

The **varbase\_starter** recipe includes these Drupal CMS recipes as dependencies, ensuring that every Varbase installation benefits from the robust baseline functionality provided by the Drupal CMS project.

## Available Recipes

| Recipe | Description |
| --- | --- |
| [Drupal CMS Admin UI](drupal-cms-admin-ui.md) | Sets up the administrative theme, navigation, and dashboard tools. |
| [Drupal CMS Anti-Spam](drupal-cms-anti-spam.md) | Anti-spam and anti-abuse functionality using CAPTCHA and honeypot. |
| [Drupal CMS Authentication](drupal-cms-authentication.md) | Authentication features including login with email or username. |
| [Drupal CMS Content Type Base](drupal-cms-content-type-base.md) | Basic tools for creating and managing content types with workflows. |
| [Drupal CMS Forms](drupal-cms-forms.md) | Simple contact form and form building tools using Webform. |
| [Drupal CMS Media](drupal-cms-media.md) | Basic media types including responsive images, focal point cropping, SVG, and video. |
| [Drupal CMS Privacy Basic](drupal-cms-privacy-basic.md) | Basic privacy features with consent management and remote content blocking. |
| [Drupal CMS Search](drupal-cms-search.md) | Search functionality using Search API with database backend. |
| [Drupal CMS SEO Basic](drupal-cms-seo-basic.md) | Basic SEO best practices including path aliases and redirects. |
| [Drupal CMS SEO Tools](drupal-cms-seo-tools.md) | Advanced SEO with meta tags, XML sitemap, robots.txt, and Yoast integration. |
| [Drupal CMS Accessibility Tools](drupal-cms-accessibility-tools.md) | Automated accessibility checks using Editoria11y. |
| [Drupal CMS Page](drupal-cms-page.md) | Simple page content type for basic site pages. |
| [Drupal CMS Google Analytics](drupal-cms-google-analytics.md) | Google Analytics and Google Tag Manager tracking integration. |
| [Drupal CMS AI](drupal-cms-ai.md) | AI services integration for alt text generation and site-building chatbot. |

## Relationship to Varbase

Varbase does not replace these Drupal CMS recipes. Instead, it depends on them and layers additional configuration, permissions, and features on top. This means Varbase sites benefit from upstream improvements to Drupal CMS recipes while maintaining Varbase-specific enhancements.
