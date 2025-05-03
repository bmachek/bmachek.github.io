---
layout: post
title:   "Enhanced Ollama support / New features"
date:   2025-05-03 09:00:00 +0200
tags: lrc-ai-assistant
---
## Ollama

### List of local installed Ollama models
The list was previously hardcoded as configuration into lrc-ai-assistant.
From now on it does an API call to the local Ollama instance, querying for the installed models.
So every model you have locally pulled in your Ollama is now selectable in the plugin's GUI.

### Temperature
Submitting a temperature to the selected AI model is now supported.
**Setting it to *"be coherent"* massively improves the results of Ollama models!**

### Custom AI related fields in Lightroom catalog
I introduced some new fields to Lightroom via Metadata extension.
This way the plugin stores it last run and used model for every picture.
Additionally the user-given context for a photo is saved and can be edited from the Library module of Lightroom.

### New prompts
There is a new default prompt and system instruction included with the release.
If you want to try them, go to the plugin manager and hit the "Defaults" button beneath task and system instruction.
The new prompts aren't translated anymore. 
So by default all results are in english, however if you want your results in a different language.
Just add something like "All results should be generated in German." e.g. to the bottom of your task in the settings.

### Focus on Ollama
Since the results with Ollama are getting better and better, the focus will intensify more and more on Ollama in the future.

## Want to be a part of lrc-ai-assistant
I'm way behind on docs and translations. 
**Is anyone interested in becoming a partner in this project?**