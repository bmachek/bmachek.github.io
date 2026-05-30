---
title: "How to install the Lightroom Immich Plugin (Windows & macOS)"
date: 2026-05-28 09:00:00 +0200
categories: [Immich, Lightroom]
tags: [lrc-immich-plugin, immich, lightroom, installation, api-key]
description: >-
  Install the free Lightroom Immich Plugin in Lightroom Classic on Windows or
  macOS, connect it to your Immich server with an API key, and upload your first photos.
---

This is the quickest path from "I have Lightroom Classic and an Immich server" to "my photos are uploading." The [Lightroom Immich Plugin]({{ '/lrc-immich-plugin/' | relative_url }}) is free and open source and works on both Windows and macOS.

## 1. Download the plugin

Grab the latest release from GitHub:

> **[Download latest release](https://github.com/bmachek/lrc-immich-plugin/releases/latest/)**

Unzip it somewhere permanent — for example your Documents folder. Don't run it from a temporary or Downloads folder you'll later clear out, or Lightroom will lose the plugin.

## 2. Add it in Lightroom Classic

1. Open Lightroom Classic.
2. Go to **File → Plug-in Manager**.
3. Click **Add**, browse to the unzipped plugin folder, and select it.
4. The Immich plugin now appears in the list as enabled.

## 3. Get an Immich API key

In Immich, open **Account Settings → API Keys** and create a key. The plugin needs permissions for uploading, reading and managing assets and albums. The full list of required scopes is on the [plugin page]({{ '/lrc-immich-plugin/' | relative_url }}) — granting all of them is the simplest path. (See the Immich docs on [obtaining an API key](https://immich.app/docs/features/command-line-interface#obtain-the-api-key).)

## 4. Connect the plugin to Immich

You enter your connection details where you'll actually use the plugin:

- **For exports:** in the **Export** dialog, choose the Immich plugin and fill in your server **URL** and **API key**.
- **For publishing:** when you create an Immich **Publish Service**, enter the same URL and key.

## 5. Upload your first photos

- **Export** a few photos to push them once (with duplicate detection so re-runs are safe), or
- Create a **publish service** for a collection that should stay in sync with an Immich album.

Optionally pick or create a destination **album** during export, and enable **stacking** to group raw + edited versions.

## Troubleshooting installation

- **Plugin won't load / disappears:** make sure the folder lives in a permanent location and re-add it in the Plug-in Manager.
- **Upload errors:** open the Plug-in Manager, select the Immich plugin, enable **debug logging**, click **Show log file**, and check what the plugin reported. Most issues are a wrong server URL or missing API-key permission.
- Still stuck? [Open an issue](https://github.com/bmachek/lrc-immich-plugin/issues/new/choose) on GitHub with the log.

That's the whole setup. From here, see [how to back up your Lightroom library to Immich]({{ '/posts/back-up-lightroom-photos-to-immich/' | relative_url }}) or [sync albums with a publish service]({{ '/posts/sync-lightroom-albums-to-immich/' | relative_url }}).
