---
icon: fab fa-instagram
title: social-mcp
permalink: /social-mcp/
order: 6
description: >-
  social-mcp by Bastian Machek: a self-hosted MCP server for Instagram and
  Facebook Page publishing, scheduling and analytics through Claude.
project_schema: social-mcp
faq:
  - q: "Can Claude post to Instagram and Facebook?"
    a: "Yes, with social-mcp. It is a self-hosted MCP server that connects Claude Code or Claude Desktop to the Meta Graph API, giving Claude tools to post photos, carousels and Reels to Instagram and a Facebook Page, plus scheduling and analytics."
  - q: "Where are my Meta access tokens stored with social-mcp?"
    a: "Your Meta token is configured in a local .env file and is sent to Meta to authenticate API requests. Selected media is uploaded or made temporarily available for Meta to fetch."
  - q: "What does the social-mcp autopilot do?"
    a: "The autopilot scans your photo inbox, removes duplicate burst shots by perceptual hash, clusters photos taken close together in time and place into carousels, and proposes a two-week posting schedule. You review it and write captions, then a single commit queues everything."
  - q: "Is social-mcp free?"
    a: "Yes. social-mcp is free and self-hosted. The source is on GitHub at github.com/bmachek/social-mcp."
---



**social-mcp** is a free, self-hosted [MCP server](https://modelcontextprotocol.io) that gives **Claude** the ability to run your **Instagram** and **Facebook Page**. You drop photos into a folder, tell Claude what to post and when, and it handles the rest — staging, uploading, archiving and scheduling. The publishing server runs on your own machine. It sends publishing requests and selected media to Meta; your AI client's data handling depends on its provider and configuration.

**Source:** [github.com/bmachek/social-mcp](https://github.com/bmachek/social-mcp) · [Setup guide](https://github.com/bmachek/social-mcp/blob/main/SETUP.md) · [Issues](https://github.com/bmachek/social-mcp/issues)

## What is MCP?

The [Model Context Protocol](https://modelcontextprotocol.io) is the standard way to give AI assistants access to external tools. social-mcp implements it, so Claude Code or Claude Desktop can connect and gain a set of posting, scheduling and analytics tools backed by the Meta Graph API.

## Features

* **Post immediately** — photos, carousels (2–10 images) and Reels to Instagram, a Facebook Page, or both platforms at once.

* **Schedule for later** — queue any post at a specific time or relatively (`in 2h`, `tomorrow at 19:30`). The scheduler is persistent and survives container restarts.

* **Analytics** — account-level reach, engagement and follower metrics, per-post insights (likes, comments, shares, saves, plays), and a ranking of your top-performing posts.

* **Autopilot** — scans your inbox, deduplicates burst shots by perceptual hash, clusters photos taken close together in time and place into carousels, and proposes a two-week schedule. You review and write captions; one commit queues it all.

* **Self-hosted publishing** — your Meta token is configured in a local `.env` file and authenticates requests to Meta. For local files, an nginx sidecar briefly serves each image at a one-shot public URL so Meta can fetch it, then tears it down and archives the file.

## Requirements

* A **Meta App** (type: Business) with Facebook Login for Business + Instagram Graph API
* A long-lived **User Access Token** with `pages_show_list`, `pages_read_engagement`, `pages_manage_posts`, `instagram_basic` and `instagram_content_publish` scopes
* **Docker Compose** (recommended) or Python 3.8+
* A connected **Instagram Business/Creator account** and a **Facebook Page**

## Setup

1. Create a Meta App and generate a long-lived User Access Token with the scopes above.
2. Copy `.env.example` to `.env` and fill in your token, Page ID and Instagram User ID.
3. Run `docker compose up -d --build` — this starts the MCP server (default port 3224) and an nginx file sidecar (default port 3223).
4. Register the server with your MCP client (Claude Code or Claude Desktop).

The full walkthrough — Meta App creation, token generation, `.env` configuration and reverse proxy — is in the [SETUP guide](https://github.com/bmachek/social-mcp/blob/main/SETUP.md).

## Usage

Once connected, just ask Claude in plain language:

> *"Post the sunset shot from my inbox to Instagram and Facebook with this caption, and add it to my story."*

> *"Schedule these three photos as an Instagram carousel for tomorrow at 19:30."*

> *"Plan the next two weeks from my inbox, then show me the carousels you'd make."*

For a step-by-step walkthrough, see [How to let Claude run your Instagram and Facebook with social-mcp]({{ '/posts/manage-instagram-facebook-with-claude/' | relative_url }}).

> **Note:** social-mcp has no built-in authentication. Restrict it at the network layer, or put a TLS-terminating reverse proxy with a bearer-token check in front if you expose it beyond your LAN.
{: .prompt-warning }

## License

Free and self-hosted — the source is on [GitHub](https://github.com/bmachek/social-mcp).

## Frequently asked questions

{% for item in page.faq %}
### {{ item.q }}

{{ item.a }}
{% endfor %}

{% include project-author.html %}
