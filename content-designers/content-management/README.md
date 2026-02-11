# Content Management

Content management is the core activity for editors and administrators on a Varbase site. This section covers everything you need to know about creating, editing, publishing, and deleting content.

## Overview

Varbase provides a robust content management system built on Drupal's content architecture. Key features include:

- **Content Types**: Pre-defined templates for different kinds of content (e.g., pages, articles, landing pages). Each content type has its own set of fields and configuration.
- **Content Listing**: A central listing of all content items, accessible at **Content** in the admin navigation or at `/admin/content`.
- **Content Moderation**: A publishing workflow with states (Draft, Published, Archived) that controls content visibility.
- **Revision Tracking**: Every edit creates a new revision, allowing you to review the history of changes and revert to previous versions.
- **Bulk Operations**: Perform actions on multiple content items at once using Views Bulk Operations.

## Content Types

Varbase comes with several pre-configured content types. The specific content types available on your site depend on which Varbase recipes have been applied. Common content types include:

- **Page**: A basic content page for static information.
- **Article / Blog Post**: Time-based content with author attribution and categorization.
- **Landing Page**: A flexible page built with Layout Builder for marketing and promotional content.

Your site may include additional custom content types configured by your development team.

## Content Listing

The content listing page (`/admin/content`) provides a filterable, sortable table of all content on your site. From this page, you can:

- Filter content by title, content type, published status, or language.
- Sort content by title, content type, author, or last updated date.
- Perform bulk operations on selected items.
- Click on a content title to view it, or use the operations dropdown to edit, delete, or translate it.

## Key Tasks

- [Create Content](create-content/): Add new content to your site.
- [Modify Content](modify-content.md): Edit existing content items.
- [Delete Content](delete-content.md): Remove content (with soft-delete via Trash).
- [Preview Content](preview-content.md): Preview content before publishing.
- [Bulk Edit Content](bulk-edit-content.md): Perform actions on multiple items.
- [Publish Content](publish-content.md): Manage publishing states and scheduling.
