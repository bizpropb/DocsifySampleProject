# Sample Page 1: Markdown Showcase

This page demonstrates various markdown features supported by Docsify.

## Text Formatting

You can make text **bold**, *italic*, or ***both***!

You can also use ~~strikethrough~~ and `inline code`.

## Lists

### Unordered Lists

- Item one
- Item two
  - Nested item A
  - Nested item B
- Item three

### Ordered Lists

1. First step
2. Second step
3. Third step
   1. Sub-step A
   2. Sub-step B

### Task Lists

- [x] Set up Docsify
- [x] Write documentation
- [ ] Deploy to production
- [ ] Share with team

## Code Blocks

### JavaScript

```javascript
function greet(name) {
  console.log(`Hello, ${name}!`);
  return `Welcome to Docsify`;
}

greet('World');
```

### Python

```python
def calculate_sum(numbers):
    """Calculate the sum of a list of numbers"""
    return sum(numbers)

result = calculate_sum([1, 2, 3, 4, 5])
print(f"Sum: {result}")
```

### Bash

```bash
# Clone repository
git clone https://github.com/user/repo.git

# Navigate to directory
cd repo

# Start local server
python -m http.server 3000
```

## Tables

| Feature | Supported | Notes |
|---------|-----------|-------|
| Search | ✅ Yes | Full-text search |
| Sidebar | ✅ Yes | Auto-generated |
| Themes | ✅ Yes | Multiple options |
| Plugins | ✅ Yes | Extensible |
| Build Required | ❌ No | Client-side rendering |

## Blockquotes

> This is a simple blockquote.
> It can span multiple lines.

> **Tip:** You can nest other markdown inside blockquotes!
>
> - Like lists
> - And `code`

## Links

- [External link](https://docsify.js.org)
- [Internal page](../getting-started.md)
- [Link to section](#text-formatting)
- [Link with title](https://github.com "GitHub Homepage")

## Images

### Inline Image

![Docsify Logo](https://docsify.js.org/_media/icon.svg)

### Image with Caption

<figure>
  <img src="https://docsify.js.org/_media/icon.svg" alt="Docsify" width="100">
  <figcaption>The Docsify mascot</figcaption>
</figure>

## Horizontal Rules

Use three or more hyphens for horizontal rules:

---

Like this!

## HTML Support

Docsify supports HTML too!

<div style="background: #f0f0f0; padding: 20px; border-radius: 8px; margin: 20px 0;">
  <h3 style="margin-top: 0;">Custom HTML Block</h3>
  <p>You can embed custom HTML for special formatting.</p>
  <button onclick="alert('Hello from Docsify!')">Click Me</button>
</div>

## Emoji Support

Thanks to the emoji plugin:

- :rocket: Rocket
- :book: Book
- :tada: Party
- :heart: Heart
- :computer: Computer
- :bulb: Idea

## Nested Lists with Code

1. **Installation**
   ```bash
   npm install docsify-cli -g
   ```

2. **Initialize**
   ```bash
   docsify init ./docs
   ```

3. **Preview**
   ```bash
   docsify serve docs
   ```

## Definition Lists

<dl>
  <dt>Docsify</dt>
  <dd>A magical documentation site generator</dd>

  <dt>Markdown</dt>
  <dd>A lightweight markup language</dd>

  <dt>GitHub Pages</dt>
  <dd>Free static site hosting from GitHub</dd>
</dl>

## Keyboard Shortcuts

Press <kbd>Ctrl</kbd> + <kbd>K</kbd> to open search (on some systems).

Use <kbd>Cmd</kbd> + <kbd>F</kbd> for browser find.

## Footnotes

Here's a sentence with a footnote[^1].

[^1]: This is the footnote content.

## Next Example

Check out [Sample Page 2](sample2.md) for more advanced features!
