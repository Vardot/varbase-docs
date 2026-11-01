# Generate Alt Text for Many Images

After a migration from an old site, hundreds of images may have no alternative text. With the AI recipes, a bulk tool finds every image that is missing it and suggests alt text for all of them in one run. You review the suggestions before anything is saved.

## Steps

1. As a **Super Admin**, go to **Configuration** \ **Media** \ _**Bulk Generate Alt Text with AI**_ (`/admin/config/media/ai_image_bulk_alt_text`). The page lists each image with missing alt text, the item it belongs to, and an empty **New Alt Text** field. If nothing is missing, it says so.
2. Click **Bulk Generate Alt Text with AI** to fill every **New Alt Text** field, or **Generate with AI** on one row at a time.
3. Read each suggestion against its image and correct it: the AI does not know why the image was chosen.
4. Click **Save changes**. Only then is the alt text saved on the images.

## Planning Notes

- Each suggestion is one AI call, so a large library costs credits. Estimate the cost, try a small batch first, and agree the budget with the client.
- Plan it like a small project: run, review a sample, correct, and only then call it done.
- The house style for alt text comes from the site's AI context. See [Show a Client What Context Changes](../ai-in-varbase/show-a-client-what-context-changes.md).

See [Image](uploading-media-files/image.md#writing-good-alt-text) for what good alt text says.
