# Accessibility Checks

Varbase checks your pages for common accessibility problems as you work, so everyone can use your site, including people who use screen readers or keyboards. The checker, **Editoria11y**, points to each problem on the page and explains how to fix it. This page shows how to use it.

## Where the Checker Appears

When you are logged in and view a page on the site, the checker scans it and shows its button in the corner of the page. If it finds a problem, the button shows the number of issues and markers appear next to each one.

<figure><img src="../.gitbook/assets/accessibility-checks-01-panel.png" alt="A published blog post viewed by a logged-in editor, with the accessibility checker button in the corner of the page"><figcaption><p>The Accessibility Checker on a Page</p></figcaption></figure>

Visitors never see the checker.

## Fixing a Problem

1. Click a marker on the page, or use the arrows in the panel to go from one issue to the next.
2. Read the explanation, for example that an image has no alternative text.
3. Edit the content and fix it, then view the page again: the issue disappears.

## Common Problems

| Problem | Fix |
| --- | --- |
| Image has no alternative text | Add alt text to the image in the **Media Library**. |
| Heading levels skipped | Use **Heading 2**, then **Heading 3**, without jumping levels. |
| Link text is not clear, such as "click here" | Write link text that says where the link goes. |
| Text formatted to look like a heading | Use a real heading from the **Heading** list. |
| Table without headers | Mark the first row or column as headers. |

## The Site-Wide Report

A **Super Admin** can see every issue found across the site at **Reports** \ **Content Accessibility** (`/admin/reports/editoria11y`), and the **Pages with accessibility alerts** panel on the dashboard. Ask them for the list when you plan an accessibility clean-up.

## Who Sees the Checker

The **Content editor**, **Content Admin**, **SEO Admin** and **Site Admin** roles. On a new site, only a **Super Admin** can mark an issue as checked or hide it.

## Tips

- Fix issues when you publish, not later: it takes a minute then and much longer in a clean-up.
- The checker finds common problems, not all of them. Also check that the page makes sense with images off and read aloud.
