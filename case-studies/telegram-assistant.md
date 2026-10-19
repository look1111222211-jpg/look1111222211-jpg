# Telegram assistant — FAQ, AI answers and image generation

**Type:** Independent demo/training project.

## Why I built it

A small assistant can put common answers and selected AI actions in one familiar chat interface. I wanted simple requests to have a predictable route and generation failures to produce clear feedback.

## What I built

A 13-node n8n workflow routes messages to predefined FAQ answers, AI text responses, or image generation. FAQ replies in Ukrainian and English can return without an AI API call. Text generation uses GPT-4o mini. Image commands select a portrait Instagram format or landscape Facebook format, generate an image and return it to Telegram. Typing indicators and image-error fallbacks support the chat experience.

**Flow:** Telegram message → request routing → FAQ / AI text / generated image → reply in the same chat.

## Why this approach

Known FAQs do not need a model call. Separate generation routes make their inputs and outputs easier to inspect. Explicit image dimensions produce the intended output format without an extra manual resize step.

## Implementation and demonstration evidence

- 13 nodes in the implemented workflow.
- Two generated image formats: 1024×1536 portrait and 1536×1024 landscape.
- The recorded demo shows real generated images delivered in Telegram.
- Typing and image-error branches are present in the workflow.

These are implementation and demo checks, not a measured customer-support improvement.

## Current limits

This demo does not include inbound image understanding, a knowledge-base retrieval system, voice processing or conversational memory. Its image feature generates new images from prompts. Broader knowledge and account integrations would be separate additions.

## What I learned

A small bot is easier to explain and test when each supported request has a clear route. Predictable FAQ responses and visible failure messages are useful alongside AI generation.

**Tools:** n8n, Telegram Bot API, OpenAI, GPT-4o mini, GPT Image 1 Mini, JavaScript.

[Workflow walkthrough](https://www.loom.com/share/9474b7fe28b64340b0fed43bc34c9890) · [Full portfolio](https://nova-slice-e68.notion.site/Vadym-Dudka-3b7f35dfa98a80d485cfdf6ecab41b67)
