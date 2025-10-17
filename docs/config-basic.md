# Basic Configuration

All Docsify configuration happens in the `window.$docsify` object in your `index.html` file.

## Essential Settings

### name

The site name that appears in the sidebar header:

```javascript
window.$docsify = {
  name: 'My Documentation',
}
```

### repo

Shows a GitHub/GitLab repository link in the corner:

```javascript
window.$docsify = {
  repo: 'https://github.com/username/repo',
  // Or just:
  repo: 'username/repo',
}
```

### loadSidebar

Enables the sidebar from `_sidebar.md`:

```javascript
window.$docsify = {
  loadSidebar: true,
  // Optional: specify custom sidebar file
  loadSidebar: '_sidebar.md',
}
```

### subMaxLevel

How many heading levels to show in the sidebar:

```javascript
window.$docsify = {
  subMaxLevel: 2, // Show H1 and H2 headings
  // 0 = show all levels
  // 1 = show only H1
  // 2 = show H1 and H2 (recommended)
}
```

### homepage

Specify which file to load as the homepage:

```javascript
window.$docsify = {
  homepage: 'README.md', // Default
  // Or use a different file:
  homepage: 'home.md',
}
```

## Navigation Settings

### auto2top

Automatically scroll to top when changing routes:

```javascript
window.$docsify = {
  auto2top: true, // Recommended
}
```

### maxLevel

Maximum table of contents level:

```javascript
window.$docsify = {
  maxLevel: 4, // Show up to H4 in TOC
}
```

### relativePath

Use relative paths for links:

```javascript
window.$docsify = {
  relativePath: true,
}
```

## Cover Page

### coverpage

Enable a landing cover page:

```javascript
window.$docsify = {
  coverpage: true,
  // Then create _coverpage.md
}
```

Example `_coverpage.md`:

```markdown
# My Docs

> A beautiful documentation site

[GitHub](https://github.com/user/repo)
[Get Started](#main)
```

### onlyCover

Show cover page only on root path:

```javascript
window.$docsify = {
  coverpage: true,
  onlyCover: true,
}
```

## Complete Example

Here's a well-configured `index.html`:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>My Documentation</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" href="//cdn.jsdelivr.net/npm/docsify@4/lib/themes/vue.css">
</head>
<body>
  <div id="app">Loading...</div>

  <script>
    window.$docsify = {
      // Site info
      name: 'My Docs',
      repo: 'username/repo',

      // Sidebar
      loadSidebar: true,
      subMaxLevel: 2,

      // Navigation
      auto2top: true,
      maxLevel: 4,

      // Homepage
      homepage: 'README.md',

      // Search (configured in plugins section)
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
</body>
</html>
```

## Common Options Reference

| Option | Type | Default | Description |
|--------|------|---------|-------------|
| `name` | String | `''` | Site name in sidebar |
| `repo` | String | `''` | Repository URL |
| `loadSidebar` | Boolean/String | `false` | Load custom sidebar |
| `subMaxLevel` | Number | `0` | Sidebar TOC depth |
| `homepage` | String | `'README.md'` | Homepage file |
| `auto2top` | Boolean | `false` | Auto scroll to top |
| `maxLevel` | Number | `6` | Max heading level in TOC |
| `coverpage` | Boolean/String | `false` | Enable cover page |

## Next Steps

- [Configure plugins](config-plugins.md) →
- [Change themes](config-themes.md) →
- [Deploy your site](deploy-github.md) →
