---
title: "How to back up your Lightroom Classic photos to Immich"
date: 2026-05-20 09:00:00 +0200
categories: [Immich, Lightroom]
tags: [lrc-immich-plugin, immich, lightroom, backup, self-hosted]
description: >-
  A step-by-step guide to backing up your Adobe Lightroom Classic library to a
  self-hosted Immich server using the free, open-source Lightroom Immich Plugin.
---

If you edit in **Adobe Lightroom Classic** and self-host your photos with [Immich](https://immich.app/), you can keep a full, automatic backup of your library in Immich without leaving Lightroom. This guide shows you how, using the free, open-source [Lightroom Immich Plugin]({{ '/lrc-immich-plugin/' | relative_url }}).

## Why back up Lightroom to Immich?

Lightroom Classic stores your originals on local disk and your edits in a catalog. Immich gives you a self-hosted, Google-Photos-style archive with deduplication, mobile apps and sharing. Pushing your Lightroom photos into Immich gives you an **off-Lightroom copy** you fully control — no subscription, no cloud lock-in.

## What you need

- Adobe Lightroom Classic (Windows or macOS)
- A running Immich server you can reach over the network
- An **Immich API key** (Account Settings → API Keys in Immich)
- The [Lightroom Immich Plugin](https://github.com/bmachek/lrc-immich-plugin/releases/latest/)

## Step 1 — Install the plugin

Download the latest release and add it in Lightroom's **File → Plug-in Manager → Add**. Point it at the unzipped plugin folder. See the [installation instructions](https://github.com/bmachek/lrc-immich-plugin#installation) for details.

## Step 2 — Connect to your Immich server

In an **export preset** or when creating a **publish service**, enter your Immich **server URL** and **API key**. The key needs upload, album and read permissions — the [plugin page]({{ '/lrc-immich-plugin/' | relative_url }}) lists the exact scopes.

## Step 3 — Choose backup vs. living sync

There are two ways to get photos into Immich, and they suit different goals:

- **Export** — a one-shot push. Great for archiving a finished shoot. The plugin offers **duplicate detection** (by Lightroom catalog ID, or by date and filename) so re-running an export won't create copies.
- **Publish** — a *living* backup. The published collection stays linked: add, edit or remove a photo in Lightroom and the next publish updates Immich to match, including creating and renaming albums.

For a true ongoing backup, use a **Publish Service** so your Immich copy tracks your catalog over time.

## Step 4 — Keep your timeline tidy with stacking

If you keep raw + edited versions, enable **stacking**. On upload the plugin groups related assets into Immich stacks with a primary image, so your Immich timeline mirrors how you organize in Lightroom instead of doubling up.

## That's it

Once connected, backing up is just hitting **Export** or **Publish**. Your Lightroom edits land in Immich, deduplicated and organized.

Questions or a feature idea? Open an [issue](https://github.com/bmachek/lrc-immich-plugin/issues) or [discussion](https://github.com/bmachek/lrc-immich-plugin/discussions) on GitHub.
