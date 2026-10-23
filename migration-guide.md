---
title: Migrating Swagger / OpenAPI macros before Connect end of support
---

# Keep your Swagger docs in Confluence after Connect end of support

Atlassian ends support for Connect apps on **31 January 2027**. After that date Connect apps receive only critical security fixes, and Atlassian has said some Connect features may stop working with little notice. If your API documentation lives in a macro from a Connect app that has not moved to Forge, Atlassian Administration → Connected apps shows a banner like *"This app is running on a platform that will be unsupported after January 2027"*.

Moving to a different app normally means opening every page and re-creating every macro by hand. Atesen OpenAPI & Swagger Viewer includes a migration tool that does this for you.

## Which macros can be migrated

The migration tool recognises these Connect macro keys:

| Macro key | Typically added by |
|---|---|
| `swagger-integration`, `swagger-open-api` | Open API (Swagger) Integration |
| `swagger-open-api-macro` | Visualize OpenAPI (Swagger) documentation |
| `swagger-ui` | Swagger UI for Confluence |
| `confluence-open-api`, `open-api` | Open API (Swagger) Editor / Viewer |

These are app names as listed on the Atlassian Marketplace; Atesen OpenAPI & Swagger Viewer is not affiliated with their publishers.

What is carried over:

- the definition URL, the definition pasted into the macro, or the attached file name;
- display options: operation expansion, model rendering, operation and tag sorting, filter box, maximum tags shown, operation IDs and extensions.

What is not carried over:

- usernames, passwords or tokens used to load a definition — attach the file to the page instead;
- "Try it out" settings — the viewer documents an API but does not call it.

## Step by step

1. Install **Atesen OpenAPI & Swagger Viewer for Confluence** from the Atlassian Marketplace. Keep the old app installed for now.
2. Go to **Confluence administration → Apps → Atesen OpenAPI & Swagger Viewer - migrate Swagger macros**.
3. Click **Scan for legacy macros**. You'll see every page you can access that contains one of the macros above, how many macros it has and where each definition comes from.
4. Untick any pages you want to leave alone, then click **Convert**.
5. Keep the page open until the progress bar finishes. If you close it, come back and click **Resume**.
6. Open a few converted pages to check them. Download the **CSV report** for your records.
7. Not happy? Click **Undo this migration**. Each page goes back to its previous version, unless someone edited it after the migration — those pages are left as they are and listed in the report.
8. When everything looks right, uninstall the old Connect app.

## What if the scan finds nothing?

The scan lists only pages that contain a macro from one of the supported older apps. On a site without such macros it shows the message *"No pages with legacy Swagger/OpenAPI macros were found that you can see"*; this is the expected result, and nothing is changed.

To try the whole migration on such a site (version 3.1.0 and later):

1. On the migration page, under **Try it on a test page**, paste the URL (or ID) of any page you can edit and click **Create test page**.
2. The app creates a child page with three sample legacy macros: one that loads `https://petstore3.swagger.io/api/v3/openapi.json`, one with a pasted OpenAPI 3 definition and one with a pasted Swagger 2 definition. The page appears in the preview at once; **Scan for legacy macros** also finds it after Confluence's search index updates (usually within a few minutes).
3. Click **Convert 1 page**, open the test page and check the three definitions. Then try **Undo this migration**.
4. Delete the test page when you are done.

To try the viewer itself without legacy macros, see [Try the viewer in two minutes](support.html#try-the-viewer-in-two-minutes).

## Good to know

- Every converted page gets a normal page version with the message *"Converted Swagger/OpenAPI macros (Atesen OpenAPI & Swagger Viewer migration)"*, so you can also restore single pages from page history.
- Page watchers may receive an update notification for each converted page.
- The tool only touches the macros listed above. Everything else on the page stays exactly as it was.

Questions: support@atesensoftware.com
