# Frequently Asked Questions

Common questions about Docsify and how to use it.

## General Questions

### What is Docsify?

Docsify is a documentation site generator that works entirely in the browser. Unlike traditional static site generators, Docsify doesn't build your site beforehand - it renders your markdown files dynamically when someone visits your site.

### How is Docsify different from Jekyll, Hugo, or MkDocs?

**Traditional generators:**
- Require a build step
- Generate HTML files beforehand
- Need installation and configuration

**Docsify:**
- No build step required
- Renders in the browser
- Just need one HTML file + markdown

### Do I need to install anything?

No! You don't need to install Docsify. Just create:
1. An `index.html` that loads Docsify from CDN
2. Your markdown files

That's it!

### Is it really free?

Yes! Docsify is:
- ✅ Open source (MIT license)
- ✅ Free to use
- ✅ Free to host (on GitHub Pages, Netlify, etc.)
- ✅ No hidden costs

## Setup Questions

### How do I start a new Docsify site?

Three files is all you need:

```bash
mkdir docs
cd docs

# Create index.html (copy from our example)
# Create README.md (your homepage)
# Create .nojekyll (for GitHub Pages)
```

See our [Installation Guide](installation.md) for details.

### Do I need Node.js or npm?

**No!** Docsify works without any installation.

However, you might want:
- A local web server to preview (Python's SimpleHTTPServer works great)
- Optional: `docsify-cli` for convenience features

### What's the .nojekyll file for?

The `.nojekyll` file tells GitHub Pages not to use Jekyll processing. This is important because:
- Jekyll ignores files starting with `_` (like `_sidebar.md`)
- Docsify needs those files to work

**Solution:** Just create an empty `.nojekyll` file in your `docs/` folder.

### How do I preview my site locally?

Use any local web server:

```bash
# Python 3
python -m http.server 3000

# Python 2
python -m SimpleHTTPServer 3000

# Node.js
npx http-server docs -o

# Docsify CLI
docsify serve docs
```

Then visit `http://localhost:3000`

## Features Questions

### How do I add a sidebar?

1. Create `_sidebar.md` in your `docs/` folder
2. Enable it in `index.html`:

```javascript
window.$docsify = {
  loadSidebar: true
}
```

3. Add links in `_sidebar.md`:

```markdown
* [Home](/)
* [Guide](guide.md)
* [API](api.md)
```

### How do I add search?

Add two things to your `index.html`:

```html
<!-- Configuration -->
<script>
  window.$docsify = {
    search: 'auto', // or detailed config
  }
</script>

<!-- Plugin -->
<script src="//cdn.jsdelivr.net/npm/docsify/lib/plugins/search.min.js"></script>
```

That's it! Search will work automatically.

### Can I use a different theme?

Yes! Change the CSS link in `index.html`:

```html
<!-- Vue theme (default) -->
<link rel="stylesheet" href="//cdn.jsdelivr.net/npm/docsify@4/lib/themes/vue.css">

<!-- Dark theme -->
<link rel="stylesheet" href="//cdn.jsdelivr.net/npm/docsify@4/lib/themes/dark.css">

<!-- Other themes: buble.css, pure.css -->
```

See [Themes guide](config-themes.md) for more.

### How do I organize pages into folders?

Just create folders and reference them:

```
docs/
├── guide/
│   ├── basics.md
│   └── advanced.md
└── api/
    └── endpoints.md
```

In `_sidebar.md`:

```markdown
* Guide
  * [Basics](guide/basics.md)
  * [Advanced](guide/advanced.md)
* API
  * [Endpoints](api/endpoints.md)
```

## Deployment Questions

### How do I deploy to GitHub Pages?

1. Push your code to GitHub
2. Go to Settings → Pages
3. Select branch: `main`, folder: `/docs`
4. Done!

See our [GitHub Pages deployment guide](deploy-github.md) for detailed steps.

### Can I use a custom domain?

Yes! With GitHub Pages:

1. Add a `CNAME` file in `docs/` with your domain
2. Configure DNS with your provider
3. Enable custom domain in GitHub settings

Other platforms (Netlify, Vercel, etc.) also support custom domains.

### Why is my site showing a 404?

Common causes:

1. **Missing .nojekyll** - Create this file in `docs/`
2. **Wrong folder in GitHub Pages** - Should be `/docs` or `/` (root)
3. **Wrong branch** - Check it's deploying from correct branch
4. **Need to wait** - GitHub Pages can take 1-2 minutes to deploy

### Why isn't my sidebar showing?

Two common issues:

1. **Missing .nojekyll** - Jekyll is ignoring `_sidebar.md`
   - Solution: Create `.nojekyll` file

2. **Not enabled** - Check `index.html` has:
   ```javascript
   window.$docsify = {
     loadSidebar: true
   }
   ```

## Customization Questions

### Can I add custom CSS?

Yes! Add a `<style>` tag in `index.html`:

```html
<style>
  :root {
    --theme-color: #ff6b6b;
  }

  .sidebar {
    background: #f5f5f5;
  }
</style>
```

Or link an external CSS file:

```html
<link rel="stylesheet" href="custom.css">
```

### Can I add Google Analytics?

Yes! Add the plugin:

```html
<script>
  window.$docsify = {
    ga: 'UA-XXXXX-Y', // Your Google Analytics ID
  }
</script>
<script src="//cdn.jsdelivr.net/npm/docsify/lib/plugins/ga.min.js"></script>
```

### Can I embed videos or iframes?

Yes! Markdown supports HTML, so just use standard HTML:

```html
<iframe width="560" height="315"
  src="https://www.youtube.com/embed/VIDEO_ID">
</iframe>
```

## Performance Questions

### Is Docsify fast?

Yes! Docsify is very fast because:
- Small JavaScript file (~20KB gzipped)
- Loads from CDN (cached globally)
- Only loads markdown files when needed
- No build step to wait for

### Is it SEO-friendly?

**Partial.** Docsify renders client-side (in JavaScript), which means:
- Modern search engines (Google) can index it
- Some search engines may have difficulty
- Static site generators are better for SEO

**For internal docs:** Docsify is perfect!
**For public docs needing SEO:** Consider a static generator

### How many pages can it handle?

Docsify scales well! Sites with hundreds of pages work great because:
- Only loads pages when visited
- Search is fast and efficient
- No build time (regardless of size)

## Troubleshooting

### Images aren't loading

Use relative paths:

```markdown
![Image](./images/pic.png)  <!-- Correct -->
![Image](images/pic.png)    <!-- May not work -->
```

Or absolute URLs:

```markdown
![Image](https://example.com/pic.png)
```

### Code blocks aren't highlighted

Add Prism language components:

```html
<script src="//cdn.jsdelivr.net/npm/prismjs@1/components/prism-python.min.js"></script>
<script src="//cdn.jsdelivr.net/npm/prismjs@1/components/prism-bash.min.js"></script>
```

### Links are broken

Make sure you're using:
- Relative paths: `[Link](page.md)` not `[Link](/page.md)`
- File extensions: `[Link](page.md)` not `[Link](page)`

## Still Have Questions?

- Check the [official Docsify docs](https://docsify.js.org)
- Visit the [GitHub repository](https://github.com/docsifyjs/docsify)
- Ask on [GitHub Discussions](https://github.com/docsifyjs/docsify/discussions)

---

[Back to Home](/)
