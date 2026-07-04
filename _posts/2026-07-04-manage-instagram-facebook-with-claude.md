---
title: "How to let Claude run your Instagram and Facebook with social-mcp"
date: 2026-07-04 09:00:00 +0200
categories: [social-mcp, AI]
tags: [social-mcp, mcp, claude, instagram, facebook, self-hosted, automation]
description: >-
  Install social-mcp, a free self-hosted MCP server, to let Claude post photos,
  carousels and Reels to Instagram and Facebook, schedule content, read
  engagement analytics, and autopilot two weeks of posts from a photo inbox —
  all on your own machine.
howto:
  name: "How to let Claude run your Instagram and Facebook with social-mcp"
  steps:
    - name: "Create a Meta App and token"
      text: "Create a Meta App (type: Business), add Facebook Login for Business and the Instagram Graph API, and generate a long-lived User Access Token with the pages and instagram_content_publish scopes."
    - name: "Clone social-mcp"
      text: "Clone github.com/bmachek/social-mcp to your server or homelab machine, then copy .env.example to .env."
    - name: "Configure your credentials"
      text: "Fill in your Meta User Access Token, Facebook Page ID and Instagram User ID in the .env file."
    - name: "Start the server"
      text: "Run docker compose up -d --build to start the MCP server and its nginx file sidecar."
    - name: "Connect Claude"
      text: "Register the server with Claude Code (claude mcp add) or Claude Desktop (Custom Connector), then ask Claude to post or schedule from your photo inbox."
faq:
  - q: "Can Claude post to Instagram and Facebook?"
    a: "Yes, with social-mcp — a self-hosted MCP server that connects Claude Code or Claude Desktop to the Meta Graph API. Claude gets tools to post photos, carousels and Reels to Instagram and a Facebook Page, plus scheduling and analytics."
  - q: "Where are my Meta access tokens stored?"
    a: "On your own machine, in a local .env file. social-mcp talks directly to the Meta Graph API, so no third-party service ever handles your token or your media."
  - q: "What does the autopilot do?"
    a: "It scans your photo inbox, removes duplicate burst shots by perceptual hash, clusters photos taken close together in time and place into carousels, and proposes a two-week posting schedule. You review it and write captions, then one commit queues everything."
  - q: "Do I need a personal Instagram account?"
    a: "No — you need an Instagram Business or Creator account connected to a Facebook Page, which is what the Instagram Graph API requires for publishing."
  - q: "Is social-mcp free?"
    a: "Yes. social-mcp is free and self-hosted. The source is on GitHub at github.com/bmachek/social-mcp."
---

If you post photography to Instagram and Facebook, most of the work isn't the shooting — it's the tedious pipeline of choosing shots, staging them, writing captions, and remembering to actually publish on a schedule. [social-mcp]({{ '/social-mcp/' | relative_url }}) hands that pipeline to **Claude**. It's a free, self-hosted [MCP server](https://modelcontextprotocol.io) that runs on your own machine and gives Claude Code (or Claude Desktop) the ability to post, schedule and analyse across both platforms — while your Meta token never leaves your server.

This guide walks through getting it running end to end.

## What you'll need

- A **Meta App** (type: Business) with **Facebook Login for Business** and the **Instagram Graph API** enabled
- A long-lived **User Access Token** with these scopes:
  - `pages_show_list`, `pages_read_engagement`, `pages_manage_posts`
  - `instagram_basic`, `instagram_content_publish`
  - `publish_to_groups` (optional — only for Facebook Group cross-posting)
- An **Instagram Business or Creator account** connected to a **Facebook Page**
- **Docker Compose** (recommended) or Python 3.8+
- **Claude Code** or **Claude Desktop** as the MCP client

## 1. Create a Meta App and generate a token

In the [Meta for Developers](https://developers.facebook.com/) console, create an app of type **Business** and add **Facebook Login for Business** plus the **Instagram Graph API**. Then generate a **long-lived User Access Token** carrying the scopes listed above.

You'll also need two IDs: your **Facebook Page ID** and your **Instagram User ID**. The full walkthrough — including the token-exchange curl commands — lives in the project's [SETUP guide](https://github.com/bmachek/social-mcp#setup).

> Long-lived user tokens last about 60 days. social-mcp ships a `check_token_validity` tool so you (or Claude) can check the expiry and re-exchange before it lapses.
{: .prompt-tip }

## 2. Get social-mcp onto your server

Clone the repository somewhere permanent on the machine that will run it — a homelab box or VPS is ideal:

```bash
git clone https://github.com/bmachek/social-mcp.git
cd social-mcp
cp .env.example .env
```

## 3. Configure your credentials

Open `.env` and fill in at least these values:

```bash
META_USER_TOKEN=<your long-lived user token>
META_PAGE_ID=<your Facebook Page ID>
META_IG_USER_ID=<your Instagram User ID>
```

Everything else has sensible defaults — the MCP server listens on port `3224` and the nginx file sidecar on `3223`.

## 4. Start the server

```bash
docker compose up -d --build
```

Two containers come up:

- `instagram-mcp` — the MCP server on `MCP_PORT` (default 3224)
- `instagram-mcp-files` — an nginx sidecar on `FILE_SERVER_PORT` (default 3223) that briefly serves each image at a one-shot public URL so Meta can fetch it, then tears it down

Prefer plain Python? `python -m venv .venv && source .venv/bin/activate`, `pip install -r requirements.txt`, then `python server.py`.

## 5. Connect Claude

**Claude Code:**

```bash
claude mcp add instagram -- docker run --rm -i \
  --env-file /opt/social/.env \
  instagram-mcp:latest
```

**Claude Desktop:** go to **Settings → Developer → Custom Connectors → Add** and point it at:

```
http://<host>:3224/mcp
```

That's it — Claude now has the full toolset.

## 6. Post something

Drop photos or videos into `data/images/` and ask Claude in plain language. A few examples of what it can do:

- *"Post the sunset shot from my inbox to Instagram and Facebook with this caption, and add it to my story."*
- *"Make an Instagram carousel from these four frames and schedule it for tomorrow at 19:30."*
- *"Show me my top-performing posts from the last 30 days so I can reuse the caption style."*

Behind the scenes, files flow from your inbox to the platforms and get archived on success:

```
data/images/  →  stage → publish  →  Instagram / Facebook Page
                     ↓ on success
                 data/posted/YYYY-MM-DD/
```

## The autopilot: two weeks of posts in one pass

The feature that saves the most time is **autopilot**. Instead of planning posts one at a time, you let Claude propose a whole schedule:

1. `autopilot_plan` scans your inbox, **deduplicates burst shots** by perceptual hash, **clusters** photos taken close together in time and place into carousels, and proposes a **two-week posting schedule**.
2. You review the plan and write captions where you want them.
3. `autopilot_commit` validates everything and queues it all at once.

From a folder of raw exports to a fortnight of scheduled content, reviewed by you, in a couple of prompts.

## A note on security

social-mcp has **no built-in authentication** — it trusts whoever can reach it on the network. Keep it on your LAN, or put a TLS-terminating reverse proxy with a bearer-token check in front if you need to reach it from outside. The README includes a [Caddy](https://caddyserver.com/) example for exposing the file sidecar over Tailscale/Headscale.

Also worth knowing: the Instagram Graph API caps publishing at **50 posts per rolling 24-hour window**. social-mcp checks this before each publish and refuses rather than failing halfway.

## Wrapping up

Once it's running, social-mcp turns social posting into a conversation. You curate the photos; Claude handles the staging, uploading, scheduling and archiving — and the whole thing stays on hardware you control.

Grab it from [github.com/bmachek/social-mcp](https://github.com/bmachek/social-mcp), and see the [project page]({{ '/social-mcp/' | relative_url }}) for the full tool reference.

## Frequently asked questions

**Can Claude post to Instagram and Facebook?**

Yes — with [social-mcp]({{ '/social-mcp/' | relative_url }}). It's a self-hosted MCP server that connects Claude Code or Claude Desktop to the Meta Graph API, giving Claude tools to post photos, carousels and Reels to Instagram and a Facebook Page, plus scheduling and analytics.

**Where are my Meta access tokens stored?**

On your own machine, in a local `.env` file. social-mcp talks directly to the Meta Graph API, so no third-party service ever handles your token or your media.

**What does the autopilot do?**

It scans your photo inbox, removes duplicate burst shots by perceptual hash, clusters photos taken close together in time and place into carousels, and proposes a two-week posting schedule. You review it and write captions, then one commit queues everything.

**Do I need a personal Instagram account?**

No — you need an Instagram **Business or Creator** account connected to a Facebook Page, which is what the Instagram Graph API requires for publishing.

**Is social-mcp free?**

Yes — social-mcp is free and self-hosted. The source is on GitHub at [github.com/bmachek/social-mcp](https://github.com/bmachek/social-mcp).
