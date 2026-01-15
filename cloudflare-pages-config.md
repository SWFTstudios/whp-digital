# Cloudflare Pages Configuration

## Issue
The deployment is failing because:
1. `videos/datacenterwithwater.mp4` is exactly 25MB (Cloudflare Pages limit)
2. Total project size is 766MB (very large for Pages)

## Solutions

### Option 1: Compress Large Videos (Recommended)
Compress videos that are at or near the 25MB limit:
- `datacenterwithwater.mp4` (25MB) - needs compression

### Option 2: Use Cloudflare Stream
Host large videos on Cloudflare Stream and embed them in your HTML.

### Option 3: External Video Hosting
Use services like:
- Cloudflare Stream
- Vimeo
- YouTube (unlisted)
- AWS S3 + CloudFront

## Cloudflare Pages Setup

1. Go to Cloudflare Dashboard → Workers & Pages
2. Click "Create application" → "Pages" → "Connect to Git"
3. Select your GitHub repository: `SWFTstudios/whp-digital`
4. Build settings:
   - **Framework preset**: None
   - **Build command**: (leave empty - it's a static site)
   - **Build output directory**: `/` (root)
   - **Root directory**: `/` (root)

5. Click "Save and Deploy"

## Notes
- Cloudflare Pages is for static sites (HTML, CSS, JS) - perfect for your Webflow export
- No Workers needed - this is a simple static site
- Individual files must be < 25MB
- Total deployment should ideally be < 500MB for best performance
