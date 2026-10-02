---
title: Support — OpenAPI Viewer for Confluence
---

# Support

**App:** OpenAPI Viewer for Confluence · **Publisher:** Atesen Software
**Email:** sametatesen2@gmail.com · **First response target:** 2 business days (Monday–Friday, Istanbul time, UTC+3)

## Getting started

1. Edit a page, type `/OpenAPI` and choose **OpenAPI Viewer**.
2. Paste a definition (YAML or JSON), pick a `.yaml`, `.yml` or `.json` file attached to the page, or enter a URL.
3. Publish the page.

To move pages from an older Connect-based Swagger app, see the [migration guide](migration-guide.html).

## Before you write

- Your site URL (`yoursite.atlassian.net`)
- The page URL, and whether the definition is pasted, attached or loaded from a URL
- The message shown by the macro, or the migration ID and error code from the CSV report

## Severity and response

| Severity | Example | Target |
|---|---|---|
| S1 | A migration changed pages incorrectly | Same-day acknowledgement, fix or workaround within 2 business days |
| S2 | Definitions do not render at all | 3 business days |
| S3 | Question or feature request | Answered in the next weekly pass |

## Known limits

- Definitions larger than **5 MB** are not loaded.
- URL definitions must be reachable from the internet without a login. Definitions behind a login: attach the file to the page instead.
- "Try it out" is turned off: the viewer documents an API but does not send requests to it.
- The migration tool runs with the permissions of the administrator who starts it. Pages that administrator cannot edit are skipped and listed in the report.
- Search results can take a few minutes to include recently edited pages.
- Migration records are deleted **30 days** after a migration was started.

## Updates

Releases are published through the Atlassian Marketplace with release notes. Minor updates install automatically; an update that needs new permissions must be approved by a Confluence administrator.

## Security reports

Email sametatesen2@gmail.com with the subject line **SECURITY**. We acknowledge within 2 business days and tell you when a fix ships.
