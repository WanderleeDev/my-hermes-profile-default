# My Hermes — Default Profile

General purpose Hermes profile with Agnes AI image/video generation and GitHub MCP.

## What's Included

- **Agnes AI Integration**: Image generation (agnes-image-2.1-flash) and video generation (agnes-video-2.5-flash)
- **GitHub MCP**: Native GitHub tools (issues, PRs, code review)
- **GitHub Skills**: Auth, PR workflow, issues, repo management
- **Cloudflare R2 Storage**: Permanent public URLs with custom domains
- **Custom Plugins**: `image_gen/agnes` and `video_gen/agnes`

## Quick Install

```bash
hermes profile install github.com/WanderleeDev/my-hermes-profile-default --alias
```

Then fill in your `.env`:
```bash
cp .env.example .env
# Edit .env with your API keys
```

## Requirements

- Hermes Agent >= 0.12.0
- Agnes AI API key (https://agnes-ai.com)
- OpenRouter API key (https://openrouter.ai)
- Cloudflare account with R2 enabled (optional)

## Author

WanderleeDev

## License

MIT
