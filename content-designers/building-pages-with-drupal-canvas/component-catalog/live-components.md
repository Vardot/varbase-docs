# Live Components

Live components show content from elsewhere on the site, and update themselves when that content changes. They are what make a Drupal Canvas page part of a living site. Their settings control what is shown, not the words themselves: posts are managed as content, forms in **Webform**, and links in the menu screens.

| Component | What it shows | Where its content is managed |
| --- | --- | --- |
| **Blog: Latest blog posts** | The newest posts, as cards | [Creating Content](../../content-management/) |
| **Blog: All blog posts** with **Exposed form: blog-all** | The full blog list and its filters | [Creating Content](../../content-management/) |
| **Blog: Related blog posts** | Posts that share tags with the current one | Tags on each post |
| **Search: Header search form**, **Search results**, **Search: Date filter block**, **Content Type** and **Tags** filters, and the **Exposed form** blocks | The search box, results and filters | [Varbase Search Base](../../../developers/understanding-varbase/varbase-recipes/varbase-search-base.md) |
| **Main navigation**, **Footer**, **Social media menu** | A menu's links | [Menu Management](../../url-management/menu-management/) |
| **Breadcrumbs** | The path to the current page | Automatic |
| **Site branding** | The site logo and name | Site settings |
| **Language switcher** | Links to the page in other languages | [Language Switcher](../../content-translation/language-switcher.md) |
| **Webform** | A form, such as the contact form | [Webforms](../../search-forms-and-email/webforms/) |
| **AI Answers: Question**, **Answer** and **Sources** | A question box with answers cited from the site | [Varbase AI Answers Base](../../../developers/understanding-varbase/varbase-ai-recipes/varbase-ai-answers-base.md) |

Your site may list more, such as **Dashboard welcome** or **User profile details**; those are for admin pages and profiles.

## Tips

- Canvas arranges, content fills: publishing a new post updates every list that shows it, so nobody edits listing pages when content arrives.
- A menu component shows a menu; it does not hold the links. Adding a page to the main menu is a menu task, not a Canvas task.
- Which search filters exist is a configuration decision made with the content model. Editors can reorder them on the page.
