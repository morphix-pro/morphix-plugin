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

Inputs such as reference images must already be in the user's Morphix library.

- Find them with `get_assets`, which lists uploads and past generation outputs, newest first. Pass the asset ids to the generate and upscale tools.
- When the user wants to add their own file, call `show_upload_widget`. It returns the new asset id once the upload finishes.
- If your client cannot render the widget, ask the user to upload the file in the Morphix app at https://morphix.pro, then find it with `get_assets`.
- `get_upload_url`, `confirm_upload` and `upload_asset` are internal to the upload widget. Do not call them directly.

## Generating

- Images: `generate_image`. Video: `generate_video`. Speech: `generate_audio`.
- Bigger or sharper only: `upscale_image` or `upscale_video`.
- Generations run asynchronously. Check progress with `get_generations` using the generation id, and share the output URL once it is ready.
- Every result is saved to the user's Morphix library, so `get_assets` also finds past work.

## Good habits

- Restate what you are about to generate and which model you picked before spending credits on video.
