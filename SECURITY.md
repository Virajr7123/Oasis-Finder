# 🛡️ Security Policy

The Sweet Spot team is committed to ensuring the security of our application. We value the contributions of security researchers and the community in helping us identify and resolve security issues. This document outlines our policy for reporting vulnerabilities.

## Reporting a Vulnerability

Please **do not** report security vulnerabilities through public GitHub issues.

We ask that you use one of the following private channels:

1. **GitHub Private Vulnerability Reporting (Preferred)**

   - Navigate to the main page of the "Sweet Spot" repository.

   - Click on the **Security** tab.

   - Click on the "Report a vulnerability" button.

2. **📧 Email**

   - If you cannot use GitHub's reporting feature, you can send your report directly to: **sawantviraj976@gmail.com**

Please provide a detailed description of the vulnerability, including:

- Steps to reproduce it.

- The potential impact.

- Screenshots or code snippets, if applicable.

We will make every effort to acknowledge your report within 48 hours and will keep you informed of our progress in resolving the issue.

## Guidelines for Contributors

To protect our users and the integrity of our services, it is critical that all API keys and sensitive credentials are handled correctly.

> **Warning**
> Pull requests found to contain hardcoded keys or credentials will be rejected.

- 🚫 **NEVER** commit API keys, Firebase configurations, or other secrets to the repository.

## Scope

We are primarily interested in vulnerabilities in the "Sweet Spot" application code itself. While we appreciate all reports, the following are generally considered out of scope:

- ⚠️ Vulnerabilities in third-party services (e.g., Firebase, Google Maps, Foursquare). Please report these to the services directly.

- ⚠️ Reports from automated scanners without a clear, reproducible exploit.

- ⚠️ Social engineering or phishing attacks.

- ⚠️ Vulnerabilities in out-of-date dependencies (we use Dependabot to manage these).

## 🤝 Our Commitment

We are committed to working with the community to resolve security issues. We will be transparent about our findings and will credit researchers who report vulnerabilities in a responsible manner.

Thank you for helping keep Sweet Spot secure.
