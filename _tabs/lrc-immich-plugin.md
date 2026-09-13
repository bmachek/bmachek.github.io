---
icon: fas fa-share
title: Lightroom Immich Plugin
permalink: /lrc-immich-plugin/
order: 4
description: >-
  Lightroom Immich Plugin by Bastian Machek: export, publish, sync albums and
  import photos between Lightroom Classic and your self-hosted Immich library.
project_schema: lrc-immich-plugin
faq:
  - q: "How do I upload Lightroom Classic photos to Immich?"
    a: "Install the Lightroom Immich Plugin, enter your Immich server URL and API key in an export preset or publish service, then export or publish your photos. The plugin uploads the images to Immich and can add them to an album."
  - q: "Can I sync Lightroom albums to Immich?"
    a: "Yes. Use a Publish Service: the plugin creates, renames and deletes Immich albums to match your published Lightroom collections, and uploads, updates or removes images as the collection changes."
  - q: "Is the Lightroom Immich Plugin free?"
    a: "Yes, it is free and open source. Download the latest release from GitHub."
---



![Immich Logo](/assets/img/lrc-immich-plugin/immich-logo.svg){: width="80" .left }

The **Lightroom Immich Plugin** (`lrc-immich-plugin`) is a free, open-source plugin that lets you **upload, sync, back up and import** photos between **Adobe Lightroom Classic** and an [Immich](https://immich.app/) server through the Immich API. Use it as an **export** preset or a **publish service** to keep your Lightroom catalog and your self-hosted Immich library in sync.

**Source:** [github.com/bmachek/lrc-immich-plugin](https://github.com/bmachek/lrc-immich-plugin) · [Releases](https://github.com/bmachek/lrc-immich-plugin/releases) · [Issues](https://github.com/bmachek/lrc-immich-plugin/issues)

## Features

* **Connection** — Set up your Immich instance via URL and API key in the export dialog or when creating the publish service.

* **Publish images**
    * Create/rename/delete albums according to the published collection.
    * Upload/update/delete images from the published collection.
    * Download comments and likes from Immich to Lightroom (if the album is a shared album).

* **Export images**
    * Optionally choose or create an album on export to Immich.
    * Replace existing images.
    * Duplicate detection via Lightroom catalog ID, and by date and filename.

* **Import images**
    * Import images album-wise from Immich into the Lightroom Classic catalog.

* **Stacking (Immich)**
    * When uploading, the plugin can create **stacks** in Immich so related assets (e.g. raw + edited, or multiple versions) are grouped with a primary image. Stacks keep your Immich timeline tidy and match how you organize in Lightroom.

* **Upcoming (maybe)**
    * Additional album options (e.g. sharing) in the Publish Collection settings.
    * [Suggest a feature](https://github.com/bmachek/lrc-immich-plugin/discussions/16)

## Download

[![GitHub downloads](https://img.shields.io/github/downloads/bmachek/lrc-immich-plugin/total.svg)](https://github.com/bmachek/lrc-immich-plugin/releases)  
[**Download latest release**](https://github.com/bmachek/lrc-immich-plugin/releases/latest/)

## Installation

Start with the [step-by-step installation guide]({{ '/posts/install-lightroom-immich-plugin/' | relative_url }}) or the [current GitHub Wiki](https://github.com/bmachek/lrc-immich-plugin/wiki).

## Choose your workflow

- [One-time export or ongoing backup]({{ '/posts/back-up-lightroom-photos-to-immich/' | relative_url }}) — send photos to your self-hosted library.
- [Sync collections with a Publish Service]({{ '/posts/sync-lightroom-albums-to-immich/' | relative_url }}) — keep an album aligned as you publish changes.
- Import from Immich — bring an album back into Lightroom for editing, following the [Wiki](https://github.com/bmachek/lrc-immich-plugin/wiki).

## Usage

After installing, enter your Immich **server URL** and [**API key**](https://immich.app/docs/features/command-line-interface#obtain-the-api-key) in the export preset and/or in the Immich publish service.

**Required API key permissions:**  
`activity.read` · `asset.read` · `asset.upload` · `asset.replace` · `asset.delete` · `asset.download` · `asset.update` · `asset.copy` · `albumAsset.create` · `albumAsset.delete` · `album.read` · `album.create` · `album.delete` · `album.update` · `user.read` · `stack.create`

## Troubleshooting

Check the plugin **log file** first: open the Lightroom **Plug-in Manager**, select the Immich plugin, enable **debug logging**, and use **Show log file**.  
If that doesn’t help, [open an issue](https://github.com/bmachek/lrc-immich-plugin/issues/new/choose) on GitHub.

## Credits

* All contributors  
* [Jeffrey Friedl](https://regex.info/blog/lua/json) — JSON.lua  
* [Enrique García Cota](https://github.com/kikito/inspect.lua) — inspect.lua  
* [Min Idzelis](https://github.com/midzelis/mi.Immich.Publisher) — ideas from his Immich Publisher plugin

## Frequently asked questions

{% for item in page.faq %}
### {{ item.q }}

{{ item.a }}
{% endfor %}

{% include project-author.html %}
