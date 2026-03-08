---
icon: fas fa-robot
title: LrGeniusAI
permalink: /LrGeniusAI/
order: 3
---

## LrGeniusAI

**lrc-ai-assistant** has been replaced by **LrGeniusAI** — a smart Lightroom Classic plugin for AI-powered tagging, describing, and semantic image search.

[LrGeniusAI](https://lrgenius.com) brings modern Large Language Models (LLMs) into Adobe Lightroom Classic: it analyzes your photos, generates accurate tags and detailed descriptions, and lets you search your library with natural language. You can run local models for maximum privacy or use cloud APIs; the plugin fits into your workflow either way.

### Core features

- **AI-powered tagging & describing** — LLMs recognize image content and generate metadata and detailed descriptions.
- **Semantic free-text search** — Find images by describing what you want (e.g. *"Red sports car parked in front of a garage"*). LrGeniusAI builds a relevance-sorted Collection in Lightroom from your prompt.
- **Local & cloud models** — **Ollama** and **LM Studio** for local AI; **Google Gemini** and **Vertex AI** for cloud. Switch as needed.
- **Customizable prompts & temperature** — Edit system prompts and control creativity vs consistency in the Plug-In Manager.
- **Photo context** — Add hints (names, background details) in a dialog or in Lightroom’s metadata panel so the AI can use them.
- **Custom Python backend** — Uses a local server (geniusai-server) you can import existing catalog metadata before the first AI run.

### Tech stack

- **Plugin:** Lua  
- **Backend:** Python ([geniusai-server](https://github.com/LrGenius/geniusai-server))  
- **AI & embeddings:** Open-CLIP  
- **Supported:** Gemini, Vertex AI, Ollama, LM Studio, OpenAI

### Get it

- **Download:** [GitHub Releases](https://github.com/LrGenius/LrGeniusAI/releases)  
- **Website & help:** [lrgenius.com](https://lrgenius.com) · [lrgenius.com/help](https://lrgenius.com/help/)  
- **Source:** [github.com/LrGenius](https://github.com/LrGenius) (LrGeniusAI, LrGeniusTagAI)