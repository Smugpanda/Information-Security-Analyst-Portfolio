## WordPress Website Security

**Executive Summary:**

This document outlines the security measures implemented to protect the WordPress website from common web application vulnerabilities and ensure PCI compliance for online payments. These measures enhance website security, protect sensitive data, and ensure compliance with PCI DSS requirements by preventing unauthorized access, detecting and blocking malicious traffic, and providing real-time security monitoring.

**Technologies Used:**

*   WordPress (Version 6.x)
*   Wordfence Security Plugin (Version 7.x)
*   WPS Hide Login Plugin
*   Cloudflare Web Application Firewall (WAF) (Pro Plan)
*   UpdraftPlus Backup Plugin
*   Authorize.Net Hosted Payment Form

**Security Measures:**

*   **Installed and Configured Wordfence Security Plugin:**
    *   *Rationale:* Provides comprehensive security features, including a firewall, malware scanner, and login security.
    *   *Configuration:* Enabled real-time threat intelligence feed, set firewall to Extended Protection mode, and scheduled daily malware scans.
*   **Installed and Configured WPS Hide Login Plugin:**
    *   *Rationale:* Changes the default WordPress login URL to prevent brute-force attacks.
    *   *Configuration:* Changed the login URL to a custom value and blocked access to the default login URL.
*   **Enforced 2FA for Admin Accounts:**
    *   *Rationale:* Adds an extra layer of security to prevent unauthorized access to admin accounts.
    *   *Implementation:* Used Google Authenticator plugin to enforce 2FA for all admin accounts.
*   **Configured Cloudflare WAF:**
    *   *Rationale:* Protects against common web application attacks, such as SQL injection and cross-site scripting (XSS).
    *   *Configuration:* Enabled OWASP ModSecurity Core Rule Set, blocked requests from known malicious IP addresses, and challenged requests with suspicious user agents.
*   **Automated Core and Plugin Updates:**
    *   *Rationale:* Ensures the website is up-to-date with the latest security patches.
    *   *Implementation:* Configured automatic updates for WordPress core, themes, and plugins using WordPress's built-in auto-update feature.
*   **Implemented Daily Offsite Backups:**
    *   *Rationale:* Provides a way to recover the website in case of a disaster.
    *   *Implementation:* Used UpdraftPlus to create daily backups of the website files and database and store them on a secure Amazon S3 bucket.

**PCI Compliance for Online Payments:**

*   Used Authorize.Net Hosted Payment Form to reduce the scope of PCI DSS compliance.
*   Disabled card data storage to prevent data breaches.
*   Implemented monthly file integrity monitoring to detect unauthorized changes to website files.
*   Regularly review and update the security measures to address emerging threats and vulnerabilities.

**Configuration Examples:**

```
# Example Cloudflare WAF rules
Rule 1: Block requests from known malicious IP addresses
Rule 2: Challenge requests with suspicious user agents
```