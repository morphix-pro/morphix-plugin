# Morphix plugin

Generate AI images, videos and audio, and upscale images and videos up to 4K, right from your agent with [Morphix](https://morphix.pro).

One Morphix account and one credit balance cover every image, video and audio model.

## What it adds

- **MCP server** `morphix` at `https://mcp.morphix.pro/mcp` (streamable HTTP)
- **Skill** `morphix` that teaches the agent how to pick a model, use reference files from your library and follow a generation to the end

## Tools

| Tool | What it does |
| --- | --- |
| `get_account` | Plan and remaining credits |
| `explore_models` | Browse the model catalog |
| `generate_image` | Text to image and image editing |
| `generate_video` | Text to video and image to video |
| `generate_audio` | Text to speech |
| `upscale_image`, `upscale_video` | Upscale up to 4K |
| `get_generations` | Status of running generations and past results |
| `get_assets` | Files in your library |
| `show_upload_widget` | Add your own reference files to your library |

## Sign in

The first time the agent calls a tool you are asked to sign in with your Morphix account through OAuth. There is no API key to create or store. A free plan is available at [morphix.pro/pricing](https://morphix.pro/pricing).

## Claude Code

```bash
/plugin install morphix --marketplace morphix-pro/morphix-plugin
```

## Gemini CLI

```bash
gemini extensions install https://github.com/morphix-pro/morphix-plugin
```

## Other agents

The same server works in Claude, ChatGPT, Gemini CLI and any client that supports remote MCP. See [morphix.pro/mcp](https://morphix.pro/mcp).

## Support

support@morphix.pro · [Privacy](https://morphix.pro/legal/privacy-policy) · [Terms](https://morphix.pro/legal/terms-of-use)
