---
title: "How to publish Lightroom photos to a self-hosted PicPeak gallery"
date: 2026-07-04 00:00:00 +0200
last_modified_at: 2026-09-13 12:00:00 +0200
categories: [PicPeak, Lightroom]
tags: [lrc-picpeak, picpeak, lightroom, client-gallery, installation]
description: >-
  Connect Lightroom Classic to PicPeak, publish client galleries and bring
  proofing ratings back to RAW files. A guide by Bastian Machek / Fokuspunk.
howto:
  name: "Publish Lightroom photos to PicPeak"
  steps:
    - name: "Download the plugin"
      text: "Download or clone github.com/PicPeak/plugin-lightroom into a permanent folder."
    - name: "Add the plugin in Lightroom Classic"
      text: "Use File → Plug-in Manager → Add and select picpeak-plugin.lrplugin."
    - name: "Connect your server"
      text: "Open Library → Plug-in Extras → PicPeak Overview, choose Config, enter your server URL and sign in. For SSO or reCAPTCHA, paste a manually created API token under Advanced."
    - name: "Publish photos"
      text: "Use PicPeak Exporter for a one-time delivery or a Publish Service for an ongoing collection."
    - name: "Bring selections back"
      text: "Use PicPeak Importer to match event photos to local RAW files and apply ratings and labels under your chosen conflict policy."
faq:
  - q: "Does the Lightroom PicPeak Plugin work on macOS?"
    a: "Yes. The plugin supports Lightroom Classic on macOS and Windows."
  - q: "How do I sign in?"
    a: "Open PicPeak Overview under Library → Plug-in Extras, choose Config and sign in to your server. Your account needs permission to create API tokens. For SSO or reCAPTCHA, use Advanced and paste a token with the admin scope."
  - q: "Where does the current plugin store credentials?"
    a: "The password is exchanged once for a token and not retained. The token is stored in the operating system keychain."
  - q: "Can I import client selections?"
    a: "Yes, on a server with GET /api/v1/events/:id/photos. PicPeak Importer matches proofs to local RAW files and applies ratings and colour labels according to your conflict policy."
---

The **[Lightroom PicPeak Plugin]({{ '/lrc-picpeak/' | relative_url }})** takes photographs from Lightroom Classic to a self-hosted client gallery, then brings client selections back for editing. I wrote its initial implementation; this guide reflects the current workflow in the [PicPeak repository](https://github.com/PicPeak/plugin-lightroom).

**Updated September 2026:** connection now uses PicPeak Overview and an operating-system keychain token. The workflow also includes importing client ratings and returning finished edits to their proofs.

## What you'll need

- Lightroom Classic on Windows or macOS.
- A PicPeak server with the v1 API enabled.
- An account allowed to create API tokens.
- Local RAW files if you want to import proofing selections.

Importing selections needs a server that supports `GET /api/v1/events/:id/photos`. Older servers can support exporting and publishing without supporting the importer.

## 1. Download and install

[Download or clone the current plugin](https://github.com/PicPeak/plugin-lightroom) into a permanent folder. Open **File → Plug-in Manager → Add** in Lightroom Classic and choose `picpeak-plugin.lrplugin`.

The plugin runs from source, with no build step. If you update its files, use **Reload Plug-in** in the Plug-in Manager.

## 2. Connect to PicPeak

Open **Library → Plug-in Extras → PicPeak Overview**, then choose **Config**. Enter your server URL and click **Sign in…**.

The plugin exchanges your password for an API token, stores the token in the operating system keychain, and does not retain the password. Tokens can be revoked in PicPeak's **Settings → API Tokens**.

For SSO or reCAPTCHA setups, use **Advanced** and paste a manually created token with the required `admin` scope. Consult the [connection documentation](https://github.com/PicPeak/plugin-lightroom#-connect) for your server configuration.

## 3. Export or publish a gallery

For a one-time delivery, select photos and use **File → Export → PicPeak Exporter**. Choose your target event, configure the rendered image format and size, and export.

For an ongoing Lightroom collection, use the PicPeak **Publish Service**. Keep track of which event you publish to: that connection matters when you later return edited photos.

For proofing, upload JPEGs with filenames that can be matched to the original RAWs. Enable colour labels in the event feedback settings if clients should use them.

## 4. Import client selections

After the client has marked their choices, open **PicPeak Importer**. Select the event and the folder holding your RAW files, then choose all files or marked selections.

The importer matches local files, applies ratings and colour labels, and collects them in Lightroom. **Fill empty only** is the default conflict policy, so existing values are preserved. Change the policy deliberately if PicPeak's selections should override your own.

On a multi-camera shoot, make filenames unique before uploading. The [matching guide](https://github.com/PicPeak/plugin-lightroom#-multi-camera-shoots) explains camera prefixes and the number-matching fallback. Ambiguous matches are reported rather than guessed.

## 5. Return the finished edits

Edit the matched RAWs and export to the **same event** they came from. The plugin uses the stored PicPeak photo ID to replace each proof, preserving its ratings, labels, comments and gallery position. Renaming the Lightroom photo does not break that ID-based link.

If you export to a different event, the render becomes a new photo there.

## Troubleshooting

Enable logging in **Plug-in Manager → PicPeak → Logging**, repeat the failed action, and use **Show log file**. For an import problem, check filename matching, the selected RAW folder, the server endpoint and your conflict policy.

Use the [current round-trip guide](https://docs.picpeak.app/guides/lightroom-roundtrip) for more detail or [open an issue](https://github.com/PicPeak/plugin-lightroom/issues).

For a self-hosted personal photo library alongside client galleries, see the [Lightroom Immich Plugin]({{ '/lrc-immich-plugin/' | relative_url }}).

## Frequently asked questions

{% for item in page.faq %}
### {{ item.q }}

{{ item.a }}
{% endfor %}
