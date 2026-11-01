# Theme Development with Varbase

Varbase 11.0.x provides a modern theming system built on established front-end technologies and Drupal's component-based architecture.

## Front-End Theme: Vartheme BS5

**Vartheme BS5** is the default front-end theme for Varbase. It is a Bootstrap 5 based theme that provides responsive design, SCSS compilation, and a component-based architecture using Drupal's Single Directory Components (SDC) system. Vartheme BS5 is installed by the Varbase Starter recipe.

## [Design System Base Install](https://storybook.demo.varbase.vardot.com/)

Uses **Storybook 10** with the Vartheme BS5 starter kit. The Varbase project requires `storybook: ^10` in its `package.json` ([#3583717](https://www.drupal.org/i/3583717)). See [Integration of Varbase With Storybook](integration-of-varbase-with-storybook.md).

## Sections

### [Understanding Vartheme BS5](understanding-vartheme-bs5.md)

Learn about the architecture of Vartheme BS5, including its Bootstrap 5 foundation, SCSS structure, Single Directory Components, and CVA (Class Variance Authority) integration.

### [Creating Your Own Theme](creating-your-own-theme.md)

Step-by-step guide to creating a custom sub-theme that extends Vartheme BS5, including setting up SCSS compilation and customizing Bootstrap variables.

### [Drupal Canvas](drupal-canvas/README.md)

Build and manage a Vartheme BS5 site visually with **Drupal Canvas**, with no code:

* [**Introduction to Drupal Canvas in Varbase**](drupal-canvas/introduction-to-drupal-canvas-in-varbase.md): what Canvas is and how the editor works.
* [**Component Reference: Vartheme BS5 in Drupal Canvas**](drupal-canvas/vartheme-bs5-components-in-drupal-canvas.md): how a theme component reaches Canvas, and the 46 components with their IDs and slots.
* [**Editing the Header and Footer With Drupal Canvas**](drupal-canvas/editing-the-header-and-footer-with-drupal-canvas.md): the page template and the Administer page template permission.
* [**Managing Multiple Accordions With Drupal Canvas**](drupal-canvas/managing-multiple-accordions-with-drupal-canvas.md): the Accordion components, the Layers panel, and holding any component inside an accordion.
* [**Hero Slider Container and Hero Slide With Drupal Canvas**](drupal-canvas/hero-slider-container-and-hero-slide-with-drupal-canvas.md): a hero carousel, its container settings and one example for each media position.
* [**Building Common Page Types With Drupal Canvas**](drupal-canvas/building-common-page-types-with-drupal-canvas.md): services, products and event pages.
* [**Building Pages With the Drupal Canvas AI Agent**](drupal-canvas/building-pages-with-the-drupal-canvas-ai-agent.md): drafting a page from a prompt.
* [**Default Canvas Patterns**](drupal-canvas/default-canvas-patterns.md): the ready sections shipped with the site template.

### [Troubleshooting Theme Switch Issues](troubleshooting-theme-switch-issues.md)

What to do when Canvas pages still point at the old theme's components after switching themes.

### [Integration of Varbase With Storybook](integration-of-varbase-with-storybook.md)

The `ddev storybook` command, generating stories, and running Storybook on DDEV and Upsun.

### [Add Preloaded Fonts in Vartheme](add-preloaded-fonts-in-vartheme.md)

Preload web fonts in a theme built from Vartheme BS5.

### [Manually Install Needed Theming Tools](manually-install-needed-theming-tools.md)

Install Node.js, npm and Yarn by hand when you do not use the DDEV commands.
