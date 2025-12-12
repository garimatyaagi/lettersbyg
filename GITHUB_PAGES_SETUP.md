# GitHub Pages Deployment Checklist

Use this checklist to ensure your Jekyll blog is properly set up for GitHub Pages.

## Pre-Deployment Checklist

- [ ] Update `_config.yml` with your site title, description, and author
- [ ] Update your email in `_config.yml`
- [ ] Add your GitHub username to `_config.yml` (for GitHub link)
- [ ] Add your Twitter username if you have one
- [ ] Replace sample blog posts with your actual content
- [ ] Update `about.md` with your bio
- [ ] Test site locally: `bundle exec jekyll serve`
- [ ] Verify site loads at `http://localhost:4000`

## GitHub Repository Setup

- [ ] Create GitHub account if needed
- [ ] Create new repository named `<your-username>.github.io`
- [ ] Clone the empty repository locally

## Deploying Code

```bash
# Navigate to your project directory
cd /path/to/lettersbyg.com

# Initialize git if not already done
git init

# Add all files
git add .

# Create initial commit
git commit -m "Initial Jekyll blog setup"

# Add remote (replace USERNAME with your GitHub username)
git remote add origin https://github.com/USERNAME/USERNAME.github.io.git

# Rename branch to main if needed
git branch -M main

# Push to GitHub
git push -u origin main
```

- [ ] Confirm all files are pushed to GitHub

## GitHub Pages Configuration

1. Go to your repository on GitHub
2. Click "Settings" tab
3. Scroll to "Pages" section
4. Verify settings:
   - [ ] "Source" is set to "Deploy from a branch"
   - [ ] Branch is set to "main"
   - [ ] Folder is set to "/ (root)"
5. Click "Save"

## Verification

- [ ] Wait 1-2 minutes for initial build
- [ ] Check Actions tab for build status (should show green checkmark)
- [ ] Visit `https://<your-username>.github.io` in browser
- [ ] Verify site loads correctly
- [ ] Test links and navigation

## Setting Up Custom Domain (Optional)

### If using lettersbyg.com:

1. [ ] Create `CNAME` file in repository root with:
   ```
   lettersbyg.com
   ```

2. [ ] Push CNAME file:
   ```bash
   git add CNAME
   git commit -m "Add custom domain"
   git push
   ```

3. [ ] Update domain DNS records:
   - For example with Namecheap, GoDaddy, etc.
   - Point to GitHub Pages (see GitHub's documentation for specific records)

4. [ ] Wait for DNS to propagate (up to 48 hours)

5. [ ] GitHub Pages settings:
   - [ ] Go to Settings > Pages
   - [ ] Enter custom domain
   - [ ] Check "Enforce HTTPS" once it appears

## Post-Deployment

- [ ] Subscribe to RSS feed: `yourdomain.com/feed.xml`
- [ ] Share your blog on social media
- [ ] Monitor GitHub Actions for any build issues
- [ ] Keep blog posts updated regularly

## Troubleshooting URLs

If your site is not loading:
- Check GitHub Actions (Settings > Actions) for build errors
- Ensure correct repository name `USERNAME.github.io`
- Verify CNAME file is properly formatted (no extra text)
- Try hard-refreshing browser (Ctrl+Shift+R or Cmd+Shift+R)

## Future Updates

To update your blog:

```bash
# Make changes to files locally
# Then commit and push:
git add .
git commit -m "Your commit message"
git push
```

GitHub will automatically rebuild your site!
