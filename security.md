---
title: Security — Atesen OpenAPI & Swagger Viewer for Confluence
---

# Security policy

**App:** Atesen OpenAPI & Swagger Viewer for Confluence · **Publisher:** Atesen Software
**Last updated:** 22 October 2026

## Reporting a vulnerability

Email **support@atesensoftware.com** with the subject line **SECURITY**. Include what you found, the steps to reproduce it and the impact you expect. We acknowledge within 2 business days and tell you when a fix ships. Please give us a reasonable period to fix an issue before disclosing it, and do not access data that is not yours. We do not run a paid bug bounty. Company-wide policy: [atesensoftware.com/security](https://atesensoftware.com/security/).

## How the app handles data

- **Runs on Atlassian Forge.** The app has no servers of its own and sends nothing to Atesen Software. Data stays in Atlassian's cloud (Forge storage) on your site.
- **What is stored:** for each migrated page the page ID, title, space name, version numbers, result and error code, plus the Atlassian account ID of the administrator who started the migration. Nothing else; no API definitions, email addresses or display names. Details: [privacy policy](privacy.html).
- **Retention:** migration records are deleted 30 days after the migration started. A weekly job reports stored account IDs to Atlassian's personal data reporting API and deletes records of closed accounts.
- **Encryption:** stored data and traffic are protected by the Forge platform (TLS in transit, Atlassian-managed encryption at rest). The app implements no cryptography of its own.
- **Logs** contain counts, status codes and error codes only, never definitions, page content or personal data.

## Access control

- Confluence requests run as the signed-in user (`asUser`); the app cannot read or change what that user cannot.
- The migration tool checks, before every action, that the user is a Confluence administrator, and a migration can only be seen, resumed, undone or deleted by the administrator who started it.
- Pages are only changed after an administrator reviews a preview and starts the migration; every change is a normal page version and can be undone. The only other write is **Create test page**: when an administrator clicks it, the app creates one page with sample macros under a page that administrator chose, with that administrator's permissions.

## Handling of API definitions and URLs

- Definitions are rendered in the reader's browser; "Try it out" is disabled, so the viewer never calls the documented API.
- URL sources must use https (also on each of at most 3 redirects). URLs with credentials and literal private or local IP addresses are rejected. Requests have a 10-second timeout and a 5 MB size limit, carry no Confluence data, and responses are neither stored nor logged.
- Credentials (username, password, token) used by older Connect apps are not migrated.

## Vulnerability management

- Production dependencies are checked with `npm audit --omit=dev` before every release (no known vulnerabilities at the time of writing) and the Forge linter is run before each deploy.
- Fixes ship as new Forge versions through the Atlassian Marketplace; material changes are listed in the release notes.

## What we do not claim

We hold no third-party security certification (such as SOC 2 or ISO 27001) for this app and do not take part in the Marketplace Bug Bounty program. The app is not "Runs on Atlassian" because it can fetch definitions from external URLs chosen by page authors.
