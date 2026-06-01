---
icon: fas fa-robot
title: LrGeniusAI
permalink: /LrGeniusAI/
order: 3
description: >-
  LrGeniusAI is an AI-powered Lightroom Classic plugin for automatic photo tagging,
  image descriptions, and semantic natural-language search using local (Ollama, LM Studio)
  or cloud (Gemini, Vertex AI) models.
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
      "description": "AI-powered Lightroom Classic plugin that uses Large Language Models to tag and describe photos and enables semantic natural-language search across your library.",
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
          "acceptedAnswer": { "@type": "Answer", "text": "LrGeniusAI is a Lightroom Classic plugin that uses Large Language Models (LLMs) to automatically tag and describe your photos, and lets you search your library with natural-language prompts. It supports local models via Ollama and LM Studio, and cloud models including Google Gemini and Vertex AI." }
        },
        {
          "@type": "Question",
          "name": "Does LrGeniusAI work with local AI models?",
          "acceptedAnswer": { "@type": "Answer", "text": "Yes. LrGeniusAI supports Ollama and LM Studio for fully local, private AI processing. You can also use cloud models such as Google Gemini and Vertex AI, or switch between local and cloud as needed." }
        },
        {
          "@type": "Question",
          "name": "How does the semantic search in LrGeniusAI work?",
          "acceptedAnswer": { "@type": "Answer", "text": "LrGeniusAI builds a vector index of your photos using Open-CLIP embeddings. Enter a natural-language description (e.g. 'red sports car parked in front of a garage') and the plugin returns a relevance-sorted Collection in Lightroom." }
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

### Frequently asked questions

**What is LrGeniusAI?**

LrGeniusAI is a Lightroom Classic plugin that uses Large Language Models (LLMs) to automatically tag and describe your photos, and lets you search your library with natural-language prompts. It supports local models via Ollama and LM Studio, and cloud models including Google Gemini and Vertex AI.

**Does LrGeniusAI work with local AI models?**

Yes. LrGeniusAI supports Ollama and LM Studio for fully local, private AI processing. You can also use cloud models such as Google Gemini and Vertex AI, or switch between local and cloud as needed.

**How does the semantic search work?**

LrGeniusAI builds a vector index of your photos using Open-CLIP embeddings. Enter a natural-language description (e.g. *"red sports car parked in front of a garage"*) and the plugin returns a relevance-sorted Collection in Lightroom Classic.

**Where can I download LrGeniusAI?**

Download from [lrgenius.com](https://lrgenius.com) or the [GitHub Releases page](https://github.com/LrGenius/LrGeniusAI/releases). Documentation and help are at [lrgenius.com/help](https://lrgenius.com/help).