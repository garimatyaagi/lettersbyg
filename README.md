# Letters by G - Jekyll Blog

A Jekyll-powered blog ready to be hosted on GitHub Pages.

## Project Structure

```
├── _config.yml              # Jekyll configuration
├── _includes/               # HTML components (header, footer)
├── _layouts/                # Page templates
├── _posts/                  # Blog post markdown files
├── assets/
│   ├── css/                 # Stylesheets
│   ├── js/                  # JavaScript
│   └── images/              # Images
├── about.md                 # About page
├── index.md                 # Home page
├── Gemfile                  # Ruby dependencies
└── .gitignore
```

## Getting Started

### Prerequisites

- Ruby 2.7+ (Ruby 3.1 recommended)
- Bundler

### Installation

1. Install Ruby from [ruby-lang.org](https://www.ruby-lang.org/en/downloads/)

2. Install dependencies:
```bash
bundle install
```

3. Serve locally:
```bash
bundle exec jekyll serve
```

Then visit `http://localhost:4000` in your browser.

## Adding Blog Posts

Create a new file in `_posts/` with the naming convention: `YYYY-MM-DD-post-title.md`

Example:
```markdown
---
layout: post
title: Your Post Title
date: 2025-01-15
categories: [Category1, Category2]
excerpt: "Brief description of your post"
---

Your post content here...
```

## Customization

### Update Site Config

Edit `_config.yml`:
- `title`: Your site title
- `description`: Site description
- `author`: Your name
- `email`: Your email
- `url`: Your domain (e.g., https://lettersbyg.com)
- `github_username`: For GitHub link in footer
- `twitter_username`: For Twitter link in footer

### Update Styling

Modify `assets/css/style.css` to customize colors and layout.

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
