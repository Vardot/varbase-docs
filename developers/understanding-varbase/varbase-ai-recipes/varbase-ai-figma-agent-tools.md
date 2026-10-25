# Varbase AI Figma Agent Tools

**Varbase AI Figma** ships 29 **AI Agent** tools. The **Drupal Canvas AI** assistant calls them to turn a Figma design into a Canvas page. They are grouped here in the order the [**Varbase AI Figma Base**](varbase-ai-figma-base.md) recipe hands them to the **Drupal Canvas AI Orchestrator**: understand the design, understand the site and decide, build, connect, then check and improve.

Every tool ID starts with `varbase_ai_figma:`. A user needs **any one** of the listed permissions, not all of them. Unless a row says otherwise, a tool needs `administer ai agents` or `use Drupal Canvas AI`.

{% hint style="info" %}
**Figma: List Design Pages** (`ai_figma:list_design_pages`) comes from the **AI Figma** module, not from **Varbase AI Figma**. It lists the top-level frames of a Figma file, so the agent can plan one Canvas page per frame.
{% endhint %}

## 1. Understand the Design

| Tool | ID | What It Does |
|---|---|---|
| **Read the design** | `get_design_context` | Reads the colors, typography, real text and layer outline of a Figma link or node, together with the theme's components, Webforms, Views listings and content types. Also accepts `use ai figma design context`. |

The inputs are optional. A pasted `figma_url` wins over `file_key` and `node_id`. With no file key, the default file key set in **AI Figma** is used. A node ID can use a colon or a dash (`1283:979` or `1283-979`).

## 2. Understand the Site, Then Decide

| Tool | ID | What It Does |
|---|---|---|
| **See what we already have** | `scan_inventory` | Lists the site's Canvas components with their real inputs, plus saved sections (patterns), blocks and Views. Call it before `resolve_design`. |
| **Decide what to reuse and what to build** | `resolve_design` | Scores each design region against the inventory and answers **reuse**, **adapt** or **build**, with a reason a site builder can read. |
| **Find the closest component** | `component_match` | The same scoring for one pasted Figma node, for questions such as "does this button already exist?". Also accepts `use ai figma design context`. |

## 3. Build What the Decision Chose

| Tool | ID | What It Does |
|---|---|---|
| **Build the page** | `create_canvas_page` | Builds one or more Canvas pages. Prefers a real View, Webform or block over hand-made markup, so listings and forms stay live. |
| **Change a page that already exists** | `page_edit` | Makes one targeted change, such as moving a section or swapping a block, without rebuilding the page. |
| **Fix the details of one thing on a page** | `update_component_inputs` | Changes the inputs of one component, such as one heading or one label. |
| **Put it in the header or footer** | `place_in_region` | Builds the site-wide header or footer once, so each page holds only its own content. |
| **Save a section so it can be reused** | `create_pattern` | Builds a reusable section (a pattern) straight from a Figma design. |
| **Save a section already on a page for reuse** | `save_as_pattern` | Saves a section that is already on a page as a pattern. |
| **Add a saved section to a page** | `insert_pattern` | Places a saved pattern on a page. |
| **Bring the images across** | `export_figma_images` | Exports the design's own images from Figma, so the page does not use placeholders. Also accepts `use ai figma design context`. |
| **Collect the design files** | `fetch_media_assets` | Collects the design's logos, icons and photos before the build. Also accepts `use ai figma design context`. |
| **Edit the theme files** | `theme_file` | Makes a small CSS, JavaScript or Bootstrap variable change in the default theme. It cannot change templates. Also accepts `administer themes`. |
| **Set the site logo** | `set_theme_logo` | Sets the site logo from the Figma design. Needs `administer themes` or `administer ai agents`. `use Drupal Canvas AI` alone is not enough. |
| **Suggest what to ask for next** | `prompt_template` | Saves a reusable checklist of instructions and applies it to any page. |
| **Suggest alternative wording to test** | `ab_variants` | Suggests alternative wording for a page's key text, for an A/B test. Also accepts `use ai figma design context`. |
| **Check many pages at once** | `batch_improve` | Checks many pages in one sweep. Follow up on a flagged page with `audit_page`. |

## 4. Connect It to the Rest of the Site

| Tool | ID | What It Does |
|---|---|---|
| **Connect the design to the real site** | `site_wiring` | Sets the new home page as the front page, gives each new page a clean URL alias, and adds it to the navigation when the design shows it there. Also accepts `administer site configuration`. |
| **Manage the menus** | `menu_link` | Adds, lists and removes links in the main, secondary and footer menus. Also accepts `administer menu`. |
| **Install a set of features** | `apply_recipe` | Applies a small recipe, for example to enable a module. Needs `administer site configuration` or `administer ai agents`. `use Drupal Canvas AI` is not enough, because a recipe can install modules and themes. |
| **Change a site setting** | `config` | Changes one site setting. Use `apply_recipe` for anything larger. Also accepts `administer site configuration`. |

## 5. Check and Improve

| Tool | ID | What It Does |
|---|---|---|
| **Look at the page in a real browser** | `preview_token_url` | Returns a short-lived preview link, so a browser tool with no login can open an unpublished page and take a screenshot. |
| **Check the page loads** | `check_page_render` | A quick check that the page renders. Run it before the browser preview. |
| **Check a page for problems** | `audit_page` | Reviews a page for accessibility, headings, contrast, SEO, spacing, images, links and missing sections, without an AI call. Fix what it finds with `page_edit`, `alt_text` and `meta_description`. Also accepts `use ai figma design context`. |
| **Improve the wording** | `improve_text` | Rewrites text on a page, for example to shorten a headline or clarify a paragraph. |
| **Describe the images for screen readers** | `alt_text` | Drafts alt text for images on a page. Review each suggestion before you keep it. |
| **Write the search-engine summary** | `meta_description` | Drafts the page's meta description. |
| **Translate the page** | `translate_page` | Translates a page. Duplicate the page first if the original language must stay. |

## Turning Tools On

The recipe turns on the tools the orchestrator needs. An administrator can switch on the others on the agent's edit form (`/admin/config/ai/tools-automation/agents`). See [Orchestrator Tools](varbase-ai-figma-base.md#orchestrator-tools) before changing the list.
