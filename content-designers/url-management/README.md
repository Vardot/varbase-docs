# URL Management

URL management in Varbase covers two key aspects: **URL aliases** (human-readable paths for content) and **URL redirects** (forwarding old or changed URLs to their correct destinations). Proper URL management improves user experience, SEO, and site maintainability.

## Overview

### URL Aliases

URL aliases allow you to create human-readable, meaningful URLs for your content pages. Instead of the default system path (e.g., `/node/42`), you can have a clean URL like `/about-us` or `/blog/my-first-post`.

Varbase uses the **Pathauto** module to generate URL aliases automatically based on configurable patterns, and also supports manually set aliases for individual content items.

See [URL Aliases](url-aliases.md) for details.

### URL Redirects

URL redirects ensure that visitors and search engines are forwarded from old or obsolete URLs to the correct current pages. This is essential when content is moved, renamed, or restructured.

Varbase includes the **Redirect** module for managing URL redirects, along with 404 error monitoring to identify broken links.

See [URL Redirects](url-redirects.md) for details.

## Why URL Management Matters

- **User experience** -- Clean, descriptive URLs help visitors understand where they are on the site and what to expect from a page.
- **Search engine optimization** -- Search engines favor descriptive URLs and penalize sites with broken links (404 errors). Proper aliases and redirects improve search rankings.
- **Link integrity** -- When content URLs change, redirects preserve the value of existing links from external sites, social media, and bookmarks.

## Accessing URL Management Tools

- **URL aliases** -- Managed per content item (in the URL alias field on the content form) or globally via **Configuration > URL aliases** (`/admin/config/search/path`).
- **URL redirects** -- Managed at **Configuration > URL redirects** (`/admin/config/search/redirect`).
