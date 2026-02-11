# Taxonomies

Taxonomies provide a structured way to categorize and organize content on your Varbase site. They use vocabularies and terms to classify content, making it easier for visitors to find related information and for editors to maintain a well-organized site.

## What Are Taxonomies?

A **taxonomy** is a classification system made up of:

- **Vocabularies**: A vocabulary is a group of related terms. For example, "Tags," "Categories," or "Departments" are all vocabularies.
- **Terms**: A term is an individual item within a vocabulary. For example, "Technology," "Health," and "Education" might be terms within a "Categories" vocabulary.

Content is categorized by assigning taxonomy terms to content items through taxonomy reference fields.

## Common Uses

- **Tags**: Freeform keywords applied to content for flexible categorization.
- **Categories**: A predefined set of categories for organizing content into sections.
- **Content topics**: Subject areas for filtering and grouping related content.
- **Departments or teams**: Organizational units for associating content with specific groups.

## Accessing Taxonomy Management

1. Navigate to **Structure > Taxonomy** in the admin navigation sidebar, or go to `/admin/structure/taxonomy`.
2. You will see a list of all taxonomy vocabularies configured on your site.
3. Click **List terms** next to a vocabulary to view and manage its terms.

## Taxonomy Tasks

- [Add Terms](add-terms.md): Add new terms to a vocabulary.
- [Reorder and Edit Terms](reorder-and-edit-terms.md): Change the order of terms and edit existing ones.

## How Taxonomies Are Used in Content

When creating or editing content, you will encounter taxonomy reference fields where you can:

- Select from existing terms using a dropdown, checkboxes, or autocomplete field.
- Add new terms on the fly (if the field is configured to allow it).
- Assign multiple terms to a single content item.

The specific taxonomy fields available depend on the content type and your site's configuration.

## Taxonomy Pages

Each taxonomy term automatically has its own page that lists all content tagged with that term. These pages can be customized by your development team to control the layout and display of tagged content.
