# GitHub Pages Deployment Guide

## Files Included

- `index.html` - Main single-page application (includes all pages: Home, About, Shop, Case Studies)
- `assets/` - CSS and JavaScript bundles
- `__manus__/` - Analytics configuration
- `404.html` - Critical file for routing (handles About, Shop, and all internal navigation)
- `.nojekyll` - Tells GitHub to skip Jekyll processing
- `DEPLOYMENT.md` - This file

## Important: All Pages Are in One HTML File

This is a **single-page application**. All pages (Home, About, Shop, Case Studies) are included in `index.html`. The `404.html` file is essential for routing to work properly on GitHub Pages.

## Deployment Steps

### Step 1: Create GitHub Repository

1. Go to https://github.com/new
2. **Important**: Name it `username.github.io` (replace `username` with your GitHub username)
   - Example: `john-smith.github.io`
3. Make it **Public**
4. Click "Create repository"

### Step 2: Upload Files

**Option A: Using GitHub Web Interface (Easiest)**
1. Click "Add file" → "Upload files"
2. Drag and drop ALL files:
   - `index.html`
   - `404.html`
   - `.nojekyll`
   - `assets/` folder (all files inside)
   - `__manus__/` folder (all files inside)
3. Write commit message: "Initial portfolio upload"
4. Click "Commit changes"

**Option B: Using Git Command Line**
```bash
# Clone your repository
git clone https://github.com/username/username.github.io.git
cd username.github.io

# Copy all files here:
# - index.html
# - 404.html
# - .nojekyll
# - assets/ (folder)
# - __manus__/ (folder)

# Commit and push
git add .
git commit -m "Initial portfolio upload"
git push origin main
```

### Step 3: Enable GitHub Pages

1. Go to your repository
2. Click **Settings** (top menu)
3. Click **Pages** (left sidebar)
4. Under "Build and deployment":
   - Source: **Deploy from a branch**
   - Branch: **main**
   - Folder: **/ (root)**
5. Click **Save**

### Step 4: Wait for Deployment

1. Go back to **Settings** → **Pages**
2. You should see: "Your site is live at https://username.github.io"
3. Wait 2-5 minutes for the site to be fully deployed
4. Visit https://username.github.io

## Testing Navigation

Once deployed, test these links to verify everything works:

- Home: https://username.github.io
- About: https://username.github.io/about
- Shop: https://username.github.io/shop
- Case Study: https://username.github.io/case-study/project-1
- Contact Form: https://username.github.io/#contact

## Using a Custom Domain

If you want to use your own domain (e.g., yourname.com):

### 1. Add CNAME File

Create a file named `CNAME` (no extension) with just your domain:
```
yourname.com
```

Upload it to your repository.

### 2. Update DNS Records

Go to your domain registrar (GoDaddy, Namecheap, etc.) and add these DNS records:

**Option A: A Records (Recommended)**
```
Type: A
Name: @ (or leave blank)
Value: 185.199.108.153

Type: A
Name: @
Value: 185.199.109.153

Type: A
Name: @
Value: 185.199.110.153

Type: A
Name: @
Value: 185.199.111.153
```

**Option B: CNAME Record (Alternative)**
```
Type: CNAME
Name: www
Value: username.github.io
```

### 3. Enable HTTPS in GitHub

1. Go to **Settings** → **Pages**
2. Check "Enforce HTTPS"
3. Wait 5-10 minutes for the certificate to be issued

## Troubleshooting

### Site not showing up
- ✓ Wait 5-10 minutes for GitHub to deploy
- ✓ Check that repository is **Public**
- ✓ Verify Settings → Pages shows "Your site is live"
- ✓ Make sure you uploaded ALL files including `404.html`

### Pages not loading (About, Shop, etc.)
- ✓ Verify `404.html` is uploaded
- ✓ Clear browser cache (Ctrl+Shift+Delete)
- ✓ Try accessing directly: https://username.github.io/about

### Styling looks broken
- ✓ Clear browser cache
- ✓ Check that `assets/` folder is uploaded with all files inside
- ✓ Wait 5 minutes and refresh

### Custom domain not working
- ✓ Verify DNS records are correct
- ✓ Wait 24-48 hours for DNS propagation
- ✓ Check that `CNAME` file exists in repository
- ✓ Verify HTTPS is enabled in Settings → Pages

## File Structure After Upload

Your GitHub repository should have this structure:

```
username.github.io/
├── index.html
├── 404.html
├── .nojekyll
├── DEPLOYMENT.md
├── assets/
│   ├── index-UIElMlWw.css
│   └── index-D-zrTlQb.js
└── __manus__/
    ├── debug-collector.js
    └── version.json
```

## Updating Your Portfolio

To update content:

1. Modify source files in the original project
2. Run `pnpm build`
3. Copy new files from `dist/public/`:
   - `index.html`
   - `assets/` folder
4. Upload to GitHub repository
5. Commit changes

## Support

- GitHub Pages Docs: https://docs.github.com/en/pages
- GitHub Pages Troubleshooting: https://docs.github.com/en/pages/getting-started-with-github-pages/about-github-pages

---

**You're ready to deploy!** Follow the steps above to get your portfolio live in minutes.
