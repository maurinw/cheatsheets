# Markdown

## Headings
Use `#` for headings:
```markdown
# H1
## H2
### H3
#### H4
##### H5
###### H6
```

## Emphasis
```markdown
*Italic* or _Italic_  
**Bold** or __Bold__  
***Bold and Italic*** or ___Bold and Italic___  
~~Strikethrough~~
```

## Lists

### Unordered List
```markdown
- Item 1
- Item 2
  - Subitem 2.1
  - Subitem 2.2
```

### Ordered List
```markdown
1. First item
2. Second item
   1. Sub-item 2.1
   2. Sub-item 2.2
```

## Links
```markdown
[Inline Link](https://example.com)  
[Link with title](https://example.com "Title Text")
```

## Images
```markdown
![Alt Text](https://example.com/image.jpg)  
![Alt with title](https://example.com/image.jpg "Image Title")
```

## Code

### Inline Code
```markdown
Use `inline code` within a sentence.
```

### Code Block
\`\`\`language  
Code here  
\`\`\`

Example:

```markdown
```python
def hello():
    print("Hello, Markdown!")
```

## Blockquotes

```markdown
> This is a blockquote.
>> Nested blockquote.
```

## Tables
```markdown
| Column 1 | Column 2 | Column 3 |
|----------|----------|----------|
| Row 1    | Data     | More     |
| Row 2    | Example  | Data     |
```

## Task Lists
```markdown
- [x] Task 1
- [ ] Task 2
- [ ] Task 3
```

## Horizontal Line
```markdown
---
```

## Footnotes
```markdown
Here is a reference[^1].

[^1]: Footnote text.
```

## Escaping Special Characters
```markdown
\*Not italicized\*
```

## Automatic URL Detection
```markdown
https://example.com
```

## Extended Features (Some Markdown Flavors)

### Definition Lists (CommonMark)
```markdown
Term 1
: Definition 1

Term 2
: Definition 2
```

### Math (KaTeX or MathJax)
```markdown
Inline: $E = mc^2$

Block:
$$
\sum_{i=1}^{n} i = \frac{n(n+1)}{2}
$$
```

### Mermaid Diagrams (GitHub, Obsidian)
```markdown
```mermaid
graph TD;
    A-->B;
    A-->C;
    B-->D;
    C-->D;
```


## Keyboard Shortcuts (Markdown Editors)

| Shortcut | Action |
|----------|--------|
| `Ctrl + B` | Bold |
| `Ctrl + I` | Italic |
| `Ctrl + K` | Insert Link |
| `Ctrl + Shift + C` | Code Block |

---
