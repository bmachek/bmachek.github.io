---
icon: fas fa-share
title: LR Immich Plugin
permalink: /lrc-immich-plugin/
order: 4
---

A Lightroom Classic plugin that **uploads and imports** images to and from an [Immich](https://immich.app/) server via the Immich API. It supports **export** as well as **publish**.

**Source:** [github.com/bmachek/lrc-immich-plugin](https://github.com/bmachek/lrc-immich-plugin) · [Releases](https://github.com/bmachek/lrc-immich-plugin/releases) · [Issues](https://github.com/bmachek/lrc-immich-plugin/issues)

#### Features

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

#### Download

[![GitHub downloads](https://img.shields.io/github/downloads/bmachek/lrc-immich-plugin/total.svg)](https://github.com/bmachek/lrc-immich-plugin/releases)  
[**Download latest release**](https://github.com/bmachek/lrc-immich-plugin/releases/latest/)

#### Installation

See the [installation instructions on GitHub](https://github.com/bmachek/lrc-immich-plugin#installation).

#### Usage

After installing, enter your Immich **server URL** and [**API key**](https://immich.app/docs/features/command-line-interface#obtain-the-api-key) in the export preset and/or in the Immich publish service.

**Required API key permissions:**  
`activity.read` · `asset.read` · `asset.upload` · `asset.replace` · `asset.delete` · `asset.download` · `asset.update` · `asset.copy` · `albumAsset.create` · `albumAsset.delete` · `album.read` · `album.create` · `album.delete` · `album.update` · `user.read` · `stack.create`

#### Troubleshooting

Check the plugin **log file** first: open the Lightroom **Plug-in Manager**, select the Immich plugin, enable **debug logging**, and use **Show log file**.  
If that doesn’t help, [open an issue](https://github.com/bmachek/lrc-immich-plugin/issues/new/choose) on GitHub.

#### Credits

* All contributors  
* [Jeffrey Friedl](https://regex.info/blog/lua/json) — JSON.lua  
* [Enrique García Cota](https://github.com/kikito/inspect.lua) — inspect.lua  
* [Min Idzelis](https://github.com/midzelis/mi.Immich.Publisher) — ideas from his Immich Publisher plugin