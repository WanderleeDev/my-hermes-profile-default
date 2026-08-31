# Agnes AI Integration Setup

## Required Environment Variables

Create `~/.hermes/.env` with these values:

```bash
# Agnes AI API Key (required)
AGNES_API_KEY=your_api_key_here

# Cloudflare R2 Credentials (required for storage)
R2_ACCOUNT_ID=your_account_id_here
R2_ACCESS_KEY_ID=your_access_key_here
R2_SECRET_ACCESS_KEY=your_secret_key_here

# Optional (with defaults)
R2_IMAGE_BUCKET=hermes-image-db
R2_VIDEO_BUCKET=hermes-video-db
R2_IMAGE_DOMAIN=media.wanderlee.site
R2_VIDEO_DOMAIN=video.wanderlee.site
```

## Getting Your Keys

| Variable | Where to Get |
|----------|--------------|
| `AGNES_API_KEY` | https://apihub.agnes-ai.com |
| `R2_ACCOUNT_ID` | Cloudflare Dashboard → R2 → Account Settings |
| `R2_ACCESS_KEY_ID` | Cloudflare Dashboard → R2 → API Tokens |
| `R2_SECRET_ACCESS_KEY` | Cloudflare Dashboard → R2 → API Tokens |

## R2 Bucket Setup

### 1. Create Buckets
In Cloudflare Dashboard → R2 → Create Bucket:
- `hermes-image-db` (for images)
- `hermes-video-db` (for videos)

### 2. Create API Token
R2 → API Tokens → Create Token:
- Name: `hermes-agent`
- Scope: Both buckets
- Permission: `Read & Write`

### 3. (Optional) Custom Domains
Add CNAME records in Cloudflare DNS:
```
media.wanderlee.site → pub-xxx.r2.dev
video.wanderlee.site → pub-xxx.r2.dev
```

## Usage

Once configured:

```bash
# Generate image
/imagine a cyberpunk city

# Generate video from image
Animate image https://media.wanderlee.site/image.png for 10 seconds
```

## Files in This Export

- `config.yaml` - Agent configuration with ${AGNES_API_KEY}
- `plugins/image_gen/agnes/` - Image generation plugin
- `plugins/video_gen/agnes/` - Video generation plugin
- `skills/mlops/agnes-image-integration/` - Image skill
- `skills/mlops/agnes-video-integration/` - Video skill
- `skills/mlops/agnes-r2-storage/` - R2 storage skill
