---
name: morphix
description: Generate images, video and speech audio, or upscale images and video, with the Morphix MCP server. Use when the user asks to create, edit, animate, narrate or upscale visual or audio content, or to find something they generated before.
---

# Morphix

Morphix runs image, video and audio models behind one account. Every generation spends credits from that account.

## Before a paid generation

1. Call `get_account` to see the remaining credits.
2. Call `explore_models` and pick a model that fits the request (type, quality, speed, aspect ratio, reference image support). Use the model the user names if they name one.

## Reference files

Inputs such as reference images must live in the user's Morphix library.

- Reuse what is already there with `get_assets`.
- A file you can read (for example one attached in Slack or saved on your computer): call `get_upload_url`, send the bytes to that URL with an HTTP PUT, then call `confirm_upload`. Use `upload_asset` when the file is already at a public URL.
- `show_upload_widget` only works in chat clients that render widgets. Skip it when you run headless.

## Generating

- Images: `generate_image`. Video: `generate_video`. Speech: `generate_audio`.
- Bigger or sharper only: `upscale_image` or `upscale_video`.
- Generations run asynchronously. Check progress with `get_generations` and share the output URL once it is ready.
- Every result is saved to the user's Morphix library, so `get_generations` also finds past work.

## Good habits

- Restate what you are about to generate and which model you picked before spending credits on video.
