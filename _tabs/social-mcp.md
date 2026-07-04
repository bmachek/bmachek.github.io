---
icon: fab fa-instagram
title: social-mcp
permalink: /social-mcp/
order: 6
description: >-
  Free, self-hosted MCP server that lets Claude manage your Instagram and
  Facebook Page — post photos, carousels and Reels, schedule content, pull
  engagement analytics, and autopilot two weeks of posts from a photo inbox.
---

<!-- SoftwareApplication + FAQ structured data for rich results -->
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@type": "SoftwareApplication",
      "name": "social-mcp",
      "operatingSystem": "Linux, macOS, Windows (Docker)",
      "applicationCategory": "DeveloperApplication",
      "description": "Self-hosted Model Context Protocol (MCP) server that gives Claude the ability to post photos, carousels and Reels to Instagram and a Facebook Page, schedule posts, read engagement analytics, and autopilot a two-week posting schedule from a local photo inbox via the Meta Graph API.",
      "url": "https://blog.fokuspunk.de/social-mcp/",
      "downloadUrl": "https://github.com/bmachek/social-mcp",
      "softwareHelp": "https://github.com/bmachek/social-mcp#setup",
      "author": { "@type": "Person", "name": "Bastian Machek" },
      "offers": { "@type": "Offer", "price": "0", "priceCurrency": "USD" }
    },
    {
      "@type": "FAQPage",
      "mainEntity": [
        {
          "@type": "Question",
          "name": "Can Claude post to Instagram and Facebook?",
          "acceptedAnswer": { "@type": "Answer", "text": "Yes, with social-mcp. It is a self-hosted MCP server that connects Claude Code or Claude Desktop to the Meta Graph API, giving Claude tools to post photos, carousels and Reels to Instagram and a Facebook Page, plus scheduling and analytics." }
        },
        {
          "@type": "Question",
          "name": "Where are my Meta access tokens stored with social-mcp?",
          "acceptedAnswer": { "@type": "Answer", "text": "Everything runs on your own machine. Your long-lived Meta User Access Token lives in a local .env file and never touches a third-party service — social-mcp talks directly to the Meta Graph API." }
        },
        {
          "@type": "Question",
          "name": "What does the social-mcp autopilot do?",
          "acceptedAnswer": { "@type": "Answer", "text": "The autopilot scans your photo inbox, removes duplicate burst shots by perceptual hash, clusters photos taken close together in time and place into carousels, and proposes a two-week posting schedule. You review it and write captions, then a single commit queues everything." }
        },
        {
          "@type": "Question",
          "name": "Is social-mcp free?",
          "acceptedAnswer": { "@type": "Answer", "text": "Yes. social-mcp is free and self-hosted. The source is on GitHub at github.com/bmachek/social-mcp." }
        }
      ]
    }
  ]
}
</script>

**social-mcp** is a free, self-hosted [MCP server](https://modelcontextprotocol.io) that gives **Claude** the ability to run your **Instagram** and **Facebook Page**. You drop photos into a folder, tell Claude what to post and when, and it handles the rest — staging, uploading, archiving and scheduling. Everything runs on your own machine, so no third-party service ever touches your tokens or your media.

**Source:** [github.com/bmachek/social-mcp](https://github.com/bmachek/social-mcp) · [Setup guide](https://github.com/bmachek/social-mcp#setup) · [Issues](https://github.com/bmachek/social-mcp/issues)

#### What is MCP?

The [Model Context Protocol](https://modelcontextprotocol.io) is the standard way to give AI assistants access to external tools. social-mcp implements it, so Claude Code or Claude Desktop can connect and gain a set of posting, scheduling and analytics tools backed by the Meta Graph API.

#### Features

* **Post immediately** — photos, carousels (2–10 images) and Reels to Instagram, a Facebook Page, or both platforms at once. Stories and Facebook Group cross-posting included.

* **Schedule for later** — queue any post at a specific time or relatively (`in 2h`, `tomorrow at 19:30`). The scheduler is persistent and survives container restarts.

* **Analytics** — account-level reach, engagement and follower metrics, per-post insights (likes, comments, shares, saves, plays), and a ranking of your top-performing posts.

* **Autopilot** — scans your inbox, deduplicates burst shots by perceptual hash, clusters photos taken close together in time and place into carousels, and proposes a two-week schedule. You review and write captions; one commit queues it all.

* **Private by design** — your Meta token stays in a local `.env` file. For local files, an nginx sidecar briefly serves each image at a one-shot public URL so Meta can fetch it, then tears it down and archives the file.

#### Requirements

* A **Meta App** (type: Business) with Facebook Login for Business + Instagram Graph API
* A long-lived **User Access Token** with `pages_show_list`, `pages_read_engagement`, `pages_manage_posts`, `instagram_basic` and `instagram_content_publish` scopes (add `publish_to_groups` for Group cross-posting)
* **Docker Compose** (recommended) or Python 3.8+
* A connected **Instagram Business/Creator account** and a **Facebook Page**

#### Setup

1. Create a Meta App and generate a long-lived User Access Token with the scopes above.
2. Copy `.env.example` to `.env` and fill in your token, Page ID and Instagram User ID.
3. Run `docker compose up -d --build` — this starts the MCP server (default port 3224) and an nginx file sidecar (default port 3223).
4. Register the server with your MCP client (Claude Code or Claude Desktop).

The full walkthrough — Meta App creation, token generation, `.env` configuration and reverse proxy — is in the [SETUP guide](https://github.com/bmachek/social-mcp#setup).

#### Usage

Once connected, just ask Claude in plain language:

> *"Post the sunset shot from my inbox to Instagram and Facebook with this caption, and add it to my story."*

> *"Schedule these three photos as an Instagram carousel for tomorrow at 19:30."*

> *"Plan the next two weeks from my inbox, then show me the carousels you'd make."*

For a step-by-step walkthrough, see [How to let Claude run your Instagram and Facebook with social-mcp]({{ '/posts/manage-instagram-facebook-with-claude/' | relative_url }}).

> **Note:** social-mcp has no built-in authentication. Restrict it at the network layer, or put a TLS-terminating reverse proxy with a bearer-token check in front if you expose it beyond your LAN.
{: .prompt-warning }

#### License

Free and self-hosted — the source is on [GitHub](https://github.com/bmachek/social-mcp).
