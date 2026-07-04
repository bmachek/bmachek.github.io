---
icon: fas fa-mountain
title: Lightroom PicPeak Plugin
permalink: /lrc-picpeak/
order: 5
description: >-
  Free, open-source Lightroom Classic plugin to upload and publish photos from
  Lightroom directly to a self-hosted PicPeak gallery server. Export presets,
  publish services, inline event creation, password protection and expiry.
---

<!-- SoftwareApplication + FAQ structured data for rich results -->
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@type": "SoftwareApplication",
      "name": "Lightroom PicPeak Plugin (lrc-picpeak)",
      "operatingSystem": "Windows, macOS",
      "applicationCategory": "MultimediaApplication",
      "description": "Free Lightroom Classic plugin to upload and publish photos from Adobe Lightroom Classic directly to a self-hosted PicPeak gallery server via the PicPeak API.",
      "url": "https://blog.fokuspunk.de/lrc-picpeak/",
      "downloadUrl": "https://github.com/PicPeak/plugin-lightroom",
      "softwareHelp": "https://github.com/PicPeak/plugin-lightroom#installation",
      "author": { "@type": "Person", "name": "Bastian Machek" },
      "offers": { "@type": "Offer", "price": "0", "priceCurrency": "USD" }
    },
    {
      "@type": "FAQPage",
      "mainEntity": [
        {
          "@type": "Question",
          "name": "How do I upload Lightroom Classic photos to PicPeak?",
          "acceptedAnswer": { "@type": "Answer", "text": "Install the Lightroom PicPeak Plugin, enter your PicPeak server URL and API token in an export preset or publish service, then export or publish your photos. The plugin uploads the images to a PicPeak gallery event, which you can also create inline without leaving Lightroom." }
        },
        {
          "@type": "Question",
          "name": "Can I create a PicPeak event from inside Lightroom?",
          "acceptedAnswer": { "@type": "Answer", "text": "Yes. The plugin lets you create a new event with full details — name, type, date, customer info, password protection, expiry, guest feedback and color theme — directly from the export or publish dialog." }
        },
        {
          "@type": "Question",
          "name": "Is the Lightroom PicPeak Plugin free?",
          "acceptedAnswer": { "@type": "Answer", "text": "Yes, it is free and open source under the MIT license. Get it from GitHub." }
        }
      ]
    }
  ]
}
</script>

The **Lightroom PicPeak Plugin** (`lrc-picpeak`) is a free, open-source plugin that uploads photos from **Adobe Lightroom Classic** directly to a self-hosted [PicPeak](https://github.com/PicPeak/picpeak) gallery server through the PicPeak API. Use it as an **export** preset or a **publish service** to deliver client galleries — weddings, birthdays, corporate and family shoots — straight from your catalog.

**Source:** [github.com/PicPeak/plugin-lightroom](https://github.com/PicPeak/plugin-lightroom) · [Issues](https://github.com/PicPeak/plugin-lightroom/issues)

#### What is PicPeak?

[PicPeak](https://github.com/PicPeak/picpeak) is an open-source, self-hosted photo-sharing platform — a privacy-friendly alternative to services like PicDrop. You create **time-limited, password-protected gallery events** for your clients while keeping full control over your data and branding on your own server.

#### Features

* **Export workflow** — upload selected photos directly to a PicPeak event during export.

* **Publish workflow** — maintain Lightroom publish collections synced to PicPeak events; re-uploads are skipped for photos that were already published.

* **Inline event creation** — create a new event with full details (name, type, date, customer info, password protection, expiry, guest feedback, color theme) without leaving Lightroom.

* **Plugin metadata** — `picpeakPhotoId` and `picpeakEventId` are written back to each photo after upload, so Lightroom always knows what lives on the server.

#### Supported event types

`wedding` · `birthday` · `corporate` · `family` · `other`

#### Requirements

* Adobe Lightroom Classic (Windows or macOS)
* A running [PicPeak](https://github.com/PicPeak/picpeak) server (v1 API)
* A PicPeak API token with `write` + `admin` scopes

#### Download & installation

1. Download or clone the [repository](https://github.com/PicPeak/plugin-lightroom).
2. In Lightroom Classic, open **File → Plug-in Manager**.
3. Click **Add** and point it at the `picpeak-plugin.lrplugin/` directory.
4. Click **Done** — the plugin now appears in the Export dialog and the Publish Services panel.

#### Usage

In the **PicPeak Server** section of the Export or Publish dialog, enter your server URL (e.g. `https://picpeak.example.com`) and API token, then click **Test Connection**. Credentials are stored in Lightroom preferences and reused across sessions.

For a step-by-step walkthrough, see [How to publish Lightroom photos to a self-hosted PicPeak gallery]({{ '/posts/publish-lightroom-photos-to-picpeak/' | relative_url }}).

> **Note:** The PicPeak v1 API does not support deleting or renaming events or photos. The plugin warns you if you attempt these operations and marks the photos as handled in Lightroom without modifying the server.
{: .prompt-info }

#### License

Free and open source under the [MIT license](https://github.com/PicPeak/plugin-lightroom/blob/main/LICENSE).
