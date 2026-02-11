# Configuring Security Features

Varbase 11.0.x provides a comprehensive set of security features through the **Varbase Security Base** recipe. This recipe installs and configures multiple modules designed to protect your site against common security threats including spam, brute-force attacks, cross-site scripting (XSS), clickjacking, and weak passwords.

## Security Modules Included

The Varbase Security Base recipe installs and configures the following security components:

| Module | Purpose |
| --- | --- |
| CAPTCHA | Challenge-response test for form submissions |
| reCAPTCHA | Google reCAPTCHA integration |
| Honeypot | Invisible spam trap for forms |
| Antibot | JavaScript-based bot detection |
| Password Policy | Configurable password strength requirements |
| SecKit | HTTP security headers and protection settings |
| Flood Control | Rate limiting for login and form submissions |

## Sections

### [Spam Protection](spam-protection.md)

Configure CAPTCHA, reCAPTCHA, Honeypot, and Antibot to protect forms against automated spam submissions.

### [Password Policies](password-policies.md)

Configure password strength requirements including character types, minimum length, history restrictions, and username restrictions.

### [Security Kit](security-kit.md)

Configure SecKit for protection against XSS, CSRF, and clickjacking attacks through HTTP security headers.

### [Flood Control](flood-control.md)

Configure rate limiting for login attempts and contact form submissions to prevent brute-force attacks.
