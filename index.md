---
layout: page
title: Bastian Machek — Fokuspunk
description: >-
  Bastian Machek, aka Fokuspunk: photographer and open-source developer in Landshut.
  Explore MoodSwings, LrGeniusAI, Lightroom plugins and CIDP Buddy.
permalink: /
---

<p class="project-kicker">Photography · Open source · Landshut, Germany</p>

## Cameras, code, and a city with a temper.

I'm **Bastian Machek**, known online as **Fokuspunk**. I live in the Landshut area of southern Germany and build free software: tools for photographers, an app for everyday life with CIDP, and now a game about a very excitable city.

This is my personal blog and project hub. My photographs live at [fokuspunk.de](https://www.fokuspunk.de); my code lives on [GitHub as bmachek](https://github.com/bmachek).

## New project: MoodSwings

**[MoodSwings — Die Stadt der Flummis]({{ '/moodswings/' | relative_url }})** is an open-source comedy sandbox built in Rust and Bevy. Bounce through a city, annoy a stranger, cheer up a neighbour, and watch moods spread. One city variant, **Landshüpf**, uses real map data from Landshut.

[Meet MoodSwings]({{ '/moodswings/' | relative_url }}) · [Source code](https://github.com/bmachek/MoodSwings)

## Software I build

- **[LrGeniusAI]({{ '/LrGeniusAI/' | relative_url }})** — AI-powered tagging, descriptions, semantic photo search, face recognition and species identification in Lightroom Classic. Built-in local AI or cloud models. [Website & downloads](https://lrgenius.com).
- **[LR Immich Plugin]({{ '/lrc-immich-plugin/' | relative_url }})** — Export, publish, import and sync photos between Lightroom Classic and a self-hosted Immich server.
- **[Lightroom PicPeak Plugin]({{ '/lrc-picpeak/' | relative_url }})** — Publish photos from Lightroom Classic to self-hosted PicPeak client galleries.
- **[social-mcp]({{ '/social-mcp/' | relative_url }})** — A self-hosted bridge for managing Instagram and Facebook content through an AI assistant.
- **[CIDP Buddy]({{ '/cidp-buddy/' | relative_url }})** — An app for managing infusions, medication, supplies, schedules, and a vitals and symptom diary. Built from my own experience of living with CIDP.

## Latest from the blog

{% for post in site.posts limit:5 %}
- [{{ post.title }}]({{ post.url | relative_url }}) — {{ post.date | date: '%B %-d, %Y' }}
{% endfor %}

[Browse all articles]({{ '/archives/' | relative_url }})

## The person behind Fokuspunk

Photography and programming meet throughout my projects: organising a photo library, connecting it to tools I host myself, or building a world to look around in. Read more [about Bastian Machek]({{ '/about-me/' | relative_url }}), explore my [photography gear]({{ '/gear/' | relative_url }}), or [get in touch]({{ '/contact-me/' | relative_url }}).

<div lang="de" markdown="1">
### Bastian Machek / Fokuspunk — auf Deutsch

Ich bin Bastian Machek, online als Fokuspunk unterwegs: Fotograf und Open-Source-Entwickler aus der Region Landshut. Hier schreibe ich über meine Projekte — von Lightroom-Plugins und LrGeniusAI über CIDP Buddy bis zu meinem Spiel MoodSwings. Fotos findest du auf [fokuspunk.de](https://www.fokuspunk.de), die Projektbeschreibungen und Anleitungen überwiegend auf Englisch hier im Blog.
</div>
