# Jekyll Guide for GitHub Pages

Jekyll is a static site generator that's built into GitHub Pages. It allows you to write blog posts in Markdown and use templates.

## What is Jekyll?

Jekyll is a Ruby-based static site generator that:
- Converts Markdown files to HTML automatically
- Supports templates and layouts
- Has built-in blog functionality
- Is integrated with GitHub Pages

## Current Setup vs Jekyll Setup

### Current Setup (Plain HTML)
- Write posts in HTML
- Manually update index.html for each new post
- No templating system

### Jekyll Setup
- Write posts in Markdown
- Automatic post listing
- Templating with layouts
- Variables and includes

## Converting to Jekyll

### 1. Create Jekyll Configuration

Create `_config.yml`:
```yaml
title: Yue Hu - Engineering & AI
description: Exploring the intersection of software engineering and artificial intelligence
url: https://yueh-ai.github.io
baseurl: ""

# Build settings
markdown: kramdown
theme: minima  # or another theme

# Exclude files from build
exclude:
  - DEPLOYMENT.md
  - JEKYLL_GUIDE.md
```

### 2. Create Directory Structure

```
blog/
├── _config.yml         # Jekyll configuration
├── _layouts/           # Page templates
│   ├── default.html
│   └── post.html
├── _posts/             # Blog posts (Markdown)
│   └── 2025-07-25-rethinking-evaluation.md
├── _includes/          # Reusable components
│   ├── header.html
│   └── footer.html
├── assets/             # CSS, JS, images
│   └── css/
│       └── style.css
├── index.md            # Homepage
└── about.md            # About page
```

### 3. Jekyll Commands

#### Install Jekyll Locally (Optional)
```bash
# Install Ruby first, then:
gem install bundler jekyll

# Create Gemfile
bundle init
bundle add jekyll
```

#### Run Jekyll Locally
```bash
# Serve site locally
bundle exec jekyll serve

# Build site
bundle exec jekyll build
```

### 4. Writing Posts in Jekyll

Create posts in `_posts/` with naming format: `YYYY-MM-DD-title.md`

Example: `_posts/2025-07-25-rethinking-evaluation.md`
```markdown
---
layout: post
title: "Rethinking Evaluation"
date: 2025-07-25
categories: ai engineering
---

When building AI agents, we jump straight to the code...
```

### 5. Jekyll with GitHub Pages

#### Option 1: Let GitHub Build (Recommended)
- Push Jekyll files to repository
- GitHub Pages automatically builds with Jekyll
- No local build needed

#### Option 2: Build Locally
- Build site locally: `jekyll build`
- Push only `_site/` contents
- Use `.nojekyll` file to disable GitHub's Jekyll

## Jekyll Features

### Front Matter
Every page/post starts with YAML front matter:
```yaml
---
layout: post
title: "My Post Title"
date: 2025-07-25
author: "Yue Hu"
categories: [ai, engineering]
tags: [evaluation, agents]
---
```

### Liquid Templating
Use variables and logic in templates:
```liquid
{% for post in site.posts %}
  <h2>{{ post.title }}</h2>
  <p>{{ post.date | date: "%B %d, %Y" }}</p>
{% endfor %}
```

### Automatic Features
- RSS feed generation
- Sitemap creation
- SEO tags
- Category/tag pages

## Migrating Current Blog to Jekyll

1. Move HTML files to appropriate Jekyll directories
2. Extract common elements to layouts
3. Convert posts to Markdown
4. Update configuration

## GitHub Pages Specifics

GitHub Pages uses:
- Jekyll 3.9.x (check current version)
- Limited set of plugins (see GitHub Pages gem)
- Specific themes available

### Supported Plugins
- jekyll-feed
- jekyll-seo-tag
- jekyll-sitemap
- jekyll-github-metadata

## Quick Start for Your Blog

To convert your current blog to Jekyll:

```bash
# 1. Create _config.yml (see above)

# 2. Create _posts directory
mkdir _posts

# 3. Move your markdown post
mv posts/why_you_should_focus_on_evaluation.md _posts/2025-07-25-rethinking-evaluation.md

# 4. Add front matter to the post

# 5. Create index.md instead of index.html

# 6. Push to GitHub
git add .
git commit -m "Convert to Jekyll"
git push origin main
```

## Checking Jekyll Build Status

Visit: https://github.com/yueh-ai/yueh-ai.github.io/settings/pages

Look for "Your site is published at https://yueh-ai.github.io/"

## Benefits of Using Jekyll

1. **Write in Markdown**: Easier than HTML
2. **Automatic Generation**: Post lists, RSS feeds, sitemaps
3. **Templating**: Reuse layouts and includes
4. **GitHub Integration**: Automatic building
5. **Local Preview**: Test changes before pushing

## Common Jekyll Commands

```bash
# Create new post
touch _posts/$(date +%Y-%m-%d)-my-new-post.md

# Serve locally with drafts
jekyll serve --drafts

# Build for production
JEKYLL_ENV=production jekyll build
```

## Resources

- [Jekyll Documentation](https://jekyllrb.com/)
- [GitHub Pages Documentation](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll)
- [Jekyll Themes](https://jekyllrb.com/docs/themes/)