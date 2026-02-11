# Layout Builder

Layout Builder is a powerful tool in Drupal that allows content editors and site administrators to customize the layout of individual content pages or content type templates directly from the browser. Varbase leverages Layout Builder to provide flexible, drag-and-drop page design capabilities.

## Overview

Layout Builder works by dividing a page into **sections**, which act as structural containers. Each section can have a defined column layout (one column, two columns, three columns, etc.). Within each section, you place **blocks** that hold the actual content -- text, media, views, custom blocks, and more.

## Key Concepts

### Sections

Sections are the top-level structural elements of a layout. Each section defines:

- The number of columns (1, 2, 3, or 4 columns).
- The width ratio between columns (e.g., 50/50, 33/67, 25/50/25).
- Optional styles such as background color, spacing, and container width.

See [Section](section/) for details.

### Blocks

Blocks are the content elements placed within sections. They can include:

- Custom content blocks (text, media, etc.).
- Existing site blocks (menus, search forms, etc.).
- Views blocks (dynamic content listings).
- Field blocks (display specific fields from the content item).

See [Block Management](block-layout/) for details.

## Using Layout Builder

### Accessing Layout Builder

To use Layout Builder on a content item:

1. Navigate to the content page you want to customize.
2. Click the **Layout** tab (visible if you have layout editing permissions).
3. The Layout Builder interface opens, showing the current layout with its sections and blocks.

### Editing the Layout

In the Layout Builder interface, you can:

- **Add sections** -- Click **Add section** between existing sections or at the end of the layout. Choose a column layout for the new section.
- **Add blocks** -- Click **Add block** within a section's column to add a new block. Browse or search for the block you want to add.
- **Move blocks** -- Drag and drop blocks to reorder them within a section or move them between sections. See [Reordering Blocks](reordering-blocks.md).
- **Configure blocks** -- Click on an existing block to edit its content or settings.
- **Remove blocks** -- Click the remove option on a block to remove it from the layout.
- **Remove sections** -- Click the remove option on a section to remove it and all its blocks.

### Saving the Layout

After making changes to the layout:

1. Review your changes in the Layout Builder interface.
2. Click **Save layout** to apply the changes.
3. The content page will update to reflect the new layout.

## Layout Builder Modes

Layout Builder can operate in two modes:

- **Default layout** -- A layout configured at the content type level that applies to all content of that type. Managed by administrators and developers.
- **Per-content override** -- A layout customized for a specific content item, overriding the default layout. Available to content editors with appropriate permissions.

## Tips

- Plan your layout before building it. Sketch out the section structure and block placement on paper or in a design tool.
- Use section styles to create visual variety without custom code. See [Section Styles](section/section-styles.md).
- Keep layouts consistent across similar pages to maintain a professional, cohesive site experience.
- Preview the layout on different screen sizes to ensure it is responsive. See [Responsive Preview](../site-configuration/user-interface/responsive-preview.md).
