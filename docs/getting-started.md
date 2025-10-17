# What is Docsify?

Docsify is a **magical documentation site generator** that doesn't require you to build your site beforehand.

## Key Concepts

### It's NOT a Static Site Generator

Unlike Jekyll, Hugo, or MkDocs, Docsify doesn't "build" your site. There's no build step!

**Traditional generators:**
```
Markdown files → Build process → HTML files → Deploy
```

**Docsify:**
```
Markdown files + index.html → Deploy → Browser converts on-the-fly
```

### It's a Single Page Application

When someone visits your Docsify site:

1. Their browser loads `index.html`
2. The Docsify JavaScript (from CDN) runs
3. Docsify reads your markdown files
4. Docsify converts markdown to HTML in real-time
5. The page renders beautifully!

## Why Use Docsify?

### Advantages

- **Zero build time** - No waiting for site generation
- **Simple setup** - Just one HTML file + markdown
- **Live preview** - Edit markdown, refresh browser, done
- **GitHub Pages ready** - Push and it works
- **Search built-in** - Full-text search with one plugin line
- **Sidebar auto-generates** - From your `_sidebar.md` file

### Perfect For

- 📚 Project documentation
- 📖 Personal wikis
- 📝 Knowledge bases
- 🎓 Tutorial sites
- 📋 API documentation

### Not Ideal For

- 🔒 Sites requiring SEO (search engines may struggle with client-side rendering)
- 🏢 Large enterprise docs with complex builds
- 🌐 Sites that need to work without JavaScript

## What You Need

Literally just:

1. A folder (let's call it `docs/`)
2. An `index.html` file (loads Docsify from CDN)
3. A `README.md` file (your homepage content)
4. Optional: `_sidebar.md` (for navigation)
5. Optional: `.nojekyll` (if using GitHub Pages)

That's it! 🎉

## Next Steps

Ready to set it up? Head to [Installation Guide](installation.md) →
