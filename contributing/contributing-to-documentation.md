# Contributing to Documentation

Clear, accurate documentation is essential for the Varbase community. Whether you are fixing a typo, improving an explanation, or writing new content, your documentation contributions help all Varbase users.

## How to Contribute

### Submitting Pull Requests

The Varbase documentation is maintained in a Git repository. To contribute:

1. **Fork the documentation repository** on GitHub.
2. **Clone your fork** to your local machine.
3. **Create a new branch** for your changes (e.g., `fix/typo-content-management` or `add/webform-advanced-guide`).
4. **Make your changes** to the relevant Markdown files.
5. **Commit your changes** with a clear, descriptive commit message.
6. **Push your branch** to your fork on GitHub.
7. **Submit a pull request** to the main documentation repository.
8. Provide a description of your changes in the pull request, including:
   - What was changed and why.
   - Any relevant context or issue references.

### Reporting Issues

If you find an error or gap in the documentation but are unable to fix it yourself:

1. Open an issue in the documentation repository on GitHub.
2. Describe the problem clearly, including:
   - The page or section affected.
   - What is incorrect or missing.
   - What the correct information should be (if known).

## Documentation Format

The Varbase documentation is written in **GitBook-compatible Markdown**. Follow these formatting guidelines:

### File Structure

- Each section has a `README.md` file that serves as the section's landing page.
- Sub-topics are individual Markdown files within the section's directory.
- File names use lowercase letters and hyphens (e.g., `create-content.md`, `url-aliases.md`).

### Markdown Conventions

- **Headings**: Use `#` for the page title (H1), `##` for main sections (H2), `###` for subsections (H3), and so on. Each page should have exactly one H1 heading.
- **Bold text**: Use `**bold**` for UI element names, field labels, and emphasis.
- **Inline code**: Use backticks for paths, URLs, commands, and code (e.g., `/admin/content`, `drush cr`).
- **Code blocks**: Use triple backticks for multi-line code or command examples.
- **Lists**: Use `-` for unordered lists and `1.` for ordered lists.
- **Links**: Use relative links for internal documentation pages (e.g., `[Content Management](../content-management/)`).
- **Tables**: Use Markdown table syntax for tabular data.

### Content Guidelines

- Write in a clear, professional tone.
- Use the second person ("you") when addressing the reader.
- Be concise. Avoid unnecessary filler words.
- Provide step-by-step instructions for procedural topics.
- Use consistent terminology throughout the documentation.
- Do not include screenshots or images unless specifically coordinated with the documentation maintainers.

### Page Structure

Each documentation page should follow this general structure:

1. **Title** (H1): The topic name.
2. **Introduction**: A brief paragraph explaining what the page covers and why it matters.
3. **Main content**: Step-by-step instructions, explanations, or reference information, organized with H2 and H3 headings.
4. **Tips**: Optional section with helpful best practices or additional notes.

## Review Process

After submitting a pull request:

1. A documentation maintainer will review your changes.
2. You may receive feedback or requests for revisions.
3. Address any feedback by updating your branch and pushing the changes.
4. Once approved, your changes will be merged into the main documentation.

## What to Contribute

The following types of contributions are always welcome:

- **Typo and grammar fixes**: Correct spelling, grammar, or formatting errors.
- **Clarifications**: Improve unclear explanations or add missing context.
- **New content**: Write documentation for features or topics that are not yet covered.
- **Updates**: Update existing documentation to reflect changes in new Varbase releases.
- **Reorganization**: Suggest improvements to the documentation structure for better navigation and discoverability.

## Resources

- Varbase Documentation Repository: Check the Vardot GitHub organization at [https://github.com/Vardot](https://github.com/Vardot).
- GitBook Markdown Reference: [https://docs.gitbook.com/](https://docs.gitbook.com/)
- Drupal Documentation Guide: [https://www.drupal.org/docs/documentation-guide](https://www.drupal.org/docs/documentation-guide)
