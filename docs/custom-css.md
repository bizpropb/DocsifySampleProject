# Docsify CSS Customization Guide

## How to Customize

Add a `<style>` tag after the theme stylesheet in your `index.html`:

```html
<!-- Theme -->
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/docsify-themeable@0/dist/css/theme-simple.css">

<!-- Custom theme styles -->
<style>
  :root {
    --base-font-size: 14px;
    --theme-color: purple;
  }
</style>
```

Or link to an external stylesheet.

## Theme Style Categories

### App
Application-level styling properties

### Base
Foundational style variables including:
- `--base-font-size`
- `--base-font-family`
- `--base-line-height`
- `--base-background-color`
- `--theme-color`

### Code
Syntax highlighting and code block appearance:
- `--code-font-family`
- `--code-font-size`
- `--code-font-weight`
- `--code-block-border-radius`
- `--code-block-line-height`
- `--code-block-margin`
- `--code-block-padding`

### Content
Markdown content styling

### Cover
Docsify coverpage elements

### Navbar
Custom navigation bar styling

### Sidebar
Custom sidebar navigation styling including:
- `--sidebar-background`
- `--sidebar-width`
- `--sidebar-border-color`

## Plugin Style Support

Theme properties for popular plugins:
- Copy Code plugin
- Pagination plugin
- Search plugin
- Tabs plugin (docsify-tabs)
- Zoom Image plugin

## Integration with PrismJS

You can integrate PrismJS themes by linking to external theme stylesheets after your site theme.

## Reference

For complete documentation visit:
- [GitHub Customization Guide](https://github.com/jhildenbiddle/docsify-themeable/blob/master/docs/customization.md)
- [docsify-themeable Documentation](https://jhildenbiddle.github.io/docsify-themeable/)
