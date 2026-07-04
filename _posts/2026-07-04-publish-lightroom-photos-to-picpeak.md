---
title: "How to publish Lightroom photos to a self-hosted PicPeak gallery"
date: 2026-07-04 09:00:00 +0200
categories: [PicPeak, Lightroom]
tags: [lrc-picpeak, picpeak, lightroom, client-gallery, installation]
description: >-
  Install the free Lightroom PicPeak Plugin in Lightroom Classic, connect it to
  your self-hosted PicPeak server with an API token, and deliver client galleries
  by export or publish service — without leaving Lightroom.
howto:
  name: "How to publish Lightroom photos to a self-hosted PicPeak gallery"
  steps:
    - name: "Download the plugin"
      text: "Download or clone github.com/PicPeak/plugin-lightroom and unzip it to a permanent location such as your Documents folder — not a Downloads folder you might clear."
    - name: "Add the plugin in Lightroom Classic"
      text: "Open Lightroom Classic, go to File → Plug-in Manager, click Add, and point it at the picpeak-plugin.lrplugin/ directory. Click Done."
    - name: "Create a PicPeak API token"
      text: "In PicPeak, create an API token with write and admin scopes. This lets the plugin create events and upload photos."
    - name: "Connect the plugin to PicPeak"
      text: "In the Export or Publish dialog, open the PicPeak Server section, enter your server URL and API token, and click Test Connection."
    - name: "Export or publish your photos"
      text: "Export selected photos to a PicPeak event for a one-time delivery, or set up a Publish Service collection to keep an event in sync with a Lightroom collection."
faq:
  - q: "What is PicPeak?"
    a: "PicPeak is an open-source, self-hosted photo-sharing platform for delivering time-limited, password-protected client galleries while keeping your data on your own server. The Lightroom PicPeak Plugin uploads photos from Lightroom Classic straight into it."
  - q: "Does the Lightroom PicPeak Plugin work on macOS?"
    a: "Yes, the plugin works on both Windows and macOS with Adobe Lightroom Classic."
  - q: "What API token permissions does the plugin need?"
    a: "A PicPeak API token with write and admin scopes. The write scope uploads photos, and admin is needed to create and manage events."
  - q: "Can I create a PicPeak event without leaving Lightroom?"
    a: "Yes. When exporting or setting up a publish collection you can create a new event inline with name, type, date, customer info, password protection, expiry, guest feedback and color theme."
  - q: "Is the Lightroom PicPeak Plugin free?"
    a: "Yes, it is free and open source under the MIT license. Get it at github.com/PicPeak/plugin-lightroom."
---

If you deliver client galleries and run a self-hosted [PicPeak](https://github.com/PicPeak/picpeak) server, this is the quickest path from a finished edit in Lightroom Classic to a live gallery your client can open. The [Lightroom PicPeak Plugin]({{ '/lrc-picpeak/' | relative_url }}) is free and open source and works on both Windows and macOS.

## What you'll need

- **Adobe Lightroom Classic** (Windows or macOS)
- A **running PicPeak server** (v1 API) — PicPeak is a self-hosted, open-source platform for time-limited, password-protected client galleries
- A **PicPeak API token** with `write` + `admin` scopes

## 1. Download the plugin

Grab the plugin from GitHub:

> **[Download from GitHub](https://github.com/PicPeak/plugin-lightroom)**

Download or clone the repository and unzip it somewhere permanent — for example your Documents folder. Don't run it from a temporary or Downloads folder you'll later clear out, or Lightroom will lose the plugin.

## 2. Add it in Lightroom Classic

1. Open Lightroom Classic.
2. Go to **File → Plug-in Manager**.
3. Click **Add**, browse to the `picpeak-plugin.lrplugin/` directory, and select it.
4. Click **Done**.

The plugin now appears in the **Export** dialog and in the **Publish Services** panel.

## 3. Get a PicPeak API token

In PicPeak, create an **API token** with `write` and `admin` scopes. The `write` scope lets the plugin upload photos, and `admin` lets it create and manage gallery events on your behalf.

## 4. Connect the plugin to PicPeak

You enter your connection details where you'll actually use the plugin:

1. In the **Export** or **Publish** dialog, find the **PicPeak Server** section.
2. Enter your server **URL** (e.g. `https://picpeak.example.com`) and your **API token**.
3. Click **Test Connection** to verify.

Credentials are stored in Lightroom preferences and reused across sessions.

## 5. Deliver your photos

You have two workflows, depending on whether this is a one-time delivery or an evolving gallery.

### Export a gallery

1. Select photos in Lightroom, then go to **File → Export**.
2. Choose **PicPeak Exporter** as the export destination.
3. Under **PicPeak Gallery Event**, pick one of:
   - **Choose on export** — a picker appears at export time
   - **Existing event** — select from a dropdown of your events
   - **Create new event** — fill in event details (name, type, date, customer info, password protection, expiry, guest feedback, color theme) inline
4. Configure the rest of your export settings (format, size, etc.) and click **Export**.

### Publish a collection

1. In the **Publish Services** panel, click **Set Up** next to PicPeak Publisher (or right-click to add a collection).
2. When creating the collection, choose to create a new PicPeak event or bind to an existing one.
3. Drag photos into the collection and click **Publish**.

With a publish collection, re-uploads are skipped for photos that were already published, so re-publishing only sends what's new. After each upload the plugin writes `picpeakPhotoId` and `picpeakEventId` back to the photo, so Lightroom always knows what already lives on the server.

## A note on deletes and renames

The PicPeak v1 API does not support deleting or renaming events or photos. If you try, the plugin warns you and marks the photos as handled in Lightroom without changing anything on the server. Plan your event names up front, and manage removals from the PicPeak admin interface.

## Troubleshooting

- **Plugin won't load / disappears:** make sure the folder lives in a permanent location and re-add it in the Plug-in Manager.
- **Connection fails:** double-check the server URL (including `https://`) and that your API token has both the `write` and `admin` scopes. Use **Test Connection** to confirm.
- Still stuck? [Open an issue](https://github.com/PicPeak/plugin-lightroom/issues) on GitHub.

That's the whole setup. If you also back up to Immich, see the companion [Lightroom Immich Plugin]({{ '/lrc-immich-plugin/' | relative_url }}).

## Frequently asked questions

**What is PicPeak?**

[PicPeak](https://github.com/PicPeak/picpeak) is an open-source, self-hosted photo-sharing platform for delivering **time-limited, password-protected** client galleries while keeping your data on your own server. The [Lightroom PicPeak Plugin]({{ '/lrc-picpeak/' | relative_url }}) uploads photos from Lightroom Classic straight into it.

**Does the plugin work on macOS?**

Yes, the [Lightroom PicPeak Plugin]({{ '/lrc-picpeak/' | relative_url }}) works on both **Windows and macOS** with Adobe Lightroom Classic.

**What API token permissions does the plugin need?**

A PicPeak API token with `write` and `admin` scopes — `write` uploads photos, and `admin` is needed to create and manage events.

**Can I create a PicPeak event without leaving Lightroom?**

Yes. When exporting or setting up a publish collection you can create a new event inline, with name, type, date, customer info, password protection, expiry, guest feedback and color theme.

**Is the Lightroom PicPeak Plugin free?**

Yes — it is free and open source under the MIT license. Get it at [github.com/PicPeak/plugin-lightroom](https://github.com/PicPeak/plugin-lightroom).
