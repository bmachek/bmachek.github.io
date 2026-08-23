---
icon: fas fa-robot
title: LrGeniusAI
permalink: /LrGeniusAI/
order: 3
description: >-
  LrGeniusAI is an AI-powered Lightroom Classic plugin for automatic photo tagging,
  image descriptions, face recognition, species identification, and semantic
  natural-language search — with built-in local AI (MLX on macOS, llama.cpp on Windows)
  or cloud models (Gemini, OpenAI).
---

<!-- SoftwareApplication + FAQ structured data for rich results -->
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@type": "SoftwareApplication",
      "name": "LrGeniusAI",
      "operatingSystem": "Windows, macOS",
      "applicationCategory": "MultimediaApplication",
      "description": "AI-powered Lightroom Classic plugin that uses Large Language Models to tag and describe photos, recognises faces, identifies species on-device, and enables semantic natural-language search across your library.",
      "url": "https://blog.fokuspunk.de/LrGeniusAI/",
      "sameAs": "https://lrgenius.com",
      "downloadUrl": "https://github.com/LrGenius/LrGeniusAI/releases",
      "softwareHelp": "https://lrgenius.com/help/",
      "author": { "@type": "Person", "@id": "https://blog.fokuspunk.de/#person", "name": "Bastian Machek" },
      "offers": { "@type": "Offer", "price": "0", "priceCurrency": "USD" }
    },
    {
      "@type": "FAQPage",
      "mainEntity": [
        {
          "@type": "Question",
          "name": "What is LrGeniusAI?",
          "acceptedAnswer": { "@type": "Answer", "text": "LrGeniusAI is a Lightroom Classic plugin that uses Large Language Models (LLMs) to automatically tag and describe your photos, and lets you search your library with natural-language prompts. It ships built-in local AI (MLX on macOS, llama.cpp on Windows), and also supports Ollama, LM Studio, Google Gemini and ChatGPT/OpenAI." }
        },
        {
          "@type": "Question",
          "name": "Does LrGeniusAI work with local AI models?",
          "acceptedAnswer": { "@type": "Answer", "text": "Yes. LrGeniusAI runs vision models itself — MLX on macOS (Apple silicon) and llama.cpp on Windows — so no external app is required. It also supports Ollama and LM Studio, or cloud models such as Google Gemini and ChatGPT/OpenAI. Switch between local and cloud as needed." }
        },
        {
          "@type": "Question",
          "name": "How does the semantic search in LrGeniusAI work?",
          "acceptedAnswer": { "@type": "Answer", "text": "LrGeniusAI builds a vector index of your photos using SigLIP2 embeddings, stored in a local LanceDB database. Enter a natural-language description (e.g. 'red sports car parked in front of a garage') and the plugin returns a relevance-sorted Collection in Lightroom." }
        },
        {
          "@type": "Question",
          "name": "Where can I download LrGeniusAI?",
          "acceptedAnswer": { "@type": "Answer", "text": "Download LrGeniusAI from lrgenius.com or from the GitHub Releases page at github.com/LrGenius/LrGeniusAI/releases. Documentation and help are at lrgenius.com/help." }
        }
      ]
    }
  ]
}
</script>

## LrGeniusAI

![LrGenius Logo](/assets/img/lrgenius/lrgenius-logo.png){: width="80" .left }

**lrc-ai-assistant** has been replaced by **LrGeniusAI** — a smart Lightroom Classic plugin for AI-powered tagging, describing, and semantic image search.

[LrGeniusAI](https://lrgenius.com) brings modern Large Language Models (LLMs) into Adobe Lightroom Classic: it analyzes your photos, generates accurate tags and detailed descriptions, and lets you search your library with natural language. You can run local models for maximum privacy or use cloud APIs; the plugin fits into your workflow either way.

### Core features

- **AI-powered tagging & describing** — LLMs recognize image content and generate metadata and detailed descriptions.
- **Semantic free-text search** — Find images by describing what you want (e.g. *"Red sports car parked in front of a garage"*). LrGeniusAI builds a relevance-sorted Collection in Lightroom from your prompt.
- **Built-in local AI** — The backend runs vision models itself: **MLX** on macOS (Apple silicon) and **llama.cpp** on Windows. Pick a model in the Plug-In Manager and click *Download* — no external app needed.
- **Local & cloud models** — Also works with **Ollama** and **LM Studio**, or cloud providers **Google Gemini** and **ChatGPT/OpenAI**.
- **People & faces** — Detect and cluster faces, name persons, browse person collections, and find similar faces across the catalog.
- **Species identification (on-device)** — Identify animals, plants and fungi down to the species with **BioCLIP 2**, running entirely on your machine.
- **Customizable prompts & temperature** — Edit system prompts and control creativity vs consistency in the Plug-In Manager.
- **Photo context** — Add hints (names, background details) in a dialog or in Lightroom’s metadata panel so the AI can use them.
- **Custom Rust backend** — A local server (`geniusai-server`) written in Rust for low memory overhead. Import existing catalog metadata before the first AI run.

### Tech stack

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

### Get it

- **Download:** [GitHub Releases](https://github.com/LrGenius/LrGeniusAI/releases)  
- **Website & help:** [lrgenius.com](https://lrgenius.com) · [lrgenius.com/help](https://lrgenius.com/help/)  
- **Source:** [github.com/LrGenius](https://github.com/LrGenius) (LrGeniusAI, LrGeniusTagAI)

### Frequently asked questions

**What is LrGeniusAI?**

LrGeniusAI is a Lightroom Classic plugin that uses Large Language Models (LLMs) to automatically tag and describe your photos, and lets you search your library with natural-language prompts. It ships built-in local AI (MLX on macOS, llama.cpp on Windows), and also supports Ollama, LM Studio, Google Gemini and ChatGPT/OpenAI.

**Does LrGeniusAI work with local AI models?**

Yes. LrGeniusAI runs vision models itself — **MLX** on macOS (Apple silicon) and **llama.cpp** on Windows — so no external app is required for fully local, private processing. It also supports Ollama and LM Studio, or cloud models such as Google Gemini and ChatGPT/OpenAI.

**How does the semantic search work?**

LrGeniusAI builds a vector index of your photos using **SigLIP2** embeddings, stored in a local **LanceDB** database. Enter a natural-language description (e.g. *"red sports car parked in front of a garage"*) and the plugin returns a relevance-sorted Collection in Lightroom Classic.

**Where can I download LrGeniusAI?**

Download from [lrgenius.com](https://lrgenius.com) or the [GitHub Releases page](https://github.com/LrGenius/LrGeniusAI/releases). Documentation and help are at [lrgenius.com/help](https://lrgenius.com/help).