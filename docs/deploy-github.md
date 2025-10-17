# Deploy to GitHub Pages

GitHub Pages is the perfect (and free!) hosting solution for Docsify sites.

## Prerequisites

- A GitHub account
- Git installed on your computer
- Your Docsify site ready in a `docs/` folder

## Step-by-Step Deployment

### Step 1: Create a GitHub Repository

```bash
# On GitHub, create a new repository (e.g., my-docs)
# Then on your computer:

cd my-project
git init
git add .
git commit -m "Initial commit"
git remote add origin https://github.com/username/my-docs.git
git push -u origin main
```

### Step 2: Ensure .nojekyll Exists

This is CRITICAL for Docsify on GitHub Pages:

```bash
# In your docs/ folder
touch docs/.nojekyll
git add docs/.nojekyll
git commit -m "Add .nojekyll for GitHub Pages"
git push
```

**Why?** GitHub Pages uses Jekyll by default, which ignores files starting with underscore (like `_sidebar.md`). The `.nojekyll` file disables Jekyll.

### Step 3: Enable GitHub Pages

1. Go to your repository on GitHub
2. Click **Settings** tab
3. Scroll to **Pages** section (left sidebar)
4. Under **Source**, select:
   - Branch: `main` (or `master`)
   - Folder: `/docs`
5. Click **Save**

### Step 4: Wait for Deployment

GitHub will build and deploy your site (usually takes 1-2 minutes).

Your site will be available at:
```
https://username.github.io/repository-name/
```

## Folder Structure Options

### Option 1: /docs Folder (Recommended)

```
my-repo/
├── docs/           # Your Docsify site
│   ├── index.html
│   ├── README.md
│   └── .nojekyll
├── src/            # Other project files
└── README.md       # Repo README
```

In GitHub Pages settings:
- Branch: `main`
- Folder: `/docs`

### Option 2: Root Directory

```
my-repo/
├── index.html
├── README.md
├── .nojekyll
└── other-files/
```

In GitHub Pages settings:
- Branch: `main`
- Folder: `/` (root)

### Option 3: gh-pages Branch

```bash
# Create separate branch for docs
git checkout --orphan gh-pages
git rm -rf .
# Add your Docsify files here
git add .
git commit -m "Deploy to gh-pages"
git push origin gh-pages
```

In GitHub Pages settings:
- Branch: `gh-pages`
- Folder: `/` (root)

## Custom Domain (Optional)

### Step 1: Add CNAME File

Create `docs/CNAME`:

```
docs.mysite.com
```

### Step 2: Configure DNS

Add DNS records with your domain provider:

```
Type: CNAME
Name: docs (or @ for apex domain)
Value: username.github.io
```

### Step 3: Enable in GitHub Settings

In GitHub Pages settings:
- Enter your custom domain
- Check "Enforce HTTPS"

## Troubleshooting

### Site Not Loading

**Problem:** Blank page or 404 error

**Solutions:**
1. Check `.nojekyll` file exists in `docs/`
2. Verify GitHub Pages is enabled in settings
3. Check branch and folder are correct
4. Wait 5 minutes (deployment takes time)
5. Hard refresh browser (Ctrl+Shift+R)

### Sidebar Not Showing

**Problem:** `_sidebar.md` not loading

**Cause:** Missing `.nojekyll` file

**Solution:**
```bash
touch docs/.nojekyll
git add docs/.nojekyll
git commit -m "Add .nojekyll"
git push
```

### CSS Not Loading

**Problem:** Site has no styling

**Solutions:**
1. Check index.html uses CDN links (not local)
2. Ensure links use `//` or `https://` (not relative paths)
3. Clear browser cache

### Images Not Loading

**Problem:** Images show broken

**Solutions:**
1. Use relative paths: `![Image](./images/pic.png)`
2. Or use full URLs: `![Image](https://example.com/pic.png)`
3. Ensure images are committed to repo

## Automatic Deployment

### Using GitHub Actions

Create `.github/workflows/deploy.yml`:

```yaml
name: Deploy to GitHub Pages

on:
  push:
    branches: [ main ]

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2

      - name: Deploy to GitHub Pages
        uses: peaceiris/actions-gh-pages@v3
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          publish_dir: ./docs
```

## Updating Your Site

Super simple:

```bash
# Edit your markdown files
git add .
git commit -m "Update documentation"
git push
```

GitHub Pages will automatically redeploy in 1-2 minutes!

## Complete Checklist

Before deploying, ensure:

- [ ] `.nojekyll` file exists in `docs/`
- [ ] `index.html` uses CDN links (not local paths)
- [ ] All markdown files are in `docs/`
- [ ] Images use relative or absolute URLs
- [ ] Repository is public (or you have GitHub Pro for private Pages)
- [ ] Git repository is initialized and pushed
- [ ] GitHub Pages is enabled in repository settings

## Next Steps

- [Deploy to other platforms](deploy-other.md) →
- [View FAQ](faq.md) →

---

**Congratulations!** Your Docsify site is now live! 🎉
