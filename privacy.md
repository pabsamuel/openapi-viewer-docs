---
title: Privacy Policy — OpenAPI Viewer for Confluence
---

# Privacy Policy

**App:** OpenAPI Viewer for Confluence
**Publisher:** Atesen Software (independent developer, Türkiye)
**Contact:** sametatesen2@gmail.com
**Last updated:** 2 October 2026

## 1. What this app does with data

The app runs inside your Atlassian Cloud site on the Atlassian Forge platform. It has two parts:

**The OpenAPI Viewer macro** shows an OpenAPI 3 or Swagger 2 definition on a Confluence page. Depending on how a page author configured the macro, the definition comes from:

- text pasted into the macro — stored by Confluence in the page itself, like any other macro setting;
- a file attached to the page — read with the viewer's own Confluence permissions each time the page is viewed;
- a URL — fetched by the app each time the page is viewed.

The definition is passed to the reader's browser and rendered there. **The app does not store API definitions, and does not write them to logs.**

**The migration tool** (Confluence administration → Apps) finds macros from older Connect-based Swagger/OpenAPI apps and converts them to the OpenAPI Viewer macro. To show progress, produce a report and let you undo a migration, it stores for each migrated page: the page ID, page title, space name, page version numbers, the result (for example "converted" or "failed") and an error code.

The app does not store Atlassian account IDs, email addresses or display names, and does not read comments, user profiles or any content other than the pages it is asked to scan or migrate.

## 2. Where data is stored and where it goes

All processing and storage happen on Atlassian's Forge platform, inside Atlassian's cloud infrastructure. The app has no servers of its own.

**Outbound requests:** when a macro is configured with a URL, the app requests that URL through Atlassian's Forge egress to download the API definition. The request contains only that URL; no Confluence content, user identity or page data is sent. The app makes no other outbound requests. There are no analytics services, advertising networks or sub-processors, and **no data is sent to Atesen Software**.

## 3. How long data is kept

Migration records are deleted automatically **30 days** after the migration was started. Uninstalling the app removes the app's storage according to Atlassian's Forge data retention policies. Macro settings, including pasted definitions, are part of your pages and remain under your control in Confluence.

## 4. Logs

Application logs contain migration IDs, counts, HTTP status codes and error codes. **They never contain API definitions, page content, page titles or personal data.** Forge logs are stored by Atlassian and are visible to the publisher only through Atlassian's developer tooling, with Atlassian's own retention limits.

## 5. Roles

For data processed by this app on your site, your organization is the controller and Atesen Software acts as a processor to the limited extent described here. Atlassian is the infrastructure provider; see Atlassian's privacy policy for how they process data in your cloud site.

## 6. Your requests

To ask about data handled by this app, or to request deletion of migration records on your site, write to sametatesen2@gmail.com.

## 7. Security

All Confluence requests run with the permissions of the user who views the page or runs the migration; the app cannot read or change pages that user cannot. The migration tool is only available to Confluence administrators. URLs are limited to http and https, URLs containing credentials are rejected, and definitions larger than 5 MB are refused. Macros from older apps that loaded definitions with a username, password or token are not migrated, so no credentials are copied into the new macro.

## 8. Changes

Material changes to this policy are announced in the release notes on the app's Atlassian Marketplace listing.
