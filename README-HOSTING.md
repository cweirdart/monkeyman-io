# MonkeyMan.io — Free Hosting Setup Guide

## Option A: GitHub Pages (Recommended — Free Forever)

### Step 1: Create the GitHub repo
1. Go to https://github.com/new
2. Name the repo `monkeyman.io` (or whatever you like)
3. Make it **Public** (required for free GitHub Pages)
4. Click **Create repository**

### Step 2: Upload the files
Upload these files from this folder to the repo:
- `index.html`
- `CNAME`
- Any images you add later (photos, etc.)

You can drag-and-drop them right into GitHub, or use git:
```bash
cd "MonkeyMan web 2026"
git init
git add .
git commit -m "Initial MonkeyMan site"
git remote add origin https://github.com/YOUR_USERNAME/monkeyman.io.git
git branch -M main
git push -u origin main
```

### Step 3: Enable GitHub Pages
1. Go to repo **Settings → Pages**
2. Under "Source", select **Deploy from a branch**
3. Branch: **main**, folder: **/ (root)**
4. Click **Save**

### Step 4: Point monkeyman.io to GitHub Pages
In your domain registrar (wherever you bought monkeyman.io), set these DNS records:

**A Records** (point to GitHub Pages IPs):
```
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```

**CNAME Record** (for www subdomain):
```
www → YOUR_USERNAME.github.io
```

### Step 5: Enable HTTPS
1. Back in repo **Settings → Pages**
2. Check **Enforce HTTPS** (may take a few minutes to appear after DNS propagates)

DNS can take up to 48 hours to fully propagate, but usually works within 30 minutes.

---

## Option B: Cloudflare Pages (Also Free)

1. Go to https://pages.cloudflare.com
2. Connect your GitHub repo
3. Deploy — it auto-builds on every push
4. Add custom domain `monkeyman.io` in Cloudflare dashboard

Both options are 100% free with no bandwidth limits for static sites.

---

## Adding Photos Later
Replace the placeholder `<div class="photo-placeholder">` elements in `index.html` with actual `<img>` tags:
```html
<div class="gallery-item"><img src="photo1.jpg" alt="MonkeyMan live" loading="lazy"></div>
```
Drop the image files in the same folder as index.html.

## Reminders
- Tell MonkeyMan to update his SoundCloud URL from `user-874682525` to a custom one!
- The booking button currently links to itsdjmonkeyman@gmail.com (from his EPK)
