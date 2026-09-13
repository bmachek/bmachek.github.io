---
icon: fas fa-gamepad
title: MoodSwings
permalink: /moodswings/
order: 2
description: >-
  MoodSwings by Bastian Machek (Fokuspunk): an open-source comedy sandbox with
  bouncing citizens, contagious moods and a playful version of Landshut.
image: /assets/img/moodswings/altstadt.png
project_schema: moodswings
faq:
  - q: What is MoodSwings?
    a: "MoodSwings, also called Mood Swings — Die Stadt der Flummis, is an open-source comedy sandbox by Bastian Machek (Fokuspunk). Explore a city of bouncing citizens whose moods spread through the crowd."
  - q: Is MoodSwings a mood tracker?
    a: "No. MoodSwings by Bastian Machek is a game. Mood is its central gameplay mechanic: taunts, cheers and collisions change how the city's inhabitants feel and react."
  - q: What does MoodSwings have to do with Landshut?
    a: "The Landshüpf city variant uses Landshut's street network from OpenStreetMap, building footprints from Overture Maps and terrain based on Copernicus elevation data. Other city styles are procedurally generated."
  - q: Can I play with other people?
    a: "An experimental multiplayer mode supports up to 16 players exploring on foot. It requires matching game revisions and a dedicated server on a trusted LAN or private VPN. Driving and save/load are disabled in this mode."
  - q: Is MoodSwings free, and where can I get it?
    a: "MoodSwings is free and open source under GPL-3.0-or-later. The source and build instructions are on GitHub at github.com/bmachek/MoodSwings. There are no packaged GitHub releases as of September 13, 2026."
---

<p class="project-kicker">Open-source game · Rust + Bevy · By Bastian Machek</p>

## A whole city. One very short fuse.

**MoodSwings — Die Stadt der Flummis** is my open-world comedy sandbox: a city where people bounce, cars bounce, and a bad mood can travel further than you intended. I'm [Bastian Machek, also known as Fokuspunk]({{ '/about-me/' | relative_url }}), and this is my venture from photography tools into a playable world with a temper.

Blow a raspberry at a stranger. Watch their expression change. Now watch their neighbour get involved. Or whistle, cheer someone up, and see how far a good mood carries. The fun is in the reactions you set off.

<p class="project-actions"><a class="btn btn-primary" href="https://github.com/bmachek/MoodSwings">Explore MoodSwings on GitHub</a> <a href="#try-moodswings">Build &amp; play</a></p>

<figure>
  <img src="{{ '/assets/img/moodswings/altstadt.png' | relative_url }}" alt="MoodSwings gameplay screenshot: pastel buildings, pedestrians and cobbled streets in Landshüpf's Altstadt" width="1600" height="900" fetchpriority="high">
  <figcaption>Landshüpf, the game's version of Landshut. Actual development screenshot, September 2026.</figcaption>
</figure>

## How the city catches a mood

Every citizen has a temperament and a mood. You can see it in their face and hear it in their reactions. Taunting makes people cross; cheering lifts their spirits. Bumps matter too: a gentle nudge can be a joke, a hard collision an insult.

Some residents shrug it off. Others hold a grudge and bounce after you. A collision can upset the next person, who passes that feeling on again. You can also throw a flower to apologise. The same rules run through the crowd, so the city can get itself into trouble without your help.

There are no weapons, health bars or failure state. You explore, drive, provoke, make peace, and watch what happens. Optional **Stadtmomente** give an outing a little direction — a walk, cheering different residents, or spending time near street music — without a countdown or penalty.

## Landshut, with a little more bounce

The **Landshüpf** city variant brings a real place into the sandbox. Its streets use map data © [OpenStreetMap contributors](https://www.openstreetmap.org/copyright), its mapped building footprints come from **Overture Maps**, and its terrain from **Copernicus elevation data**. The result is a playful interpretation of Landshut, with the Altstadt, the Isar and the hills around town shaping the world you explore.

Other styles, including **New Dork**, **Londoof**, **Minga** and **Paree**, tune the procedural city generator. Weather and a day/night cycle change the atmosphere while pedestrians and traffic keep the streets moving.

<figure>
  <img src="{{ '/assets/img/moodswings/altstadt-night.png' | relative_url }}" alt="Landshüpf in MoodSwings at night, with illuminated windows along the Altstadt" width="1600" height="900" loading="lazy" decoding="async">
  <figcaption>The same town after dark. The world has weather and a changing time of day.</figcaption>
</figure>

## Built in the open

MoodSwings is written in **Rust**, using the **Bevy** game engine and **Avian 3D** physics. City generation, elastic movement, character expressions and the mood simulation are part of the source. The project is licensed under **GPL-3.0-or-later**; asset and map credits are documented separately in the [project credits](https://github.com/bmachek/MoodSwings/blob/main/CREDITS.md).

The game supports keyboard/mouse and gamepad controls. Its menus and HUD are in German; development documentation is in English.

An **experimental multiplayer mode** lets up to 16 players explore together on foot. It needs matching game revisions and a dedicated server, intended for a trusted LAN or private VPN. It is more limited than solo play: vehicle entry and save/load are disabled. The [multiplayer documentation](https://github.com/bmachek/MoodSwings#multiplayer-shared-exploration) explains setup and current limitations.

## Try MoodSwings

**Development status, September 13, 2026:** the source is public and the game can be built locally. There are no packaged GitHub releases yet. Expect an evolving project, with rough edges and features that may change.

Start with the [README and build instructions](https://github.com/bmachek/MoodSwings#running). You need the Rust toolchain and the project's asset setup; the sound-bank download is required for audio. See the repository for current requirements rather than treating this overview as a version-specific installation guide.

Found something odd, or have an idea for the city? [Open an issue](https://github.com/bmachek/MoodSwings/issues) or read the [contribution guide](https://github.com/bmachek/MoodSwings/blob/main/CONTRIBUTING.md).

## Frequently asked questions

{% for item in page.faq %}
### {{ item.q }}

{{ item.a }}
{% endfor %}

## More from Fokuspunk

My other projects connect cameras, software and everyday life: [LrGeniusAI]({{ '/LrGeniusAI/' | relative_url }}) brings AI into Lightroom Classic, the [LR Immich Plugin]({{ '/lrc-immich-plugin/' | relative_url }}) connects Lightroom with self-hosted photo storage, and [CIDP Buddy]({{ '/cidp-buddy/' | relative_url }}) helps organise treatment routines.

[About Bastian Machek / Fokuspunk]({{ '/about-me/' | relative_url }}) · [All projects]({{ '/' | relative_url }})
