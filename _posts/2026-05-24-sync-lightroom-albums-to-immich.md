---
title: "Sync Lightroom albums to Immich with a Publish Service"
date: 2026-05-24 09:00:00 +0200
categories: [Immich, Lightroom]
tags: [lrc-immich-plugin, immich, lightroom, publish-service, albums]
description: >-
  Keep your Lightroom Classic collections and Immich albums in sync automatically
  using a Publish Service in the free Lightroom Immich Plugin.
howto:
  name: "Sync Lightroom albums to Immich with a Publish Service"
  steps:
    - name: "Create a Publish Service"
      text: "In Lightroom Classic's Publish Services panel, create a new service with the Immich plugin, then enter your Immich server URL and API key."
    - name: "Add a published collection"
      text: "Right-click the new service and add a published collection. Give it a name — the plugin automatically creates a matching album in Immich."
    - name: "Add photos and publish"
      text: "Drag photos into the published collection, then click Publish. The plugin uploads them to the Immich album. From now on, changes to the collection are reconciled on every subsequent publish."
faq:
  - q: "What is a Lightroom Publish Service?"
    a: "A Publish Service keeps a live link between a Lightroom collection and a destination. Changes to the collection — added, edited, or removed photos — are reconciled on the next publish run."
  - q: "Can I sync multiple Lightroom albums to Immich at once?"
    a: "Yes. Create one published collection per album within the same Publish Service. Each collection maps to one Immich album and is synced independently."
  - q: "What happens if I delete a photo from a Lightroom published collection?"
    a: "On the next publish, the plugin removes the photo from the corresponding Immich album."
  - q: "Can I receive comments from Immich back into Lightroom?"
    a: "Yes. If the Immich album is a shared album, the plugin downloads comments and likes from Immich back into Lightroom during each publish."
  - q: "What is the difference between Export and Publish?"
    a: "Export is a fire-and-forget one-time push. Publish maintains a live link between a Lightroom collection and an Immich album, keeping them in sync as the collection changes."
---

A one-off export is fine for archiving, but if you want your **Immich albums to track your Lightroom collections** as you add, edit and remove photos, you want a **Publish Service**. Here's how it works with the [Lightroom Immich Plugin]({{ '/lrc-immich-plugin/' | relative_url }}).

## Export vs. Publish — the key difference

An **export** is a fire-and-forget push. A **publish service** keeps a *live link* between a Lightroom collection and its destination. Change the collection and the next publish reconciles the difference. That's exactly what you want for albums you maintain over time — a "Best of 2026" set, a client gallery, a portfolio.

## Setting up the Publish Service

1. In Lightroom Classic's **Publish Services** panel, create a new service with the Immich plugin.
2. Enter your Immich **server URL** and **API key**.
3. Create a **published collection**. The plugin will create a matching **album in Immich**.

From now on the collection and the Immich album stay aligned.

## What gets synced

When you publish, the plugin will:

- **Create, rename or delete albums** to match your published collections.
- **Upload, update or delete images** as the collection changes.
- **Download comments and likes** from Immich back into Lightroom — if the album is a **shared album**, your viewers' feedback comes to you.

So if you rename a collection, the Immich album is renamed. Remove a photo from the collection, and it's removed from the album on the next publish.

## Tips for clean syncing

- **Duplicate detection** prevents re-uploads when the same image is already in Immich (matched by Lightroom catalog ID, or by date and filename).
- Enable **stacking** to group raw + edited versions under a primary image so the album doesn't show near-duplicates.
- Use **debug logging** (Plug-in Manager → Show log file) if a publish behaves unexpectedly — it's the fastest way to see what the plugin sent to Immich.

## Why publish instead of export

If you only ever need a snapshot, export. If you treat Immich as the place you and others actually *browse* your photos, publish — your albums become a faithful, self-updating mirror of how you curate in Lightroom.

Got a question or want album sharing options in the publish settings? There's an open [discussion](https://github.com/bmachek/lrc-immich-plugin/discussions/16) for feature requests.

## Frequently asked questions

**What is a Lightroom Publish Service?**

A Publish Service keeps a **live link** between a Lightroom collection and a destination. Changes to the collection — added, edited, or removed photos — are reconciled on the next publish run. This is different from a one-shot Export.

**Can I sync multiple albums to Immich at once?**

Yes. Create one **published collection** per album within the same Publish Service. Each collection maps to one Immich album and is synced independently.

**What happens if I delete a photo from a published collection?**

On the next publish, the plugin removes the photo from the corresponding Immich album.

**Can I receive comments and likes from Immich back into Lightroom?**

Yes. If the Immich album is a **shared album**, the plugin downloads comments and likes from Immich back into Lightroom during each publish.

**What is the difference between Export and Publish?**

Export is a fire-and-forget one-time push. Publish maintains a live link — use it when Immich is the place you and others actually browse your photos, so albums stay a faithful mirror of how you curate in Lightroom.

See also: [how to install the plugin]({{ '/posts/install-lightroom-immich-plugin/' | relative_url }}) and [how to back up your library to Immich]({{ '/posts/back-up-lightroom-photos-to-immich/' | relative_url }}).
