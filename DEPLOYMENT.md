# Deployment Guide for yueh-ai.github.io

This guide explains how to deploy your blog to https://yueh-ai.github.io/.

## Overview

Your blog is hosted on GitHub Pages using the repository `yueh-ai/yueh-ai.github.io`. GitHub Pages automatically serves static files from the main branch of repositories named `[username].github.io`.

## How It Works

1. **Repository Name**: The repository is named `yueh-ai.github.io`, which tells GitHub to serve it as a GitHub Pages site
2. **Automatic Deployment**: GitHub Pages automatically deploys any changes pushed to the main branch
3. **Static Files**: All HTML, CSS, and other static files in the repository are served directly
4. **Jekyll Support**: GitHub Pages has built-in Jekyll support - if you include a `_config.yml` file, it will automatically build your site with Jekyll

## Deployment Process

### Step 1: Stage Your Changes
```bash
git add .
```

### Step 2: Commit Your Changes
```bash
git commit -m "Update blog with new post"
```

### Step 3: Push to GitHub
```bash
git push origin main
```

### Step 4: Wait for Deployment
- GitHub Pages typically takes 1-10 minutes to deploy changes
- You can check the deployment status at: https://github.com/yueh-ai/yueh-ai.github.io/actions

## Current Blog Structure

```
blog/
├── index.html          # Homepage listing all blog posts
├── about.html          # About page
├── contact.html        # Contact page
├── style.css           # Main stylesheet
└── posts/              # Blog posts directory
    ├── post.css        # Post-specific styles
    └── *.html          # Individual blog posts
```

## Adding New Blog Posts

1. Create a new HTML file in the `posts/` directory
2. Update `index.html` to add a link to your new post
3. Follow the deployment process above

## Troubleshooting

### Changes Not Appearing
- Wait 10 minutes for GitHub Pages cache to update
- Try hard refresh in browser (Ctrl+F5 or Cmd+Shift+R)
- Check GitHub repository to ensure files were pushed correctly

### 404 Errors
- Ensure file paths in links are correct (relative paths)
- Check that files exist in the repository
- Remember URLs are case-sensitive

### Checking Deployment Status
Visit: https://github.com/yueh-ai/yueh-ai.github.io/settings/pages

## Quick Commands

Deploy all changes:
```bash
git add . && git commit -m "Update blog" && git push origin main
```

Check current status:
```bash
git status
```

View recent commits:
```bash
git log --oneline -5
```

## Using Jekyll (Optional)

Jekyll is a static site generator built into GitHub Pages. If you want to:
- Write posts in Markdown instead of HTML
- Use templates and layouts
- Have automatic post listing

See `JEKYLL_GUIDE.md` for detailed instructions.

### Quick Jekyll Setup
1. Add `_config.yml` to your repository
2. Create `_posts/` directory for blog posts
3. Write posts in Markdown with format: `YYYY-MM-DD-title.md`
4. Push to GitHub - it automatically builds with Jekyll

## Notes

- The site is available at https://yueh-ai.github.io/
- No build process is required - GitHub Pages serves the HTML files directly (or builds Jekyll automatically)
- Changes typically appear within 5-10 minutes of pushing
- Check build status at: https://github.com/yueh-ai/yueh-ai.github.io/actions