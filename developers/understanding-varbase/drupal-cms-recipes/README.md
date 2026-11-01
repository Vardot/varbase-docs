# Drupal CMS Recipes

## Overview

Varbase 11.0.x reuses some **Drupal CMS 2** recipes and layers its own recipes on top. **Varbase Starter** applies anti-spam, authentication, forms, SEO basic, SEO tools, accessibility tools and search. **Varbase AI Base** applies **Drupal CMS AI**.

Drupal CMS 2.2 reorganized its recipes: the core features moved into one recipe, `drupal_cms_site_template_base`, and eight separate recipes were marked unsupported on Drupal.org. The **Varbase 11.0.x** column shows how each one is used today. See [Drupal CMS and Varbase](../../drupal-cms-and-varbase.md).

## Available Recipes

| Recipe | Description | Varbase 11.0.x |
| --- | --- | --- |
| [Drupal CMS Admin UI](drupal-cms-admin-ui.md) | Sets up the administrative theme, navigation, and dashboard tools. | Not used. Unsupported upstream. |
| [Drupal CMS Anti-Spam](drupal-cms-anti-spam.md) | Anti-spam and anti-abuse functionality using CAPTCHA and honeypot. | Varbase Starter. Unsupported upstream. |
| [Drupal CMS Authentication](drupal-cms-authentication.md) | Authentication features including login with email or username. | Varbase Starter. Unsupported upstream. |
| [Drupal CMS Content Type Base](drupal-cms-content-type-base.md) | Basic tools for creating and managing content types with workflows. | Not used. Unsupported upstream. |
| [Drupal CMS Forms](drupal-cms-forms.md) | Simple contact form and form building tools using Webform. | Varbase Starter |
| [Drupal CMS Media](drupal-cms-media.md) | Basic media types including responsive images, focal point cropping, SVG, and video. | Not used. Unsupported upstream. |
| [Drupal CMS Privacy Basic](drupal-cms-privacy-basic.md) | Basic privacy features with consent management and remote content blocking. | Not used. Unsupported upstream. |
| [Drupal CMS Search](drupal-cms-search.md) | Search functionality using Search API with database backend. | Varbase Starter, Varbase Search Base |
| [Drupal CMS SEO Basic](drupal-cms-seo-basic.md) | Basic SEO best practices including path aliases and redirects. | Varbase Starter. Unsupported upstream. |
| [Drupal CMS SEO Tools](drupal-cms-seo-tools.md) | Advanced SEO with meta tags, XML sitemap, robots.txt, and Yoast integration. | Varbase Starter. Unsupported upstream. |
| [Drupal CMS Accessibility Tools](drupal-cms-accessibility-tools.md) | Automated accessibility checks using Editoria11y. | Varbase Starter |
| [Drupal CMS Google Analytics](drupal-cms-google-analytics.md) | Google Analytics and Google Tag Manager tracking integration. | Downloaded, applied on demand |
| [Drupal CMS AI](drupal-cms-ai.md) | AI services integration for alt text generation and site-building chatbot. | Varbase AI Base, Varbase AI Figma Base |

## Relationship to Varbase

Varbase depends on the Drupal CMS recipes it lists and layers its own configuration, permissions and features on top. Where Varbase has its own recipe for the same job, such as media, admin UI or privacy, it uses that instead.
