# Letters by G - Blog Owner's Guide

Welcome to your Jekyll blog! This guide will help you write and customize your blog.

---

## Writing Your First Post

### Creating a New Blog Post

1. Navigate to the `_posts` folder
2. Create a new file with the naming convention: `YYYY-MM-DD-your-post-title.md`
   - Example: `2025-12-15-why-i-started-this-blog.md`

### Blog Post Structure

Every post starts with **front matter** (the section between `---` markers):

```markdown
---
layout: post
title: Your Post Title
date: 2025-12-15
categories: [Category1, Category2]
excerpt: "A brief summary that appears on the homepage"
---

Your post content goes here...
```

**Front Matter Explained:**
- `layout: post` – Always use this for blog posts
- `title` – Your post title (appears as heading and in listings)
- `date` – Publication date in YYYY-MM-DD format
- `categories` – Topics for your post (helps organize content)
- `excerpt` – Brief summary (shows on homepage; write 1-2 sentences)

### Writing Your Content

After the front matter, write your post using **Markdown**:

```markdown
## Main Section

Write your content here. You can use paragraphs, **bold**, *italics*, `code`, and more.

### Subsection

- Bullet points
- Work great
- For lists

[Links look like this](https://example.com)

> Blockquotes are useful for emphasis or quotes
```

### Tips for Great Posts

- **Start strong** – Your first paragraph should grab attention
- **Use subheadings** – Break up longer posts with `##` and `###`
- **Keep paragraphs short** – Easier to read on screen
- **Use examples** – Concrete examples help readers understand
- **Write naturally** – Your voice matters more than perfection

---

## Customizing Your Blog

### Change Blog Title & Description

Edit `_config.yml`:

```yaml
title: Letters by G
description: Essays on startups, building, and learning
author: Your Name
email: your@email.com
```

### Add Social Links

In `_config.yml`, add your social usernames:

```yaml
github_username: your-github-handle
twitter_username: your-twitter-handle
```

These will appear as clickable links in your footer.

### Customize Colors & Design

Edit `assets/css/style.css` to change:

- **Main color** – `--main-color: #333` (text color)
- **Light color** – `--light-color: #666` (meta text)
- **Accent color** – `--accent-color: #0066cc` (links, highlights)
- **Background** – `--background: #fff` (page background)

Example:
```css
:root {
  --main-color: #1a1a1a;      /* Darker text */
  --accent-color: #e74c3c;    /* Red links */
  --background: #f9f9f9;      /* Light gray background */
}
```

### Update Your About Page

Edit `about.md` to tell your story. This page is separate from blog posts and appears in navigation.

### Update Homepage

Edit `index.md` to customize what appears on your homepage.

## GitHub Pages Setup

### Method 1: Using GitHub Pages UI (Recommended)

1. Create a new repository named `<username>.github.io` on GitHub

2. Push this code:
```bash
git init
git add .
git commit -m "Initial commit"
git remote add origin https://github.com/<username>/<username>.github.io.git
git branch -M main
git push -u origin main
```

3. Go to repository Settings → Pages
4. Ensure "Source" is set to "Deploy from a branch" with "main" branch selected
5. Your site will be published at `https://<username>.github.io`

### Method 2: Custom Domain

1. Follow Method 1 first

2. Create a file named `CNAME` in the root with your domain:
```
lettersbyg.com
```

3. Push the CNAME file:
```bash
git add CNAME
git commit -m "Add custom domain"
git push
```

4. Update your domain's DNS records to point to GitHub Pages:
   - Add an A record pointing to GitHub's IP addresses
   - Or use CNAME pointing to `<username>.github.io`
   
   See: https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site

5. GitHub will auto-generate an SSL certificate (wait a few minutes)

### GitHub Pages Settings

In your repository settings:
- Ensure "Source" is set to "Deploy from a branch"
- Select the "main" branch
- Enforce HTTPS (after custom domain setup)

## Building & Deployment

### Local Build
```bash
bundle exec jekyll build
```

Output goes to `_site/` directory.

### Automatic Deployment

GitHub automatically rebuilds your site when you push to the main branch. The build process:
1. Runs Jekyll to generate static HTML
2. Publishes to GitHub Pages
3. Available at your domain within seconds

### Build Status

Check your build status:
- Go to Actions tab in GitHub repository
- View recent workflow runs
- Check for any build errors

## Managing Content

### Adding Pages

Create `.md` files in the root directory with front matter:
```markdown
---
layout: page
title: Page Title
permalink: /path/
---

Page content...
```

### Organizing Posts

Use categories in front matter:
```markdown
---
layout: post
title: Post Title
date: 2025-01-15
categories: [AI, Startups, Tech]
---
```

Posts automatically appear on homepage, sorted by date (newest first).

## Plugins Included

- **jekyll-feed**: Generates RSS feed at `/feed.xml`
- **jekyll-sitemap**: Generates `sitemap.xml` for SEO
- **jekyll-seo-tag**: Optimizes meta tags for search engines

## Tips & Best Practices

- Use descriptive post filenames with dates
- Write in Markdown with Jekyll front matter
- Include excerpts in posts for homepage listing
- Add categories for better organization
- Link to other posts using `{{ post.url | relative_url }}`
- Optimize images before uploading to `assets/images/`

## Troubleshooting

### Site doesn't update after push
- Check GitHub Actions tab for build errors
- Ensure you're pushing to the `main` branch
- Wait a few moments, GitHub can take up to 30 seconds

### Local build fails
```bash
bundle update
bundle exec jekyll serve
```

### Custom domain not working
- Verify DNS records are correct
- Check CNAME file is in repository root
- Wait 24-48 hours for DNS propagation

## Resources

- [Jekyll Documentation](https://jekyllrb.com/)
- [GitHub Pages Documentation](https://pages.github.com/)
- [Markdown Syntax Guide](https://www.markdownguide.org/)

## License

Your content, your rules. Customize as needed!
