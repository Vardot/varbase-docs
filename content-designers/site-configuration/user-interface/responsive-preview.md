# Responsive Preview

Responsive Preview allows you to test how your site and content appear on different screen sizes and devices directly from the admin interface. This is valuable for ensuring that your content looks good across desktops, tablets, and mobile phones.

## How to Use Responsive Preview

1. Navigate to the page you want to preview.
2. Click the **Responsive Preview** icon in the admin toolbar. The icon typically looks like a mobile device or screen.
3. A toolbar of device options appears at the top of the page.
4. Click on a device to preview the current page at that device's screen dimensions.
5. The page is displayed in a resizable frame that simulates the selected device's viewport.

## Pre-Configured Devices

Responsive Preview comes with several pre-configured device profiles representing common screen sizes:

| Device | Type | Typical Resolution |
|---|---|---|
| iPhone 15 | Mobile (Portrait) | 393 x 852 |
| iPhone 15 (Landscape) | Mobile (Landscape) | 852 x 393 |
| Galaxy S23 | Mobile (Portrait) | 360 x 780 |
| Galaxy S23 (Landscape) | Mobile (Landscape) | 780 x 360 |
| iPad Pro | Tablet (Portrait) | 1024 x 1366 |
| iPad Pro (Landscape) | Tablet (Landscape) | 1366 x 1024 |

These are representative resolutions. The actual devices listed and their resolutions may vary based on your site's configuration.

## What to Check During Preview

When previewing your content on different devices, verify the following:

- **Text readability** -- Is the text legible without zooming? Are paragraphs well-spaced?
- **Image sizing** -- Do images scale properly? Are they too large or too small on the previewed device?
- **Navigation** -- Does the site menu work correctly on smaller screens?
- **Layout** -- Do multi-column layouts stack properly on mobile devices? Are there any horizontal scrolling issues?
- **Interactive elements** -- Are buttons, links, and form fields large enough to tap on mobile devices?
- **Media embeds** -- Do embedded videos and other media resize correctly?

## Exiting Responsive Preview

Click the **Responsive Preview** icon again or click the close button (X) on the preview toolbar to exit the preview mode and return to the normal view.

## Limitations

- Responsive Preview simulates screen dimensions but does not replicate actual device behavior (touch interactions, device-specific browsers, etc.).
- For comprehensive device testing, supplement Responsive Preview with testing on actual devices or browser developer tools.
- Some complex JavaScript interactions may behave differently in the preview frame than on actual devices.

## Tips

- Preview content on at least one mobile, one tablet, and one desktop resolution before publishing.
- Pay special attention to content with Layout Builder sections that use multiple columns, as these are most likely to be affected by responsive behavior.
- If the preview reveals layout issues, adjust the content, section styles, or image sizes before publishing.
- Use Responsive Preview in combination with the content Preview button to see exactly how unpublished content will appear on different devices.
