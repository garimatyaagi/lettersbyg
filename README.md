# Letters by G – Writing Guide

This is the fast path for adding new posts and keeping the site updated.

## Quick Start (every new post)
- Create file in `_posts/` named `YYYY-MM-DD-title.md` (use today's date).
- Paste the front matter below, change title/date/excerpt/categories, then write.
- Run `bundle exec jekyll serve` to preview at `http://localhost:4000`; commit and push when happy.

### Front matter template
```markdown
---
layout: post
title: My Post Title
date: 2025-01-01
categories: [topic1, topic2]
tags: [favorite]        # optional: add "favorite" to show on homepage list
excerpt: "1–2 sentence summary for the homepage."
---
```

### Writing reminders
- Use Markdown for headings (`##`), lists, links, and quotes.
- Keep paragraphs short; first paragraph should hook the reader.
- Add links with `[text](/path)` or `[text]({{ "/posts/slug" | relative_url }})`.

## Preview locally
From the project root:
```bash
bundle exec jekyll serve
```
Site runs at `http://localhost:4000`; auto-refresh on save.

## Publish
GitHub Pages builds automatically from `main`.
```bash
git add .
git commit -m "Post: my-title"
git push origin main
```

## Edit site pages
- `about.md`: update your bio.
- `index.md`: homepage intro; posts tagged `favorite` appear here first.
- `_includes/header.html` / `_includes/footer.html`: navigation and footer links.

## Style tweaks
Colors, fonts, and spacing live in `assets/css/style.css`. Adjust CSS vars at the top of the file for quick theme changes.

## Troubleshooting
- **Site not updating after push:** check GitHub Actions/Pages build status and wait a minute.
- **Local build issues:** run `bundle update` then `bundle exec jekyll serve`.
- **Custom domain:** ensure `CNAME` in repo root matches your domain and DNS points to GitHub Pages.
