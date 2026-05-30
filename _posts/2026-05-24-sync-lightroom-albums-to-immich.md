---
title: "Sync Lightroom albums to Immich with a Publish Service"
date: 2026-05-24 09:00:00 +0200
categories: [Immich, Lightroom]
tags: [lrc-immich-plugin, immich, lightroom, publish-service, albums]
description: >-
  Keep your Lightroom Classic collections and Immich albums in sync automatically
  using a Publish Service in the free Lightroom Immich Plugin.
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
