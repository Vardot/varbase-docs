# Accordions and Tabs

Accordions and tabs keep a page short by hiding detail until a visitor asks for it. Use them for questions and answers, agendas and specifications, not for the main message of the page.

## Accordion Container and Accordion

The **Accordion container** holds **Accordion** items. Each item has a heading that opens and closes its content.

- **Key settings (container)**: **Flush style** (no outer border), **Keep multiple items open**, **Header color override**, and an optional **Accordion ID**.
- **Key settings (item)**: **Heading**, **Heading level**, **Expanded by default**, **Keep this item independent**, **Header color override**, and optional IDs for links.
- **Slots**: the container's **Accordion content** holds the items; each item's **Accordion content** holds anything: text, a list of posts, a block or a webform.
- **Tip**: set **Heading level** to fit the page outline, usually one level below the section heading. The **FAQ Accordion** pattern builds a ready set of questions.

For several accordions on one page, see [Managing Multiple Accordions With Drupal Canvas](../../../developers/theme-development-with-varbase/drupal-canvas/managing-multiple-accordions-with-drupal-canvas.md).

## Tabs

Shows one panel at a time, switched by tab labels.

- **Key setting**: **Shape** (tabs or pills).
- **Tip**: keep tab labels short, and do not hide information every visitor needs inside a later tab.
