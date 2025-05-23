---
layout: post
title:   "Version 3.7.0: Supported for multiple prompts"
date:   2025-05-19 07:00:00 +0200
tags: lrc-ai-assistant
---
### General improvements
* Support for saving multiple prompts, for different genres of photography/use cases.
* Keywords hierarchy is now optional. The top level keyword can be removed, as well as disabling to the whole hierarchy thing.

### Ollama
* Move to the chat API endpoint, which should slightly improve performance due to prompt caching.
* Possibility to use another host for Ollama not only localhost. (See Ollama base URL).

### LM Studio
* There's experimental support for LM Studio as LLM backend. Not activated by default, yet.

### Wiki
There's going to be more documentation going in the [GitHub Wiki](https://github.com/bmachek/lrc-ai-assistant/wiki)

