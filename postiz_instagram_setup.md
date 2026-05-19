# Postiz Instagram Setup — Step-by-Step

## What You Need to Do at developers.facebook.com

### Step 1: Create Meta App
1. Go to https://developers.facebook.com/apps/
2. Click "Create App"
3. Select **"Business"** type (required for Instagram)
4. App name: "Postiz Scheduler" (or whatever)
5. Business portfolio: select/create one
6. Click "Create"

### Step 2: Add Instagram Product
1. In your new app dashboard, click "Add Product"
2. Find **Instagram** → Click "Set Up"
3. Choose **"API Setup with Instagram Login"** (standalone, no Facebook page needed)
4. OR choose "API setup with Facebook login" if your IG is linked to a FB page

### Step 3: Configure OAuth Redirect URI
1. Go to Settings → Basic
2. Scroll to "App Domains" → Add `localhost`
3. Go to Products → Instagram → Settings
4. Add Valid OAuth Redirect URIs:
   - `http://localhost:4007/integrations/social/facebook`
5. Save changes

### Step 4: Set App to Live Mode
1. Top toggle: switch from "Development" to **"Live"**
2. Confirm business verification if prompted (for personal use, basic verification is enough)

### Step 5: Get Credentials
1. Settings → Basic
2. Copy **App ID** and **App Secret**
3. Paste them below:

```
FACEBOOK_APP_ID=     <<< paste here
FACEBOOK_APP_SECRET= <<< paste here
```

### Step 6: Connect in Postiz
1. Restart Postiz with new env vars: `docker compose down && docker compose up -d`
2. Open http://localhost:4007
3. Go to Settings → Channels → Add Instagram
4. Authorize → should work now!

## Important Notes
- Instagram and Facebook share the same App ID/Secret in Postiz
- For local use, you DON'T need business verification (just basic app review)
- If "API Setup with Instagram Login" doesn't appear, your Instagram account must be a **Professional/Creator** account, not personal
