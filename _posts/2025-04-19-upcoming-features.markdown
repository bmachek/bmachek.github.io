---
layout: post
title:   "Upcoming features/changes in lrc-ai-assistant"
date:   2025-04-19 15:00:00 +0200
tags: lrc-ai-assistant
---
### Upcoming changes
#### Selection of AI models
In the next couple days maybe weeks, I want to rewrite the whole Lua code for the model selection in lrc-ai-assistant.
New models are released in a pretty short time manner as well for Ollama, as for the Google and OpenAI. 
At the moment the table of selectable models is hardcoded in the Defaults.lua, which makes it necessary to release a new version if something changes.
This obviously sucks, so I will rely on querying local Ollama, Google and OpenAI which models are currently available. 
I'm still unsure if a model pull function for Ollama should be part of the plugin, since this is a very time consuming task, I think this will be left a manual step.
#### Redesign of the prompts
For now the plugin heavily relies on the structured response that is submitted to the API, and not so much on sophisticated prompts which I now think is a disadvantage.
I think the generated results will get more usable and customizable when most of its structure and content is controlled by the prompt.

What are your thoughts on that?