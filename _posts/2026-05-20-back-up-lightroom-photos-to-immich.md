---
title: "How to back up your Lightroom Classic photos to Immich"
date: 2026-05-20 09:00:00 +0200
categories: [Immich, Lightroom]
tags: [lrc-immich-plugin, immich, lightroom, backup, self-hosted]
description: >-
  A step-by-step guide to backing up your Adobe Lightroom Classic library to a
  self-hosted Immich server using the free, open-source Lightroom Immich Plugin.
howto:
  name: "How to back up Lightroom Classic photos to Immich"
  steps:
    - name: "Install the Lightroom Immich Plugin"
      text: "Download the latest release from github.com/bmachek/lrc-immich-plugin/releases/latest/ and add it in Lightroom Classic via File → Plug-in Manager → Add, pointing at the unzipped plugin folder."
    - name: "Connect to your Immich server"
      text: "In an export preset or publish service settings, enter your Immich server URL and API key. The key needs upload, album, and read permissions."
    - name: "Choose Export or Publish"
      text: "Use Export for a one-shot archive of a finished shoot. Use a Publish Service for an ongoing backup: add, edit, or remove photos in Lightroom, and the next publish updates Immich to match."
    - name: "Enable stacking (optional)"
      text: "Turn on stacking to group raw and edited versions of the same image into Immich stacks, so your Immich timeline mirrors how you organize in Lightroom."
faq:
  - q: "Does the plugin prevent duplicate uploads to Immich?"
    a: "Yes. The plugin detects duplicates by Lightroom catalog ID, or by date and filename, so re-running an export or publish will not create copies."
  - q: "What is the difference between Export and Publish for backup?"
    a: "Export is a one-time push, ideal for archiving finished shoots. Publish creates a live link: add, edit, or remove photos in Lightroom and the next publish updates Immich to match, including creating and renaming albums."
  - q: "Does the plugin work with raw files?"
    a: "Yes. The plugin uploads files from your Lightroom catalog, including raws. Enable stacking to group raw and edited versions under a primary image in Immich."
  - q: "Can I back up to a self-hosted Immich server?"
    a: "Yes. The plugin connects to any Immich instance via its URL and API key, including self-hosted servers on a local network or VPN."
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

## Frequently asked questions

**Does the plugin prevent duplicate uploads?**

Yes. The plugin detects duplicates by Lightroom catalog ID, or by date and filename — re-running an export or publish will not create copies.

**What is the difference between Export and Publish for backup?**

**Export** is a one-time push, ideal for archiving a finished shoot. **Publish** creates a live link: add, edit, or remove photos in Lightroom and the next publish updates Immich to match, including creating and renaming albums. For true ongoing backup, use Publish.

**Does the plugin work with raw files?**

Yes. The plugin uploads files from your Lightroom catalog, including raws. Enable **stacking** to group raw and edited versions under a primary image in Immich.

**Can I back up to a self-hosted Immich server?**

Yes. The plugin connects to any Immich instance via its URL and API key — including self-hosted servers on a home network or reachable over VPN.

**What do I need to get started?**

Adobe Lightroom Classic (Windows or macOS), a running Immich server, an Immich API key, and the [Lightroom Immich Plugin]({{ '/lrc-immich-plugin/' | relative_url }}) (free and open source).
