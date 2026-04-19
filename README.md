# SR Product Designer & Communication Coach Portfolio

This is a static HTML website optimized for GitHub Pages hosting.

## Quick Start - Deploy to GitHub Pages

### Option 1: Using GitHub Web Interface (Easiest)

1. **Create a new GitHub repository**
   - Go to https://github.com/new
   - Name it: `username.github.io` (replace `username` with your GitHub username)
   - Make it Public
   - Click "Create repository"

2. **Upload files**
   - Click "Add file" → "Upload files"
   - Drag and drop all files from this folder (index.html, assets/, __manus__/, .nojekyll)
   - Commit changes

3. **Enable GitHub Pages**
   - Go to Settings → Pages
   - Source: Deploy from a branch
   - Branch: main
   - Folder: / (root)
   - Click Save

4. **Visit your site**
   - Your portfolio will be live at: `https://username.github.io`

### Option 2: Using Git Command Line

```bash
# Clone your repository
git clone https://github.com/username/username.github.io.git
cd username.github.io

# Copy all files from this folder into the repository
# (Copy index.html, assets/, __manus__/, .nojekyll)

# Commit and push
git add .
git commit -m "Add portfolio website"
git push origin main
```

### Option 3: Using Custom Domain

If you want to use a custom domain (e.g., yourname.com):

1. **Add CNAME file**
   - Create a file named `CNAME` (no extension)
   - Add your domain: `yourname.com`
   - Commit and push

2. **Update DNS**
   - Go to your domain registrar
   - Add DNS records pointing to GitHub Pages:
     - Type A records: 185.199.108.153, 185.199.109.153, 185.199.110.153, 185.199.111.153
     - Or CNAME record: `username.github.io`

3. **Enable HTTPS**
   - Go to Settings → Pages
   - Check "Enforce HTTPS"

## File Structure

```
.
├── index.html           # Main website (single-page app)
├── assets/              # CSS and JavaScript bundles
├── __manus__/           # Analytics configuration
├── .nojekyll            # Tells GitHub to skip Jekyll processing
└── README.md            # This file
```

## Features

- **Responsive Design**: Works on desktop, tablet, and mobile
- **Fast Loading**: Pre-optimized and minified assets
- **No Build Required**: Just upload and it works
- **SEO Ready**: Proper meta tags and structure

## Customization

To edit content, you'll need to rebuild the website from source. The HTML file is minified and contains the entire application.

For updates:
1. Modify source files in the original project
2. Run `pnpm build`
3. Copy new files from `dist/public/` to your GitHub repository

## Troubleshooting

### Site not showing up
- Wait 5-10 minutes for GitHub to build and deploy
- Check that repository is public
- Verify Settings → Pages shows "Your site is live"

### Styling looks broken
- Clear browser cache (Ctrl+Shift+Delete or Cmd+Shift+Delete)
- Check that `assets/` folder is uploaded correctly

### Custom domain not working
- Verify DNS records are correct
- Wait 24-48 hours for DNS propagation
- Check CNAME file exists and contains correct domain

## Support

For GitHub Pages help: https://docs.github.com/en/pages
For portfolio updates: Rebuild from source and re-upload files

---

**Ready to go live?** Follow Option 1 above to deploy in minutes!
