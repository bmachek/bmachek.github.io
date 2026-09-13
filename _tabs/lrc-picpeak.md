---
icon: fas fa-mountain
title: Lightroom PicPeak Plugin
permalink: /lrc-picpeak/
order: 5
description: >-
  Lightroom PicPeak Plugin: publish client galleries, import proofing ratings
  onto RAW files and return finished edits. Initially built by Bastian Machek.
project_schema: lrc-picpeak
faq:
  - q: What does the Lightroom PicPeak Plugin do?
    a: "The plugin uploads photos from Lightroom Classic to a self-hosted PicPeak server and imports client proofing selections back onto matching local RAW files. Bastian Machek (Fokuspunk) wrote the initial implementation."
  - q: Can I bring client ratings and colour labels into Lightroom?
    a: "Yes. Use PicPeak Importer to choose an event and your local RAW folder. Matching files are added to the catalog with ratings and colour labels, subject to your chosen conflict policy. The server must support GET /api/v1/events/:id/photos."
  - q: Do finished edits preserve the client's feedback?
    a: "When an imported photo is exported back to the same PicPeak event, the plugin uses its stored photo ID to replace the proof while preserving ratings, labels, comments and gallery position. Exporting to a different event creates a new copy."
  - q: Where are my PicPeak credentials stored?
    a: "The current plugin exchanges your password once for an API token and stores the token in the operating system keychain. It does not keep your password. SSO or reCAPTCHA setups require a manually created token."
---

The **Lightroom PicPeak Plugin** connects **Adobe Lightroom Classic** to self-hosted **PicPeak client galleries**. Upload proofs, let a client mark favourites, bring those selections back to matching RAW files, and send the finished edits to the same gallery.

I wrote the initial implementation as **Bastian Machek / Fokuspunk**. The project now lives in the [PicPeak organisation](https://github.com/PicPeak/plugin-lightroom), whose [current documentation](https://docs.picpeak.app/guides/lightroom-roundtrip) covers the full round-trip workflow.

## From proofs to finished photographs

1. Upload camera JPEGs to a PicPeak event.
2. Your client selects colour labels and star ratings while proofing.
3. In Lightroom, open **Library → Plug-in Extras → PicPeak Importer**. Select the event and the folder containing your RAW files.
4. Import all matching files or only marked selections. The plugin adds them to the catalog, applies the chosen ratings and labels, and collects them into a collection.
5. Edit the RAW files and export to the **same event**. Stored photo IDs connect the finished renders to their proofs, preserving feedback and gallery position even after renaming.

Colour labels must be enabled in the event's feedback settings. Importing selections also requires a PicPeak server with the event-photos API endpoint; older servers may support export and publish but not the importer.

## Your existing edits and ratings matter

The importer offers conflict policies for photos that already have ratings or labels. **Fill empty only** is the default. You can choose to prefer PicPeak, prefer existing Lightroom values, or use the highest-priority value. Check that choice before applying a client's selections to an already-triaged catalog.

For multi-camera shoots, keep filenames distinguishable before uploading. Ambiguous matches are skipped and reported. The [matching guide](https://github.com/PicPeak/plugin-lightroom#-multi-camera-shoots) explains camera prefixes and the optional trailing-number fallback.

## Install and connect

The plugin runs from source and has no separate installer. Download or clone [PicPeak/plugin-lightroom](https://github.com/PicPeak/plugin-lightroom), then use **File → Plug-in Manager → Add** to select the `picpeak-plugin.lrplugin` folder.

Open **Library → Plug-in Extras → PicPeak Overview**, choose **Config**, enter your server URL and select **Sign in…**. Your account must be allowed to create API tokens. The plugin exchanges the password for a token and stores that token in the **operating system keychain**.

If the server uses SSO or reCAPTCHA, use **Advanced** and paste an API token instead. See the [current connection instructions](https://github.com/PicPeak/plugin-lightroom#-connect) for permissions and token management.

## Export, publish and troubleshoot

Use an export for a one-time delivery, or a Publish Service for an ongoing Lightroom collection. Returning imported edits to the same event replaces their proofs; exporting to a different event creates new photos there.

If matching or publishing fails, enable logging in **Plug-in Manager → PicPeak → Logging**, reproduce the problem, and use **Show log file**. [Report issues in the current repository](https://github.com/PicPeak/plugin-lightroom/issues).

The earlier [Lightroom-to-PicPeak walkthrough]({{ '/posts/publish-lightroom-photos-to-picpeak/' | relative_url }}) is also available, with notes about the current connection workflow.

## Frequently asked questions

{% for item in page.faq %}
### {{ item.q }}

{{ item.a }}
{% endfor %}

{% include project-author.html %}
