---
icon: fas fa-robot
title: LrGeniusAI
permalink: /LrGeniusAI/
order: 3
description: >-
  LrGeniusAI by Bastian Machek: AI tagging, semantic search, faces, species
  identification and beta editing tools for Lightroom Classic. Local or cloud AI.
image: /assets/img/lrgenius/lrgenius-logo.png
project_schema: LrGeniusAI
faq:
  - q: "What is LrGeniusAI?"
    a: "LrGeniusAI is a Lightroom Classic plugin that uses Large Language Models (LLMs) to automatically tag and describe your photos, and lets you search your library with natural-language prompts. It ships built-in local AI (MLX on macOS, llama.cpp on Windows), and also supports Ollama, LM Studio, Google Gemini and ChatGPT/OpenAI."
  - q: "Does LrGeniusAI work with local AI models?"
    a: "Yes. LrGeniusAI runs vision models itself — MLX on macOS (Apple silicon) and llama.cpp on Windows — so no external app is required. It also supports Ollama and LM Studio, or cloud models such as Google Gemini and ChatGPT/OpenAI. Switch between local and cloud as needed."
  - q: "How does the semantic search in LrGeniusAI work?"
    a: "LrGeniusAI builds a vector index of your photos using SigLIP2 embeddings, stored in a local LanceDB database. Enter a natural-language description (e.g. 'red sports car parked in front of a garage') and the plugin returns a relevance-sorted Collection in Lightroom."
  - q: "Where can I download LrGeniusAI?"
    a: "Download LrGeniusAI from lrgenius.com or from the GitHub Releases page at github.com/LrGenius/LrGeniusAI/releases. Documentation and help are at lrgenius.com/help."
---



## AI tools for your Lightroom Classic library

![LrGenius Logo](/assets/img/lrgenius/lrgenius-logo.png){: width="80" .left }

**lrc-ai-assistant** has been replaced by **LrGeniusAI** — a smart Lightroom Classic plugin for AI-powered tagging, describing, and semantic image search.

[LrGeniusAI](https://lrgenius.com) brings modern Large Language Models (LLMs) into Adobe Lightroom Classic: it analyzes your photos, generates accurate tags and detailed descriptions, and lets you search your library with natural language. You can run local models for maximum privacy or use cloud APIs; the plugin fits into your workflow either way.

## Core features

- **AI Edit & style training (beta)** — Create Develop recipes from your own saved edits, with at least five training examples and per-photo review enabled by default. This workflow interpolates your examples rather than calling a language model.
- **Image culling (beta)** — Group bursts and near-duplicates, rank frames, and create collections for picks, alternates and reject candidates.

- **AI-powered tagging & describing** — LLMs recognize image content and generate metadata and detailed descriptions.
- **Semantic free-text search** — Find images by describing what you want (e.g. *"Red sports car parked in front of a garage"*). LrGeniusAI builds a relevance-sorted Collection in Lightroom from your prompt.
- **Built-in local AI** — The backend runs vision models itself: **MLX** on macOS (Apple silicon) and **llama.cpp** on Windows. Pick a model in the Plug-In Manager and click *Download* — no external app needed.
- **Local & cloud models** — Also works with **Ollama** and **LM Studio**, or cloud providers **Google Gemini** and **ChatGPT/OpenAI**.
- **People & faces** — Detect and cluster faces, name persons, browse person collections, and find similar faces across the catalog.
- **Species identification (on-device)** — Identify animals, plants and fungi down to the species with **BioCLIP 2**, running entirely on your machine.
- **Customizable prompts & temperature** — Edit system prompts and control creativity vs consistency in the Plug-In Manager.
- **Photo context** — Add hints (names, background details) in a dialog or in Lightroom’s metadata panel so the AI can use them.
- **Custom Rust backend** — A local server (`geniusai-server`) written in Rust for low memory overhead. Import existing catalog metadata before the first AI run.

## Tech stack

- **Plugin:** Lua (Lightroom Classic SDK)  
- **Backend:** Rust — `geniusai-server`, an [axum](https://github.com/tokio-rs/axum) HTTP service that runs locally alongside Lightroom  
- **Embeddings & semantic search:** SigLIP2 via ONNX Runtime  
- **Faces:** YuNet (detection) + FaceNet (embeddings), ONNX  
- **Species:** BioCLIP 2 (ONNX) with a pruned TreeOfLife taxonomy head  
- **Local inference:** MLX on macOS (Apple silicon, Metal helper process); llama.cpp compiled into the backend on Windows (GGUF, Vulkan)  
- **Database:** LanceDB  
- **Supported model providers:** built-in MLX (macOS), built-in llama.cpp (Windows), Google Gemini, ChatGPT/OpenAI, Ollama, LM Studio  
- **License:** AGPL-3.0

> The backend used to be a Python/Flask server; it was rewritten in Rust and now lives in the
> [LrGeniusAI repository](https://github.com/LrGenius/LrGeniusAI) under `server-rs/`. The old
> `geniusai-server` repository is archived. **Google Vertex AI support was removed in August 2026.**
{: .prompt-info }

## Get it

- **Download:** [GitHub Releases](https://github.com/LrGenius/LrGeniusAI/releases)  
- **Website & help:** [lrgenius.com](https://lrgenius.com) · [lrgenius.com/help](https://lrgenius.com/help/)  
- **Source:** [github.com/LrGenius](https://github.com/LrGenius) (LrGeniusAI, LrGeniusTagAI)

## Frequently asked questions

{% for item in page.faq %}
### {{ item.q }}

{{ item.a }}
{% endfor %}

{% include project-author.html %}
