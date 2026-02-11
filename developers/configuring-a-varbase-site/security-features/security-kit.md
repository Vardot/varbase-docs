# Security Kit

The **Security Kit (SecKit)** module, installed by the **Varbase Security Base** recipe, provides a collection of security hardening options that protect your site against common web application attacks including cross-site scripting (XSS), cross-site request forgery (CSRF), and clickjacking.

## Accessing SecKit Configuration

Navigate to **Configuration > System > Security Kit settings**, or go to:

```
/admin/config/system/seckit
```

## Cross-Site Scripting (XSS) Protection

SecKit provides HTTP headers that help browsers prevent XSS attacks.

### Content Security Policy (CSP)

Content Security Policy is an HTTP header that tells the browser which sources of content are allowed to be loaded on the page. This helps prevent XSS attacks by blocking inline scripts, unauthorized external scripts, and other potentially malicious content.

To configure CSP:

1. Navigate to the SecKit settings page.
2. Under the **Content Security Policy** section, enable CSP.
3. Configure the directives:
   - **default-src**: Default source for all content types.
   - **script-src**: Allowed sources for JavaScript.
   - **style-src**: Allowed sources for CSS.
   - **img-src**: Allowed sources for images.
   - **font-src**: Allowed sources for fonts.
   - **connect-src**: Allowed sources for AJAX, WebSocket, and similar connections.
4. Save the configuration.

{% hint style="warning" %}
Configuring CSP too restrictively can break site functionality. Test thoroughly after making changes, especially if your site uses third-party services, CDNs, or embedded content.
{% endhint %}

## Clickjacking Protection

Clickjacking attacks trick users into clicking on hidden elements by overlaying them with seemingly innocent content. SecKit provides two mechanisms to prevent this:

### X-Frame-Options

The **X-Frame-Options** header controls whether the site can be loaded within an iframe on another domain.

Options:

- **DENY**: The page cannot be displayed in a frame on any site.
- **SAMEORIGIN**: The page can only be displayed in a frame on the same origin.
- **ALLOW-FROM**: The page can be displayed in a frame on the specified origin (limited browser support).

### frame-ancestors CSP Directive

The `frame-ancestors` directive in Content Security Policy provides a more modern and flexible alternative to X-Frame-Options.

## Cross-Site Request Forgery (CSRF) Protection

SecKit can set the **Origin** header validation to help prevent CSRF attacks. This works in conjunction with Drupal's built-in CSRF token protection.

## Additional Security Headers

SecKit also configures the following HTTP security headers:

### X-Content-Type-Options

Set to `nosniff` to prevent browsers from MIME-type sniffing, which can lead to security vulnerabilities when browsers interpret files as a different content type than intended.

### HTTP Strict Transport Security (HSTS)

Forces browsers to communicate with the site only over HTTPS. Configure:

- **max-age**: Duration (in seconds) that the browser should remember to only access the site over HTTPS.
- **includeSubDomains**: Apply the HSTS policy to all subdomains.
- **preload**: Allow the domain to be included in browser HSTS preload lists.

### Referrer Policy

Controls how much referrer information the browser includes when navigating from your site to another. Options range from `no-referrer` (send nothing) to `unsafe-url` (send the full URL).

## Recommended Configuration

For most Varbase sites, the following baseline configuration is recommended:

- **X-Frame-Options**: SAMEORIGIN
- **X-Content-Type-Options**: nosniff
- **HSTS**: Enabled with a max-age of at least 31536000 (one year), with includeSubDomains
- **Referrer Policy**: strict-origin-when-cross-origin
- **CSP**: Configure based on your site's specific requirements, starting with a report-only policy to identify issues before enforcing
