# Cloudflare Pages Setup Instructions

## Issue Fixed ✅
- Removed all large video files (>25MB) from the repository
- Latest commit (2cf8217) has no files over 25MB
- All `-transcode` video files are kept (they're all under 25MB and are what your HTML uses)

## Current Problem
Cloudflare Pages is deploying from the **old commit** (`005206b`) instead of the latest commit (`2cf8217`).

## Solution - Update Cloudflare Pages Configuration

### Option 1: Retrigger Deployment (Easiest)
1. Go to Cloudflare Dashboard → **Workers & Pages**
2. Click on your **whp-digital** project
3. Go to **Deployments** tab
4. Click **Retry deployment** or **Redeploy** on the latest deployment
5. Or click **Create deployment** → Select branch `main` → Deploy

### Option 2: Check Branch Configuration
1. Go to your project settings
2. Click **Settings** → **Builds & deployments**
3. Make sure **Production branch** is set to `main`
4. Make sure **Branch deployments** is enabled
5. Save and retrigger deployment

### Option 3: Reconnect Repository
1. Go to **Settings** → **Builds & deployments**
2. Scroll down to **Source**
3. Click **Disconnect** (if needed)
4. Click **Connect to Git** again
5. Select `SWFTstudios/whp-digital` repository
6. Select branch: `main`
7. Build settings:
   - **Framework preset**: None
   - **Build command**: (leave empty)
   - **Build output directory**: `/` (root directory)
   - **Root directory**: `/` (root directory)
8. Click **Save and Deploy**

## Verify Latest Commit
The latest commit on GitHub should be:
- **Commit**: `2cf8217` - "Remove large video files (>25MB) to fix Cloudflare Pages deployment"
- **Branch**: `main`

You can verify this at: https://github.com/SWFTstudios/whp-digital/commits/main

## After Deployment
Once Cloudflare deploys from the latest commit, the deployment should succeed because:
- ✅ No files over 25MB
- ✅ All video files used in HTML are `-transcode` versions (all under 25MB)
- ✅ Static site structure is correct for Cloudflare Pages
