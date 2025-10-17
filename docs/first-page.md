# Your First Page

Let's create your first documentation page!

## Creating a New Page

It's as simple as creating a new markdown file:

```bash
# In your docs/ folder
echo "# My First Page" > my-page.md
echo "This is my content!" >> my-page.md
```

That's it! The page is now accessible at `http://yoursite.com/#/my-page`

## Adding to Sidebar

To make it appear in the navigation, edit `_sidebar.md`:

```markdown
* [Home](/)
* [My First Page](my-page.md)  <!-- Add this line -->
```

## Markdown Basics

Docsify supports all standard markdown syntax:

### Headings

```markdown
# H1 Heading
## H2 Heading
### H3 Heading
```

### Text Formatting

```markdown
**bold text**
*italic text*
~~strikethrough~~
`inline code`
```

### Lists

```markdown
* Unordered item 1
* Unordered item 2
  * Nested item

1. Ordered item 1
2. Ordered item 2
```

### Links

```markdown
[Link text](url)
[Internal page link](other-page.md)
[Link to section](#section-heading)
```

### Code Blocks

    ```javascript
    function hello() {
      console.log("Hello world!");
    }
    ```

### Tables

```markdown
| Column 1 | Column 2 | Column 3 |
|----------|----------|----------|
| Data 1   | Data 2   | Data 3   |
```

### Blockquotes

```markdown
> This is a blockquote
> It can span multiple lines
```

### Images

```markdown
![Alt text](image-url.png)
```

## Docsify-Specific Features

### Alerts

```markdown
> [!NOTE]
> This is a note

> [!TIP]
> This is a tip

> [!WARNING]
> This is a warning
```

### Task Lists

```markdown
- [x] Completed task
- [ ] Incomplete task
- [ ] Another task
```

## Organizing Content

### Subdirectories

You can organize pages in folders:

```
docs/
├── guide/
│   ├── basics.md
│   └── advanced.md
└── api/
    ├── endpoints.md
    └── authentication.md
```

Reference them in `_sidebar.md`:

```markdown
* Guide
  * [Basics](guide/basics.md)
  * [Advanced](guide/advanced.md)
```

## Live Reloading

When you're running a local server:

1. Edit your markdown file
2. Save it
3. Refresh your browser
4. See changes instantly!

No build step needed!

## Tips for Good Documentation

### DO:
- ✅ Use clear, descriptive headings
- ✅ Break content into small sections
- ✅ Include code examples
- ✅ Add a table of contents for long pages
- ✅ Use lists and tables for clarity

### DON'T:
- ❌ Create walls of text
- ❌ Forget to test your links
- ❌ Skip explaining complex concepts
- ❌ Use jargon without defining it

## Next Steps

- [Configure basic settings](config-basic.md) →
- [Add more plugins](config-plugins.md) →
- [Customize the theme](config-themes.md) →
