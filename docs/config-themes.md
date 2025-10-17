# Themes

Docsify comes with several built-in themes, and you can easily customize or create your own.

## Built-in Themes

Change themes by modifying the CSS link in `index.html`:

### Official Docsify v4 Themes

#### Vue Theme (Default)

```html
<link rel="stylesheet" href="//cdn.jsdelivr.net/npm/docsify@4/lib/themes/vue.css">
```

Light, clean, Vue.js-inspired design.

#### Buble Theme

```html
<link rel="stylesheet" href="//cdn.jsdelivr.net/npm/docsify@4/lib/themes/buble.css">
```

Similar to Vue but with different colors.

#### Dark Theme

```html
<link rel="stylesheet" href="//cdn.jsdelivr.net/npm/docsify@4/lib/themes/dark.css">
```

Dark mode for your docs.

#### Pure Theme

```html
<link rel="stylesheet" href="//cdn.jsdelivr.net/npm/docsify@4/lib/themes/pure.css">
```

Minimal, distraction-free design.

#### Dolphin Theme

```html
<link rel="stylesheet" href="//cdn.jsdelivr.net/npm/docsify@4/lib/themes/dolphin.css">
```

Alternative light theme.

### Docsify-Themeable (Advanced Theme System)

Better themes with more customization options and improved mobile experience:

#### Simple Theme

```html
<link rel="stylesheet" href="//cdn.jsdelivr.net/npm/docsify-themeable@0/dist/css/theme-simple.css">
```

Clean, modern light theme.

#### Simple Dark Theme

```html
<link rel="stylesheet" href="//cdn.jsdelivr.net/npm/docsify-themeable@0/dist/css/theme-simple-dark.css">
```

Clean, modern dark theme with better contrast than default dark.

#### Defaults Theme

```html
<link rel="stylesheet" href="//cdn.jsdelivr.net/npm/docsify-themeable@0/dist/css/theme-defaults.css">
```

Comprehensive default styling.

### Community Themes

#### Darkly Theme

```html
<link rel="stylesheet" href="//cdn.jsdelivr.net/npm/docsify-darkly-theme@latest/dist/style.min.css">
```

High-contrast dark theme.

#### DarkLight Theme (with toggle)

```html
<link rel="stylesheet" href="//cdn.jsdelivr.net/npm/docsify-darklight-theme@latest/dist/style.min.css">
<script src="//cdn.jsdelivr.net/npm/docsify-darklight-theme@latest/dist/index.min.js"></script>
```

Automatic dark/light theme switcher.

#### Darcula Theme

```bash
npm install docsify-theme-darcula
```

Then add to your `index.html`:
```html
<link rel="stylesheet" href="./node_modules/docsify-theme-darcula/dist/style.min.css">
```

JetBrains Darcula-inspired dark theme.

#### GitHub Theme

```bash
npm install docsify-theme-github
```

Then add to your `index.html`:
```html
<link rel="stylesheet" href="./node_modules/docsify-theme-github/dist/style.min.css">
```

GitHub Markdown style.

#### Retro Themes

**Windows 98 Classic:**
```bash
npm install docsify-theme-98
```

Then add to your `index.html`:
```html
<link rel="stylesheet" href="./node_modules/docsify-theme-98/dist/style.min.css">
```

**Windows XP Luna:**
```bash
npm install docsify-theme-xp
```

Then add to your `index.html`:
```html
<link rel="stylesheet" href="./node_modules/docsify-theme-xp/dist/style.min.css">
```

**Windows Vista Aero:**
```bash
npm install docsify-theme-vista
```

Then add to your `index.html`:
```html
<link rel="stylesheet" href="./node_modules/docsify-theme-vista/dist/style.min.css">
```

## Theme Comparison

| Theme | Style | CDN Available | Best For |
|-------|-------|---------------|----------|
| Vue | Light, colorful | Yes | General documentation |
| Buble | Light, professional | Yes | Business docs |
| Dark | Dark background | Yes | Developer docs |
| Pure | Minimal | Yes | Technical writing |
| Dolphin | Light alternative | Yes | Alternative light theme |
| Themeable Simple | Modern light | Yes | Professional docs |
| Themeable Dark | Modern dark | Yes | Better dark mode |
| Darkly | High-contrast dark | Yes | Accessibility |
| DarkLight | Auto-switching | Yes | User preference |
| GitHub | GitHub-style | No (npm) | Familiar interface |
| Retro | Nostalgic | No (npm) | Fun projects |

## Custom Styling

### Override with Custom CSS

Add a `<style>` tag in your `index.html`:

```html
<head>
  <link rel="stylesheet" href="//cdn.jsdelivr.net/npm/docsify@4/lib/themes/vue.css">

  <style>
    /* Custom colors */
    :root {
      --theme-color: #2c3e50;
      --theme-color-dark: #1a252f;
    }

    /* Custom sidebar */
    .sidebar {
      background: #f8f9fa;
    }

    /* Custom links */
    a {
      color: #3498db;
    }
  </style>
</head>
```

### External CSS File

Create `custom.css` in your `docs/` folder:

```css
/* custom.css */
:root {
  --theme-color: #ff6b6b;
}

.sidebar-nav a {
  font-weight: 500;
}

.markdown-section code {
  background: #f0f0f0;
  border-radius: 4px;
}
```

Then load it in `index.html`:

```html
<link rel="stylesheet" href="//cdn.jsdelivr.net/npm/docsify@4/lib/themes/vue.css">
<link rel="stylesheet" href="custom.css">
```

## CSS Variables

Docsify uses CSS custom properties for easy theming:

```css
:root {
  /* Main theme color */
  --theme-color: #ea6f5a;
  --theme-color-dark: #d84315;

  /* Background colors */
  --base-background-color: #ffffff;
  --sidebar-background: #f8f9fa;

  /* Text colors */
  --base-color: #333333;
  --heading-color: #2c3e50;

  /* Sidebar */
  --sidebar-width: 300px;
  --sidebar-toggle-background: #fafafa;

  /* Code blocks */
  --code-background-color: #f8f8f8;
  --code-inline-background: #f0f0f0;
  --code-theme-keyword: #c678dd;

  /* Links */
  --link-color: #3498db;
  --link-color-hover: #2980b9;
}
```

## Example: Custom Brand Theme

```html
<head>
  <link rel="stylesheet" href="//cdn.jsdelivr.net/npm/docsify@4/lib/themes/vue.css">

  <style>
    :root {
      /* Your brand colors */
      --theme-color: #ff6b6b;
      --theme-color-dark: #ee5a52;

      /* Custom sidebar */
      --sidebar-background: #2c3e50;
      --sidebar-nav-link-color: #ecf0f1;
      --sidebar-nav-link-color--hover: #ffffff;
      --sidebar-nav-link-background-color--hover: #34495e;
    }

    /* Custom font */
    body {
      font-family: 'Inter', sans-serif;
    }

    /* Rounded corners */
    .sidebar {
      border-radius: 0 12px 12px 0;
    }

    /* Custom search bar */
    .search input {
      border: 2px solid var(--theme-color);
      border-radius: 8px;
    }

    /* Custom code blocks */
    pre[data-lang] {
      border-left: 4px solid var(--theme-color);
      border-radius: 4px;
    }
  </style>
</head>
```

## Dark Mode Toggle

Add a simple dark mode toggle:

```html
<script>
  window.$docsify = {
    plugins: [
      function(hook, vm) {
        hook.mounted(function() {
          // Add toggle button
          const toggle = document.createElement('button');
          toggle.textContent = '🌙';
          toggle.style.cssText = 'position:fixed;bottom:20px;right:20px;z-index:999;';
          document.body.appendChild(toggle);

          // Toggle theme
          toggle.onclick = function() {
            const link = document.querySelector('link[title="theme"]');
            const isDark = link.href.includes('dark');
            link.href = isDark
              ? '//cdn.jsdelivr.net/npm/docsify@4/lib/themes/vue.css'
              : '//cdn.jsdelivr.net/npm/docsify@4/lib/themes/dark.css';
            toggle.textContent = isDark ? '🌙' : '☀️';
          };
        });
      }
    ]
  }
</script>

<link rel="stylesheet" href="//cdn.jsdelivr.net/npm/docsify@4/lib/themes/vue.css" title="theme">
```

## Community Themes

- **docsify-themeable**: Advanced theming system
  ```html
  <link rel="stylesheet" href="//cdn.jsdelivr.net/npm/docsify-themeable@0/dist/css/theme-simple.css">
  ```

- **docsify-darklight-theme**: Built-in dark/light toggle
  ```html
  <link rel="stylesheet" href="//cdn.jsdelivr.net/npm/docsify-darklight-theme@latest/dist/style.min.css">
  ```

## Tips for Custom Themes

1. **Start with a base theme** - Override only what you need
2. **Use CSS variables** - Makes customization easier
3. **Test on mobile** - Ensure responsive design
4. **Check contrast** - Maintain readability
5. **Keep it simple** - Don't over-style

## Next Steps

- [Deploy to GitHub Pages](deploy-github.md) →
- [See example pages](examples/sample1.md) →
