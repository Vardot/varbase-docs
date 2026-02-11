# Defining Active Menu Trail Using Menu Position

The **Menu Position** module allows you to define rules that automatically set the active menu trail based on conditions such as content type, taxonomy term, language, or other criteria. This ensures that the correct menu item is highlighted in the navigation when a visitor views content that does not have a direct menu link.

## Why Use Menu Position?

On most websites, not every piece of content has a dedicated menu link. For example, individual blog posts typically do not appear in the main menu, but when a visitor reads a blog post, the "Blog" menu item should still appear as active. Menu Position solves this by allowing you to create rules that match content to specific menu items.

## Accessing Menu Position

Navigate to **Structure > Menu Position Rules** in the Drupal admin interface, or go directly to:

```
/admin/structure/menu-position
```

## Creating a Menu Position Rule

1. Navigate to **Structure > Menu Position Rules**.
2. Click **Add menu position rule**.
3. Enter a descriptive **label** for the rule (for example, "Blog posts under Blog menu").
4. Select the **menu** that contains the target menu item (for example, "Main navigation").
5. Select the specific **parent menu item** that should be marked as active when the rule matches.
6. Configure the **conditions** that determine when the rule applies.

## Available Conditions

Menu Position supports several condition types:

### Content Type

Match content based on its content type. For example, you can create a rule that activates a "News" menu item whenever a visitor views any node of the "Article" content type.

- Check the content types that should trigger this rule.

### Taxonomy Term

Match content based on taxonomy term references. For example, you can activate a specific menu item when viewing content tagged with a particular term or vocabulary.

- Select the vocabulary and optionally specify specific terms.

### Language

Match content based on the language of the node being viewed. This is useful for multilingual sites where different menu items correspond to different languages.

## Rule Ordering

When multiple menu position rules could match the same content, the rules are evaluated in the order they appear on the Menu Position Rules administration page. The first matching rule wins. You can reorder rules by dragging them into the desired order.

## Example: Blog Posts

To ensure the "Blog" menu item is active when viewing any blog post:

1. Navigate to **Structure > Menu Position Rules**.
2. Click **Add menu position rule**.
3. Set the label to "Blog posts".
4. Select "Main navigation" as the menu.
5. Choose the "Blog" menu item as the parent.
6. Under conditions, select **Content Type** and check "Blog post".
7. Save the rule.

Now, whenever a visitor views a blog post, the "Blog" item in the main navigation will be highlighted as the active trail.
