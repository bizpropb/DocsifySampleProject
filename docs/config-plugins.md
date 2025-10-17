# Plugins

Docsify has a rich plugin ecosystem. All plugins are loaded via CDN script tags.

## Essential Plugins

### Search Plugin

Full-text search across all your docs:

```html
<!-- In index.html, add to window.$docsify -->
<script>
  window.$docsify = {
    search: {
      maxAge: 86400000,        // Cache for 1 day
      paths: 'auto',            // Auto-detect all pages
      placeholder: 'Search...',
      noData: 'No Results!',
      depth: 4,                 // Search heading depth
    },
  }
</script>

<!-- Then add the plugin script -->
<script src="//cdn.jsdelivr.net/npm/docsify/lib/plugins/search.min.js"></script>
```

### Emoji Plugin

Render emoji shortcodes like `:smile:` → :smile:

```html
<script src="//cdn.jsdelivr.net/npm/docsify/lib/plugins/emoji.min.js"></script>
```

### Copy Code Plugin

Adds a copy button to code blocks:

```html
<script src="//cdn.jsdelivr.net/npm/docsify-copy-code@2"></script>
```

## Code Enhancement Plugins

### Syntax Highlighting (Prism)

Add language-specific highlighting:

```html
<!-- Core languages are included by default -->
<!-- Add more languages: -->
<script src="//cdn.jsdelivr.net/npm/prismjs@1/components/prism-bash.min.js"></script>
<script src="//cdn.jsdelivr.net/npm/prismjs@1/components/prism-python.min.js"></script>
<script src="//cdn.jsdelivr.net/npm/prismjs@1/components/prism-java.min.js"></script>
```

### Run Code Plugin

Execute JavaScript code directly in docs:

```html
<script src="//cdn.jsdelivr.net/npm/docsify/lib/plugins/external-script.min.js"></script>
```

## Navigation Plugins

### Pagination

Previous/Next navigation buttons:

```html
<script src="//cdn.jsdelivr.net/npm/docsify-pagination@2/dist/docsify-pagination.min.js"></script>
```

### Tabs Plugin

Create tabbed content:

```html
<script src="//cdn.jsdelivr.net/npm/docsify-tabs@1"></script>
```

Usage in markdown:

```markdown
<!-- tabs:start -->
#### **Tab 1**
Content for tab 1

#### **Tab 2**
Content for tab 2
<!-- tabs:end -->
```

## Content Plugins

### Zoom Image

Click images to zoom:

```html
<script src="//cdn.jsdelivr.net/npm/docsify/lib/plugins/zoom-image.min.js"></script>
```

### External Link Plugin

Opens external links in new tabs:

```html
<script src="//cdn.jsdelivr.net/npm/docsify/lib/plugins/external-script.min.js"></script>
```

### Embed Plugin

Embed external files:

```html
<script src="//cdn.jsdelivr.net/npm/docsify-embed/embed.min.js"></script>
```

## Utility Plugins

### Edit on GitHub

Add "Edit on GitHub" link to each page:

```html
<script>
  window.$docsify = {
    plugins: [
      function(hook, vm) {
        hook.beforeEach(function(html) {
          const url = 'https://github.com/user/repo/blob/main/docs/' + vm.route.file;
          const editHtml = '[📝 Edit on GitHub](' + url + ')\n\n';
          return editHtml + html;
        });
      }
    ]
  }
</script>
```

### Footer Plugin

Add footer to every page:

```html
<script>
  window.$docsify = {
    plugins: [
      function(hook) {
        hook.afterEach(function(html) {
          return html + '<hr/><footer>Made with ❤️</footer>';
        });
      }
    ]
  }
</script>
```

### Progress Bar

Show loading progress bar:

```html
<script src="//cdn.jsdelivr.net/npm/docsify/lib/plugins/progress.min.js"></script>
```

## Complete Plugin Example

Here's an `index.html` with common plugins:

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <title>My Docs</title>
  <link rel="stylesheet" href="//cdn.jsdelivr.net/npm/docsify@4/lib/themes/vue.css">
</head>
<body>
  <div id="app"></div>

  <script>
    window.$docsify = {
      name: 'My Docs',
      repo: 'user/repo',
      loadSidebar: true,

      // Search plugin config
      search: {
        placeholder: 'Search...',
        noData: 'No Results',
        depth: 3,
      },
    }
  </script>

  <!-- Docsify core -->
  <script src="//cdn.jsdelivr.net/npm/docsify@4"></script>

  <!-- Plugins -->
  <script src="//cdn.jsdelivr.net/npm/docsify/lib/plugins/search.min.js"></script>
  <script src="//cdn.jsdelivr.net/npm/docsify/lib/plugins/emoji.min.js"></script>
  <script src="//cdn.jsdelivr.net/npm/docsify-copy-code@2"></script>
  <script src="//cdn.jsdelivr.net/npm/docsify/lib/plugins/zoom-image.min.js"></script>
  <script src="//cdn.jsdelivr.net/npm/docsify-pagination@2/dist/docsify-pagination.min.js"></script>

  <!-- Syntax highlighting -->
  <script src="//cdn.jsdelivr.net/npm/prismjs@1/components/prism-bash.min.js"></script>
  <script src="//cdn.jsdelivr.net/npm/prismjs@1/components/prism-javascript.min.js"></script>
</body>
</html>
```

## Finding More Plugins

- Official plugins: https://docsify.js.org/#/plugins
- Community plugins: Search "docsify plugin" on npm
- Write your own: Use the hook system in `window.$docsify.plugins`

## Next Steps

- [Customize themes](config-themes.md) →
- [Deploy to GitHub Pages](deploy-github.md) →
