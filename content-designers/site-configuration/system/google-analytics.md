# Google Analytics

Varbase supports integration with Google Analytics and Google Tag Manager for tracking visitor behavior, page views, and other site usage metrics. Analytics data helps you understand how visitors interact with your site and make data-driven content decisions.

## Setup Options

### Using the Drupal CMS Google Analytics Recipe

Varbase supports the `drupal_cms_google_analytics` recipe, which provides a streamlined setup for Google Analytics integration. Your development team can apply this recipe to configure the integration with minimal manual setup.

### Manual Configuration with Google Tag

Alternatively, you can configure Google Analytics/Tag Manager manually using the **Google Tag** module:

1. Navigate to **Configuration > System > Google Tag**, or go to `/admin/config/system/google-tag`.
2. Click **Add container** or edit the existing container configuration.
3. Enter your Google Tag container ID:
   - For Google Analytics 4: Enter the measurement ID (e.g., `G-XXXXXXXXXX`).
   - For Google Tag Manager: Enter the container ID (e.g., `GTM-XXXXXXX`).
4. Configure additional settings:
   - **Status**: Enable or disable tracking.
   - **Pages**: Optionally restrict tracking to specific pages.
   - **Roles**: Exclude specific roles from tracking (e.g., exclude administrators to avoid skewing analytics data).
5. Click **Save** to apply the configuration.

## Google Analytics 4 vs. Google Tag Manager

### Google Analytics 4 (GA4)

- Tracks page views, user sessions, and events directly.
- Provides built-in reports and analytics dashboards.
- Suitable for standard website analytics.

### Google Tag Manager (GTM)

- A container system that manages multiple tracking tags (Google Analytics, Facebook Pixel, etc.).
- Provides more flexibility for advanced tracking configurations.
- Changes can be made in the Google Tag Manager interface without modifying site code.
- Recommended for sites that need to manage multiple tracking scripts.

## What Analytics Tracks

With analytics configured, you can track:

- **Page views**: Which pages visitors view and how often.
- **User sessions**: How long visitors stay on your site and how many pages they visit.
- **Traffic sources**: Where visitors come from (search engines, social media, direct, referral).
- **User behavior**: How visitors navigate through your site.
- **Conversions**: Actions visitors take (e.g., form submissions, downloads).
- **Demographics**: General information about your audience (location, device, browser).

## Verifying the Configuration

After configuring analytics:

1. Visit your site's front end while logged out (or in incognito mode).
2. Open the analytics platform (Google Analytics or Tag Manager) and check for real-time data.
3. Verify that page views are being recorded.
4. If using Google Tag Manager, use the **Preview** mode to test tag firing.

## Tips

- **Exclude admin users.** Configure the tracking to exclude Administrator and Site Admin roles to avoid skewing your analytics data with internal traffic.
- **Respect privacy regulations.** Ensure that your analytics setup complies with applicable privacy regulations (GDPR, CCPA, etc.). This may require a cookie consent banner and anonymized IP tracking.
- **Review analytics regularly.** Use analytics data to inform content strategy. Identify high-performing content, common entry points, and areas where visitors drop off.
- **Set up goals and conversions.** Configure analytics goals for important user actions (form submissions, newsletter signups, etc.) to measure the effectiveness of your content.
- **Coordinate with your team.** Work with your development team to ensure the analytics setup is correct and that all necessary events are being tracked.
