# Understanding Vartheme BS5

**Vartheme BS5** is the default Bootstrap 5 based front-end theme for Varbase 11.0.x. It provides a responsive, accessible, and customizable foundation for building Drupal websites, leveraging modern front-end development practices and Drupal's component architecture.

## Bootstrap 5 Foundation

Vartheme BS5 is built on **Bootstrap 5**, one of the most widely used CSS frameworks. It provides:

- **Responsive grid system**: A 12-column grid with breakpoints for mobile, tablet, and desktop layouts.
- **Utility classes**: A comprehensive set of spacing, typography, color, and layout utilities.
- **Component library**: Pre-styled UI components including buttons, cards, modals, navbars, and forms.
- **JavaScript plugins**: Interactive components such as dropdowns, carousels, and tooltips.

## SCSS Architecture

Vartheme BS5 uses **SCSS** (Sassy CSS) for stylesheets, providing variables, mixins, nesting, and other features that make CSS more maintainable and scalable.

### File Structure

The theme's SCSS files are organized into a structured directory layout:

- **Variables**: Bootstrap variable overrides that control colors, fonts, spacing, and other design tokens.
- **Components**: SCSS partials for individual UI components.
- **Layout**: Styles for page layout regions and structural elements.
- **Base**: Base element styles, resets, and typography.

### Compilation

SCSS files are compiled into CSS using the build tools configured in the theme's `package.json`. The compiled CSS is output to the theme's CSS directory and loaded by Drupal.

## Single Directory Components (SDC)

Vartheme BS5 uses Drupal's **Single Directory Components** system for organizing reusable UI components. SDC bundles each component's template (Twig), styles (CSS/SCSS), JavaScript, and metadata into a single directory.

### Component Structure

Each SDC component follows this structure:

```
components/
  my-component/
    my-component.twig
    my-component.scss
    my-component.js (optional)
    my-component.component.yml
```

The `*.component.yml` file defines the component's metadata, including its name, description, props (input parameters), and slots (content areas).

### Using Components

Components can be used in Twig templates through the `include` or `embed` directives, or by referencing them in the component system. SDC components promote reusability, consistency, and maintainability across the theme.

## CVA (Class Variance Authority)

Vartheme BS5 integrates **CVA (Class Variance Authority)** for managing component variants. CVA provides a structured way to define CSS class combinations based on variant properties, making it easier to create consistent component variations.

### How CVA Works

CVA allows you to define a component's base classes and variant-specific classes in a structured format. When rendering a component, you specify which variants to apply, and CVA generates the appropriate CSS class string.

For example, a button component might have:

- **Base classes**: `btn`
- **Variant: size**: `sm` adds `btn-sm`, `lg` adds `btn-lg`
- **Variant: color**: `primary` adds `btn-primary`, `secondary` adds `btn-secondary`

This approach keeps class logic organized and prevents inconsistencies when applying component styles.

## Responsive Design

Vartheme BS5 provides responsive design out of the box through Bootstrap's breakpoint system:

| Breakpoint | Min Width | CSS Class Prefix |
| --- | --- | --- |
| Extra small | 0 | (default) |
| Small | 576px | `sm` |
| Medium | 768px | `md` |
| Large | 992px | `lg` |
| Extra large | 1200px | `xl` |
| Extra extra large | 1400px | `xxl` |

## Regions

Vartheme BS5 defines the following theme regions for placing blocks:

- **Header**: Site branding, navigation, and search.
- **Content**: Main page content area.
- **Sidebar**: Optional sidebar for supplementary content.
- **Footer**: Footer blocks including copyright, links, and contact information.
- Additional regions for banners, highlighted content, and other layout needs.

## Dependencies

Vartheme BS5 depends on:

- **Bootstrap 5**: CSS framework (loaded via the theme's library definitions).
- **CVA module**: Class Variance Authority integration for Drupal.
- **Drupal core**: Twig templating, asset libraries, and SDC support.
