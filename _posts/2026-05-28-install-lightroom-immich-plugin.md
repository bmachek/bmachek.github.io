---
title: "How to install the Lightroom Immich Plugin (Windows & macOS)"
date: 2026-05-28 09:00:00 +0200
categories: [Immich, Lightroom]
tags: [lrc-immich-plugin, immich, lightroom, installation, api-key]
description: >-
  Install the free Lightroom Immich Plugin in Lightroom Classic on Windows or
  macOS, connect it to your Immich server with an API key, and upload your first photos.
howto:
  name: "How to install the Lightroom Immich Plugin (Windows & macOS)"
  steps:
    - name: "Download the plugin"
      text: "Grab the latest release from github.com/bmachek/lrc-immich-plugin/releases/latest/ and unzip it to a permanent location such as your Documents folder — not a Downloads folder you might clear."
    - name: "Add the plugin in Lightroom Classic"
      text: "Open Lightroom Classic, go to File → Plug-in Manager, click Add, and browse to the unzipped plugin folder. The plugin appears in the list as enabled."
    - name: "Create an Immich API key"
      text: "In Immich, open Account Settings → API Keys and create a key. Grant upload, album-read/write, asset, and stack permissions. The full scope list is on the plugin page."
    - name: "Enter your Immich server URL and API key"
      text: "In the Lightroom Export dialog or when creating a Publish Service, enter your Immich server URL and the API key you just created."
    - name: "Upload your first photos"
      text: "Export selected photos for a one-time push, or create a Publish Service collection to keep an Immich album in continuous sync with a Lightroom collection."
faq:
  - q: "Does the Lightroom Immich Plugin work on macOS?"
    a: "Yes, the plugin works on both Windows and macOS with Adobe Lightroom Classic."
  - q: "Where do I find my Immich API key?"
    a: "In Immich, go to Account Settings → API Keys and create a new key. The plugin needs permissions including asset.upload, album.read, album.create, stack.create, and related scopes. The full list is on the plugin page at blog.fokuspunk.de/lrc-immich-plugin."
  - q: "Why does the plugin disappear from Lightroom after a restart?"
    a: "Lightroom loses plugins stored in temporary locations. Store the plugin folder in a permanent place such as Documents and re-add it in File → Plug-in Manager."
  - q: "Is the Lightroom Immich Plugin free?"
    a: "Yes, it is free and open source. Download the latest release at github.com/bmachek/lrc-immich-plugin/releases/latest."
  - q: "What does duplicate detection do?"
    a: "The plugin checks whether an image already exists in Immich by matching the Lightroom catalog ID, or by date and filename, so re-running an export or publish will not create duplicate copies."
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

## Frequently asked questions

**Does the plugin work on macOS?**

Yes, the [Lightroom Immich Plugin]({{ '/lrc-immich-plugin/' | relative_url }}) works on both **Windows and macOS** with Adobe Lightroom Classic.

**Where do I find my Immich API key?**

In Immich, go to **Account Settings → API Keys** and create a new key. The plugin needs permissions including `asset.upload`, `album.read`, `album.create`, `stack.create`, and related scopes — the full list is on the [plugin page]({{ '/lrc-immich-plugin/' | relative_url }}).

**Why does the plugin disappear from Lightroom after a restart?**

Lightroom loses plugins stored in temporary locations like Downloads. Move the plugin folder to a permanent place (e.g. Documents) and re-add it in **File → Plug-in Manager**.

**Is the Lightroom Immich Plugin free?**

Yes — it is free and open source. [Download the latest release](https://github.com/bmachek/lrc-immich-plugin/releases/latest/) from GitHub.

**What does duplicate detection do?**

The plugin checks whether an image already exists in Immich by matching the Lightroom catalog ID, or by date and filename — so re-running an export or publish will not create duplicate copies.
