# Google Analytics

Google Analytics tells you how visitors use your site: which pages they read, where they come from and what they do. A standard Varbase 11 site does not include it; your development team adds it when your site needs it. This page explains how it fits in.

## Adding Google Analytics

Your development team adds Google Analytics, usually with the **Google Analytics** recipe from Drupal CMS, and enters your measurement ID (it starts with `G-`). Ask them for it; it is not a setting in the editor screens on a new site.

## Consent Comes First

Analytics sets cookies, so visitors are asked for consent first. The cookie consent manager already lists **Google Analytics** and **Google Tag Manager** as services; your team turns the right one on when analytics is added. Visitors who decline are not tracked. See [Cookie Consent](../../cookie-consent.md).

## Checking It Works

1. Open your site in a private browser window and accept the analytics service.
2. In Google Analytics, open the real-time report: your visit should appear within a minute.

## Tips

- Ask your team to leave out logged-in editors, so your own visits do not count.
- Agree with your team which actions to measure, such as form submissions and downloads.
- Use the data to decide what to write next, and which old pages to update.
