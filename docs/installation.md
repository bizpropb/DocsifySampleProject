# Installation Guide

Setting up Docsify is incredibly simple. No npm install, no build tools required!

## Quick Setup (5 Minutes)

### Step 1: Create Your Folder Structure

```bash
mkdir my-docs
cd my-docs
mkdir docs
cd docs
```

### Step 2: Create index.html

This is the **only** HTML file you need!

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <title>My Docs</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" href="//cdn.jsdelivr.net/npm/docsify@4/lib/themes/vue.css">
</head>
<body>
  <div id="app"></div>
  <script>
    window.$docsify = {
      name: 'My Docs',
      loadSidebar: true,
      subMaxLevel: 2,
      search: 'auto',
    }
  </script>
  <script src="//cdn.jsdelivr.net/npm/docsify@4"></script>
  <script src="//cdn.jsdelivr.net/npm/docsify/lib/plugins/search.min.js"></script>
</body>
</html>
```

### Step 3: Create README.md

This becomes your homepage:

```markdown
# My Documentation

Welcome to my docs!

## Getting Started

This is the homepage of your documentation site.
```

### Step 4: Create _sidebar.md (Optional but Recommended)

This creates your navigation menu:

```markdown
* [Home](/)
* [Guide](guide.md)
* [About](about.md)
```

### Step 5: Create .nojekyll (If Using GitHub Pages)

This prevents GitHub from ignoring files starting with underscore:

```bash
touch .nojekyll
```

## Testing Locally

You need a local web server to test. Here are simple options:

### Option 1: Python (Usually Pre-installed)

```bash
# Python 3
python -m http.server 3000

# Python 2
python -m SimpleHTTPServer 3000
```

Then visit: `http://localhost:3000`

### Option 2: Node.js http-server

```bash
npx http-server docs -o
```

### Option 3: VS Code Live Server Extension

1. Install "Live Server" extension
2. Right-click `index.html`
3. Select "Open with Live Server"

## File Structure Summary

Your final structure should look like:

```
my-docs/
└── docs/
    ├── .nojekyll          # Tells GitHub to serve underscore files
    ├── index.html         # The magic file that loads Docsify
    ├── README.md          # Your homepage content
    ├── _sidebar.md        # Navigation menu
    ├── getting-started.md # Other pages...
    └── guide.md           # More pages...
```

## What Each File Does

| File | Purpose |
|------|---------|
| `index.html` | Loads Docsify library, configures settings |
| `README.md` | Homepage content (landing page) |
| `_sidebar.md` | Navigation sidebar structure |
| `.nojekyll` | Tells GitHub Pages to serve all files |
| Other `.md` files | Your actual documentation pages |

## Next Steps

Now you're ready to:

- [Create your first page](first-page.md) →
- [Configure settings](config-basic.md) →
- [Deploy to GitHub Pages](deploy-github.md) →

---

**Pro Tip:** You can copy this entire sample project to start your own docs!
