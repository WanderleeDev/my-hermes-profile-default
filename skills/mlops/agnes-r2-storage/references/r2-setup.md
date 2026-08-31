# R2 Setup Guide

## Buckets
- `hermes-image-db` → media.wanderlee.site
- `hermes-video-db` → video.wanderlee.site

## Credentials (create your own in ~/.hermes/.env)
```
R2_ACCOUNT_ID=your_account_id_here
R2_ACCESS_KEY_ID=your_access_key_here
R2_SECRET_ACCESS_KEY=your_secret_key_here
```

## Public URL Format
```
https://media.yourdomain.com/images/<key>
https://video.yourdomain.com/videos/<key>
```

## Free Tier
- 10 GB storage/month (per account, not per bucket)
- 1M writes/month
- 10M reads/month
- Unlimited egress (FREE)

## Plugin Behavior
- Image plugin: uses Agnes CDN URL directly (~1h TTL)
- Image plugin + `storage="r2"`: downloads + uploads to R2 for permanent URL
- Video plugin: uploads to R2 on completion
