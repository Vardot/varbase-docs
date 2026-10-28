# Glossary

This glossary defines key terms and concepts used throughout the Varbase documentation and the Drupal content management system.

## A

### AI Review
An AI check of a content item against your editorial rules, run from the item's **AI Review** tab.

### Alt Text (Alternative Text)
A text description of an image used by screen readers for accessibility and by search engines for indexing. Required for all editorial images.

### Alias
See **URL Alias**.

### Archived
A content moderation state in which content is removed from public view but retained in the system for reference or future reuse.

## B

### Block
A reusable piece of content or functionality, such as a menu, a form or a list. In Drupal Canvas, blocks are added as components.

### Bulk Operations
Actions performed on several content items at once from a list, such as deleting them or updating their URL aliases.

## C

### CKEditor (CKEditor 5)
The rich-text editor (WYSIWYG) used in Varbase for formatting content. CKEditor 5 provides tools for text formatting, linking, media embedding, tables, and source editing.

### Coffee
A Drupal module that provides a quick-search overlay for admin navigation. Activated by pressing Alt+D.

### Component
A ready-made piece of a Drupal Canvas page, such as a heading, an image, a card or a slider.

### Content Admin
A Varbase user role with broader content management authority, including the ability to publish, archive, and manage content structure.

### Content Editor
A Varbase user role for editorial staff who create and manage content, upload media, and build Drupal Canvas pages for others to publish.

### Content Lock
A temporary lock on a content item while someone edits it, so two people do not overwrite each other's changes.

### Content Moderation
A Drupal core feature that provides a publishing workflow with defined states (Draft, Published, Archived) and controlled transitions between them.


### Content Template
The Drupal Canvas layout used to show every item of a content type, such as every blog post.

### Content Type
A template that defines the structure of a kind of content, including its fields, display settings, and form configuration. Examples: Page, Article, Landing Page.

### Cron
A scheduled task system that runs periodic maintenance operations on the site, such as checking for updates, indexing search content, and processing queues.

## D

### Dashboard
The first page you see after logging in, with your drafts, recent content and shortcuts.

### Draft
A content moderation state in which content is saved but not visible to anonymous site visitors. Used for content that is being created, reviewed, or revised.

### Drupal Canvas
The visual page builder in Varbase 11. You build pages from components and patterns and see them as visitors will.

### Drush
A command-line tool for managing Drupal sites. Used by developers and administrators for tasks such as clearing cache, running updates, and managing configuration.

### DropzoneJS
A JavaScript library integrated into Varbase for drag-and-drop file uploading.

## E

### ECA (Event-Condition-Action)
A Drupal module that enables building automated workflows based on site events. Allows defining rules such as "When event X happens, if condition Y is met, perform action Z."


### Editoria11y
The accessibility checker that marks problems on pages for logged-in editors.

### EntityQueue
A module that provides manually ordered lists of content items. Used for curated content sections where editorial control over order is needed.

## F

### Focal Point
A feature that allows setting a point of interest on an image. When the image is cropped for different display sizes, the focal point area remains visible.

## G

### Gin
The admin theme used by Varbase 11.0.x. Provides a modern, clean, and accessible administration interface with support for light and dark modes.

## J

### JSON:API
A Drupal core module that provides a standards-compliant API for accessing and manipulating content entities. Follows the JSON:API specification.

## K

### Klaro
The cookie consent manager that asks visitors before loading services such as YouTube videos.

## L

### Layout Builder
An older Drupal page layout tool. Varbase 11 builds pages with **Drupal Canvas** instead.

### Linkit
A Drupal module that provides an autocomplete-based link insertion tool for the rich-text editor. Allows finding and linking to internal content by title.

## M

### Media Library
The central interface for browsing, managing, and selecting media assets (images, videos, documents, audio) on a Drupal site.

### Meta Tags
HTML elements that provide metadata about a page to search engines and social media platforms, including title, description, and Open Graph information.

### Module
A package of code that extends Drupal's functionality. Modules can be part of Drupal core (core modules) or contributed by the community (contributed modules).

## N

### Navigation Module
The Drupal core module used by Varbase 11.0.x for the primary admin sidebar navigation, replacing the traditional admin toolbar.

### Node
The internal term for a content item in Drupal. Each piece of content (page, article, etc.) is stored as a node.

## O

### oEmbed
A protocol that allows embedding content from external providers (e.g., YouTube, Vimeo) by providing a URL. Drupal core uses oEmbed for remote video embedding.

### OpenAPI
A specification for describing RESTful APIs. Provides interactive documentation (via Swagger UI) for exploring and testing API endpoints.

## P

### Page Template
The Drupal Canvas layout around every page, holding the header and footer.

### Pathauto
A Drupal module that automatically generates URL aliases for content based on configurable patterns.


### Pattern
A ready-made page section in Drupal Canvas, such as a hero slider or a set of feature cards.

### Published
A content moderation state in which content is live and visible to all site visitors.

## R

### Recipe
A Drupal concept for packaging configuration, modules, and default content into a reusable set that can be applied to a site. Varbase uses recipes to provide optional feature bundles (e.g., `varbase_i18n_base` for multilingual support).

### Responsive Preview
An optional module, not included in Varbase 11, that previews site pages at different screen sizes. Drupal Canvas has its own viewport selector for the same purpose.

### Revision
A saved version of a content item. Drupal creates a new revision each time content is saved, allowing editors to review change history and revert to previous versions.

## S

### Scheduler
A module that allows scheduling content to be automatically published or unpublished at a specified date and time.

### Schema.org
A structured data vocabulary used to provide search engines with detailed information about web content. Enables rich search results.

### SEO (Search Engine Optimization)
The practice of optimizing website content and configuration to improve visibility and ranking in search engine results.

### Simple Sitemap
A Drupal module that generates XML sitemaps to help search engines discover and index site content.

### Super Admin
The Varbase user role with every permission. Keep it for a few trusted technical people.

## T

### Taxonomy
A classification system in Drupal that uses vocabularies and terms to categorize content. Examples: Tags, Categories, Departments.

### Theme
A package of files that controls the visual presentation (design, layout, colors, typography) of a Drupal site. Varbase uses the Gin theme for administration and a separate theme for the front end.

### Trash
A module that provides soft-delete functionality. Deleted content is moved to the trash where it can be reviewed, restored, or permanently deleted.

## V

### Varbase
An open-source Drupal distribution developed by Vardot that provides a comprehensive set of features and configurations for building enterprise websites.

### View
A Drupal feature that creates dynamic listings and displays of content based on configurable criteria (filters, sorts, relationships). Used for content listings, feeds, blocks, and pages.

### VBO (Views Bulk Operations)
A module that adds bulk operation capabilities to views, allowing editors to perform actions on multiple items at once.

## W

### Webform
A Drupal module for building and managing web forms. Supports complex form structures, conditional logic, email handlers, and submission management.

### WYSIWYG (What You See Is What You Get)
An editing approach where content in the editor appears similar to the final published output. CKEditor 5 is the WYSIWYG editor used in Varbase.

## X

### XML Sitemap
A structured XML file that lists the important pages on a site, helping search engines discover and crawl content efficiently.

## Y

### Yoast SEO
The SEO analysis on blog posts that checks the text against a focus keyword and previews the search result.
