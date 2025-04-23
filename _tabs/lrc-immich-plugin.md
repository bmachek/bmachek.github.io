---
icon: fas fa-share
title: LR Immich Plugin
permalink: /lrc-immich-plugin/
order: 4
---

A Lightroom Classic plugin which uploads images to an Immich Server.

#### Features

* Setup connection to your Immich instance via URL and API key in the export dialog, or when creating the publish service.

* Publish images:
    * Create/rename/delete album according to published collection.
    * Upload/update/delete images from the published collection.
    * Download comments and likes from Immich to Lightroom. (If album is a shared album.)

* Export images:
    * Optionally choose or create an album to use on export to Immich.
    * Replace existing images.
    * Duplicate detection via Lightroom catalog ID, and based on date and filename.

* Import images:
    * Import images album wise from Immich into the Lightroom Classic catalog.

* Upcoming features:
    * (Maybe) Additional album options like sharing in the Published Collection settings dialog.
    * (Maybe) [Your feature](https://github.com/bmachek/lrc-immich-plugin/discussions/16)

#### Download the plugin
[Download](https://github.com/bmachek/lrc-immich-plugin/releases/latest/)

#### Installation

[Installation guide]({% link _articles/install-plugin.md %})

#### Usage

After you successfully installed the plugin, enter the server url and [API key](https://immich.app/docs/features/command-line-interface#obtain-the-api-key) in your export preset and/or in your Immich publish service.
You're good to go.

#### Troubleshooting

If you run into troubles, best thing to do is check the log file.
Easiest way to find the log file, is by opening the Lightroom module manager, navigate to the Immich plugin, and enable debug logging.
There's also a button *Show log file*. 
If nothing helps, [open an issue](https://github.com/bmachek/lrc-immich-plugin/issues/new/choose) over at GitHub.

#### Credits

* All contributors
* Enrique García Cota for [inspect.lua](https://github.com/kikito/inspect.lua)
* Jeffrey Friedl for [JSON.lua](https://regex.info/blog/lua/json)