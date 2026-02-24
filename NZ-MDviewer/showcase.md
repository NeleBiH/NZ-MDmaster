# NZ-MDviewer — Markdown Showcase

> **NOTE:** This file demonstrates ALL features supported by NZ-MDviewer.
> Open it in the app and check that everything renders correctly.

[TOC]

---

## 1. Headings (H1–H6)

# Heading H1 — Largest
## Heading H2 — Large
### Heading H3 — Medium
#### Heading H4 — Small
##### Heading H5 — Smaller
###### Heading H6 — Smallest

---

## 2. Basic Text Formatting

This is a regular paragraph. Each block separated by a blank line becomes a new paragraph.

**Bold text** — written with double asterisks.

*Italic text* — written with single asterisks.

***Bold and Italic together*** — combined style.

~~Strikethrough text~~ — text with a line through it.

==Highlighted text== — like a marker pen.

^Superscript^ — text above the line (e.g. E=mc^2^).

~Subscript~ — text below the line (e.g. H~2~O).

`Inline code` — for short code snippets.

<span style="color:#ff7b72">Red text</span> — HTML color inside Markdown.

<span style="color:#3fb950">Green text</span> — another color.

<span style="color:#d2a8ff">Purple text</span> — one more.

---

## 3. Horizontal Rules

Three dashes:

---

Three asterisks:

***

Three underscores:

___

---

## 4. Lists

### 4.1 Unordered List

- First item
- Second item
- Third item
  - Nested item 1
  - Nested item 2
    - Deeper nested item
    - Another deep item
  - Back to level 2
- Fourth item

With asterisks:

* Item A
* Item B
* Item C

With plus signs:

+ Plus item 1
+ Plus item 2
+ Plus item 3

### 4.2 Ordered List

1. First item
2. Second item
3. Third item
   1. Sub-item 3.1
   2. Sub-item 3.2
   3. Sub-item 3.3
4. Fourth item
5. Fifth item

### 4.3 Task List (Checkboxes)

- [x] Completed task
- [x] Another completed task
- [ ] Unfinished task
- [ ] Another unfinished task
- [x] Create showcase file
- [ ] Check all features
- [ ] Fix any issues

---

## 5. Blockquotes

> This is a simple blockquote.

> This is a longer blockquote that spans
> multiple lines of text.
> All these lines are part of the same quote.

> **Formatted blockquote**
> This quote contains *italic*, **bold** and `code`.

> Nested quotes:
> > This is a quote inside a quote.
> > > And this is even deeper.

> 💡 **Pro tip:** Blockquotes can contain almost any Markdown element!

---

## 6. Code

### 6.1 Inline Code

Use `print("Hello World")` to output text in Python.

The variable `x = 42` is an integer, and `y = "text"` is a string.

### 6.2 Code Blocks with Syntax Highlighting

**Python:**

```python
#!/usr/bin/env python3
"""Example Python code with syntax highlighting"""

from pathlib import Path
import json


class MarkdownDev:
    """A developer who loves Markdown"""

    def __init__(self, name: str, coffee: int = 5):
        self.name = name
        self.coffee = coffee
        self.stressed = False

    def write_code(self, hours: int) -> str:
        """Writes code for a given number of hours"""
        if hours > 8:
            self.stressed = True
            return f"{self.name} is stressed but the code works!"
        return f"{self.name} writes code calmly and steadily"

    def fix_bug(self, bug: str) -> bool:
        """Attempts to fix a bug"""
        # TODO: fix this bug someday
        coffees_left = self.coffee - 1
        return coffees_left > 0


# Main section
if __name__ == "__main__":
    dev = MarkdownDev("Nele", coffee=10)
    result = dev.write_code(12)
    print(result)  # Output: Nele is stressed but the code works!

    # Lambda example
    square = lambda x: x ** 2
    numbers = [1, 2, 3, 4, 5]
    squares = list(map(square, numbers))

    # Dict comprehension
    mapping = {k: v for k, v in enumerate(squares)}
    print(json.dumps(mapping, indent=2))
```

**JavaScript:**

```javascript
// ES6+ JavaScript example
const fetchData = async (url) => {
    try {
        const response = await fetch(url);

        if (!response.ok) {
            throw new Error(`HTTP error! status: ${response.status}`);
        }

        const data = await response.json();
        return data;
    } catch (error) {
        console.error('Error:', error.message);
        return null;
    }
};

// Arrow functions and destructuring
const processList = (items) => {
    return items
        .filter(({ active }) => active)
        .map(({ id, name, score }) => ({
            id,
            label: `${name} (${score}pts)`,
        }))
        .sort((a, b) => a.label.localeCompare(b.label));
};

// Class syntax
class EventEmitter {
    #listeners = new Map();

    on(event, callback) {
        if (!this.#listeners.has(event)) {
            this.#listeners.set(event, []);
        }
        this.#listeners.get(event).push(callback);
        return this;
    }

    emit(event, ...args) {
        this.#listeners.get(event)?.forEach(cb => cb(...args));
    }
}
```

**Bash/Shell:**

```bash
#!/bin/bash
# Example bash script

set -euo pipefail

APP_NAME="NZ-MDviewer"
VERSION="0.3.0"
INSTALL_DIR="$HOME/.local/bin"

echo "=== Installing $APP_NAME v$VERSION ==="

# Check dependencies
check_deps() {
    local deps=("python3" "pip" "xdg-mime")
    for dep in "${deps[@]}"; do
        if ! command -v "$dep" &> /dev/null; then
            echo "ERROR: '$dep' not found!"
            exit 1
        fi
    done
    echo "✅ All dependencies OK"
}

# Install pip packages
install_packages() {
    pip install markdown pymdown-extensions pygments \
        --break-system-packages 2>/dev/null || \
        pip install markdown pymdown-extensions pygments
}

# Main
check_deps
install_packages
echo "✅ Installation complete!"
```

**JSON:**

```json
{
    "application": "NZ-MDviewer",
    "version": "0.3.0",
    "author": "Nele",
    "dependencies": {
        "python": ">=3.9",
        "packages": [
            "markdown",
            "pymdown-extensions",
            "pygments",
            "PySide6",
            "PySide6-WebEngine"
        ]
    },
    "settings": {
        "theme": "github-auto",
        "font": "Fira Code",
        "font_size": 13,
        "auto_reload": true,
        "zoom": 1.0
    },
    "supported_formats": [".md", ".markdown", ".mdown", ".txt"]
}
```

**HTML:**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>NZ-MDviewer Showcase</title>
    <style>
        body {
            background: #0d1117;
            color: #c9d1d9;
            font-family: 'Fira Code', monospace;
        }
        .container {
            max-width: 980px;
            margin: 0 auto;
            padding: 32px;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Showcase Page</h1>
        <p>This HTML was exported from <strong>NZ-MDviewer</strong>.</p>
    </div>
</body>
</html>
```

**SQL:**

```sql
-- Example SQL query
CREATE TABLE users (
    id          SERIAL PRIMARY KEY,
    name        VARCHAR(100) NOT NULL,
    email       VARCHAR(255) UNIQUE NOT NULL,
    created_at  TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    active      BOOLEAN DEFAULT TRUE
);

-- Insert data
INSERT INTO users (name, email) VALUES
    ('Nele', 'nele@example.com'),
    ('Dev User', 'dev@example.com');

-- Complex SELECT
SELECT
    u.name,
    u.email,
    COUNT(o.id) AS order_count,
    SUM(o.amount) AS total_amount
FROM users u
LEFT JOIN orders o ON o.user_id = u.id
WHERE u.active = TRUE
    AND u.created_at > NOW() - INTERVAL '30 days'
GROUP BY u.id, u.name, u.email
HAVING COUNT(o.id) > 0
ORDER BY total_amount DESC
LIMIT 10;
```

**YAML:**

```yaml
# NZ-MDviewer configuration
app:
  name: NZ-MDviewer
  version: 0.3.0
  debug: false

ui:
  theme: github-auto
  font:
    family: "Fira Code"
    size: 13
  sidebar:
    visible: true
    width: 250

markdown:
  extensions:
    - fenced_code
    - tables
    - toc
    - admonition
    - footnotes
    - def_list
  pymdownx:
    - highlight
    - superfences
    - tasklist
    - mark
    - caret
    - tilde
    - keys
```

**Rust:**

```rust
use std::collections::HashMap;
use std::fs;

#[derive(Debug, Clone)]
struct Config {
    name: String,
    version: String,
    settings: HashMap<String, String>,
}

impl Config {
    fn new(name: &str, version: &str) -> Self {
        Config {
            name: name.to_string(),
            version: version.to_string(),
            settings: HashMap::new(),
        }
    }

    fn add_setting(&mut self, key: &str, value: &str) {
        self.settings.insert(key.to_string(), value.to_string());
    }

    fn load_from_file(path: &str) -> Result<String, std::io::Error> {
        fs::read_to_string(path)
    }
}

fn main() {
    let mut config = Config::new("NZ-MDviewer", "0.3.0");
    config.add_setting("theme", "github-auto");
    config.add_setting("font", "Fira Code");

    println!("App: {} v{}", config.name, config.version);

    match Config::load_from_file("settings.json") {
        Ok(content) => println!("Settings loaded: {} bytes", content.len()),
        Err(e) => eprintln!("Error: {}", e),
    }
}
```

---

## 7. Tables

### 7.1 Basic Table

| Column 1 | Column 2 | Column 3 |
|----------|----------|----------|
| Data     | Data     | Data     |
| More     | More     | More     |

### 7.2 Table with Alignment

| Left-aligned | Centered     | Right-aligned |
|:-------------|:------------:|-------------:|
| left 1       | center 1     | right 1       |
| left 2       | center 2     | right 2       |
| left long    | center long  | right long    |

### 7.3 Keyboard Shortcuts Table

| Action              | Shortcut       | Description                        |
|:--------------------|:---------------|:-----------------------------------|
| Open file           | `Ctrl+O`       | Open file dialog                   |
| Toggle Edit/Preview | `Ctrl+E`       | Switch between edit and preview    |
| Save                | `Ctrl+S`       | Save file in edit mode             |
| Reload              | `F5`           | Reload current file                |
| Zoom In             | `Ctrl++`       | Increase zoom                      |
| Zoom Out            | `Ctrl+-`       | Decrease zoom                      |
| Reset Zoom          | `Ctrl+0`       | Reset zoom to 100%                 |
| Sidebar             | `Ctrl+B`       | Show/hide sidebar                  |
| Back                | `Alt+←`        | Previous file                      |
| Forward             | `Alt+→`        | Next file                          |
| Split View          | `Ctrl+Shift+S` | Toggle split editor/preview        |
| Export PDF          | `Ctrl+Shift+E` | Export current file as PDF         |
| Documentation       | `F1`           | Open this documentation            |
| Quit                | `Ctrl+Q`       | Close the application              |
| Bold (editor)       | `Ctrl+B`       | Bold selected text                 |
| Italic (editor)     | `Ctrl+I`       | Italicize selected text            |
| Link (editor)       | `Ctrl+K`       | Insert a link                      |
| Code (editor)       | `Ctrl+\``      | Insert inline code                 |

### 7.4 Table with Formatted Cells

| Name         | Description                | Status      |
|:-------------|:---------------------------|:------------|
| **Bold**     | *Italic* text              | ✅ Works    |
| `Inline code`| ~~Strikethrough~~          | ✅ Works    |
| ==Highlight==| ^Super^ and ~Sub~          | ✅ Works    |
| [Link](https://github.com) | External link | ✅ Works |

---

## 8. Links

### 8.1 Inline Links

- [GitHub](https://github.com) — external link, opens in browser
- [Python documentation](https://docs.python.org) — another external link
- [PySide6](https://doc.qt.io/qtforpython-6/) — Qt documentation

### 8.2 Reference Links

This is text with a [reference link][ref1] and another [link][ref2].

[ref1]: https://github.com "GitHub"
[ref2]: https://python.org "Python"

### 8.3 Auto-links (MagicLink)

Direct URL: https://github.com/NeleBiH/NZ-MDviewer

Email address: example@example.com

### 8.4 Anchor Links (Within File)

- [Go to top](#nz-mdviewer--markdown-showcase)
- [Go to Tables](#7-tables)
- [Go to Admonitions](#11-admonitions)

### 8.5 Links to Other .md Files

- [Documentation](documentation.md) — opens inside the app!

---

## 9. Images

### 9.1 Image from URL

![Python logo](https://www.python.org/static/community_logos/python-logo.png)

### 9.2 Image with Alt Text and Title

![Placeholder image](https://via.placeholder.com/400x200/161b22/58a6ff?text=NZ-MDviewer+Showcase "Hover title here")

### 9.3 Image as Link

[![GitHub](https://github.githubassets.com/images/modules/logos_page/GitHub-Mark.png)](https://github.com/NeleBiH/NZ-MDviewer)

---

## 10. Footnotes

This is a sentence with a footnote[^1].

This is another sentence with a longer footnote[^long].

You can have multiple footnotes in one document[^2].

[^1]: This is a short footnote.

[^long]: This is a longer footnote that can contain more text,
    even across multiple lines when properly indented.

    It can even have multiple paragraphs!

[^2]: Third footnote with `inline code`.

---

## 11. Admonitions

### Note

!!! note "Note"
    This is a **note** admonition block. Use it for general information
    the reader should know but that isn't critical.

### Warning

!!! warning "Watch out!"
    This is a **warning** admonition. Use it when something could go
    wrong or the reader needs to be careful.

### Danger

!!! danger "Danger!"
    This is a **danger** admonition. Use it for critical warnings
    that could cause data loss or serious problems.

### Tip

!!! tip "Pro Tip"
    This is a **tip** admonition. Use it for helpful hints
    and tricks that make your workflow easier.

### Without Title

!!! note
    Admonition without a title — uses the default type name.

---

## 12. Definition Lists

Markdown
:   A lightweight markup language used for formatting text.
:   Created by John Gruber in 2004.

NZ-MDviewer
:   A desktop application for viewing and editing Markdown files.
:   Written in Python with the PySide6 framework.
:   Uses a GitHub-style theme with automatic light/dark mode.

PyMdown Extensions
:   A collection of extensions for the Python Markdown parser.
:   Adds advanced features like task lists, highlighting, and more.

Syntax Highlighting
:   Visual differentiation of code parts using colors.
:   Implemented through the Pygments library.

---

## 13. Abbreviations

This works using the HTML and CSS specifications.

We use the MD format for documentation.

The app is built with the QT framework.

*[HTML]: HyperText Markup Language
*[CSS]: Cascading Style Sheets
*[MD]: Markdown
*[QT]: Qt Cross-Platform Framework

---

## 14. Keyboard Keys

Shortcuts in NZ-MDviewer:

- ++ctrl+o++ to open a file
- ++ctrl+e++ to toggle Edit/Preview mode
- ++ctrl+s++ to save in edit mode
- ++f5++ to reload
- ++ctrl+plus++ and ++ctrl+minus++ for zoom
- ++ctrl+0++ to reset zoom
- ++ctrl+b++ to toggle sidebar (in preview mode)
- ++alt+left++ and ++alt+right++ for navigation
- ++ctrl+shift+s++ to toggle split view
- ++f1++ to open documentation
- ++ctrl+q++ to quit

In the editor:
- ++ctrl+b++ for **bold**
- ++ctrl+i++ for *italic*
- ++ctrl+k++ for a link
- ++ctrl+grave++ for `code`

---

## 15. HTML Inside Markdown (md_in_html)

<div markdown="1" style="background:#161b22; border:1px solid #30363d; border-radius:8px; padding:16px; margin:16px 0;">

### HTML Container with Markdown

This is **Markdown text** inside an HTML `<div>` element.

- List inside HTML
- Works perfectly!

```python
print("Code inside HTML works too!")
```

</div>

<details>
<summary>Click for details (HTML details element)</summary>

This is hidden content inside a `<details>` HTML tag.

It can contain **Markdown** formatting!

```bash
echo "Even code blocks!"
```

</details>

---

## 16. Special Characters and Symbols

### 16.1 Smart Quotes (Smarty Extension)

"Double quotes" become smart quotes.

'Single quotes' too.

### 16.2 Smart Dashes

En dash: exchange rate is 1.95--2.00

Em dash: NZ-MDviewer---the best MD viewer

### 16.3 Unicode and Emoji

Arrows: → ← ↑ ↓ ↔ ⇒ ⇐ ⇑ ⇓

Math: ± × ÷ ≠ ≈ ≤ ≥ ∞ √ ∑ ∏ ∫

Symbols: © ® ™ ° † ‡ § ¶ • …

Greek: α β γ δ ε π σ μ λ Ω

Emoji: 😀 😎 🎉 🔥 ⭐ 💡 ✅ ❌ ⚠️ 📝

---

## 17. Nested Structures

### 17.1 List with Blockquote and Code

1. First item

   > This is a blockquote inside the first list item.

2. Second item

   ```python
   # Code inside a list item
   x = "nested"
   print(x)
   ```

3. Third item

### 17.2 Table with Code in Cells

| Extension    | Syntax                | Example              |
|:-------------|:----------------------|:---------------------|
| Bold         | `**text**`            | **bold**             |
| Italic       | `*text*`              | *italic*             |
| Strike       | `~~text~~`            | ~~struck~~           |
| Highlight    | `==text==`            | ==highlight==        |
| Superscript  | `^text^`              | E=mc^2^              |
| Subscript    | `~text~`              | H~2~O                |
| Inline code  | `` `text` ``          | `code`               |
| Code block   | ` ```lang `           | (see examples above) |
| Link         | `[t](url)`            | [link](https://github.com) |
| Image        | `![alt](url)`         | (see above)          |
| Task list    | `- [x] task`          | - [x] done           |
| Footnote     | `[^1]`                | text[^note]          |
| Definition   | `: definition`        | (see above)          |
| Admonition   | `!!! note`            | (see above)          |
| Keyboard key | `++ctrl+s++`          | ++ctrl+s++           |

[^note]: This is a footnote from the table.

---

## 18. Edge Cases

### 18.1 Long Line Without Wrapping

```
this_is_a_very_long_line_that_tests_horizontal_scrolling_in_code_blocks_and_checks_that_it_displays_correctly_without_text_wrapping
```

### 18.2 Empty Cells in Table

| Column A | Column B | Column C |
|----------|----------|----------|
| Data     |          | Data     |
|          | Data     |          |
| Data     | Data     | Data     |

### 18.3 List with Paragraphs Between Items

- **Item 1** — short item

- **Item 2** — this item has a paragraph below it

  This is a paragraph that belongs to item 2. It must be indented with four spaces or one tab.

- **Item 3** — short again

### 18.4 Code Block with Explanation

Install packages:

```bash
pip install markdown pymdown-extensions pygments
```

Run the app:

```bash
python3 NZ-MDviewer/NZ-MDviewer.py
# or open a specific file
python3 NZ-MDviewer/NZ-MDviewer.py /path/to/file.md
```

### 18.5 Math Examples with Formatting

Circle area: A = π × r^2^

Pythagorean theorem: a^2^ + b^2^ = c^2^

Water: H~2~O

Carbon dioxide: CO~2~

Voltage: U = I × R (where R ≈ 47 Ω)

---

## 19. More Language Examples

**TypeScript:**

```typescript
interface MarkdownConfig {
    extensions: string[];
    theme: 'dark' | 'light';
    fontSize: number;
    autoReload: boolean;
}

async function renderMarkdown(
    content: string,
    config: MarkdownConfig
): Promise<string> {
    const { extensions, theme, fontSize } = config;

    // Type guard
    if (!content || typeof content !== 'string') {
        throw new TypeError('Content must be a string');
    }

    return `<html class="${theme}">${content}</html>`;
}

// Generic function
function filterMap<T, U>(
    arr: T[],
    predicate: (item: T) => boolean,
    transform: (item: T) => U
): U[] {
    return arr.filter(predicate).map(transform);
}
```

**CSS:**

```css
/* GitHub theme with auto light/dark */
:root {
    --bg-primary: #ffffff;
    --text-primary: #1f2328;
    --text-link: #0969da;
    --border: #d0d7de;
}

@media (prefers-color-scheme: dark) {
    :root {
        --bg-primary: #0d1117;
        --text-primary: #c9d1d9;
        --text-link: #58a6ff;
        --border: #30363d;
    }
}

body {
    background-color: var(--bg-primary);
    color: var(--text-primary);
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
    font-size: 16px;
    line-height: 1.6;
}

code {
    background-color: rgba(110, 118, 129, 0.4);
    border-radius: 6px;
    padding: 0.2em 0.4em;
    font-family: 'Fira Code', monospace;
}
```

**Go:**

```go
package main

import (
    "fmt"
    "os"
    "strings"
)

type MarkdownViewer struct {
    CurrentFile string
    History     []string
    HistIndex   int
}

func NewViewer() *MarkdownViewer {
    return &MarkdownViewer{
        History:   make([]string, 0),
        HistIndex: -1,
    }
}

func (v *MarkdownViewer) LoadFile(path string) error {
    content, err := os.ReadFile(path)
    if err != nil {
        return fmt.Errorf("cannot load file %s: %w", path, err)
    }

    v.CurrentFile = path
    v.History = append(v.History[:v.HistIndex+1], path)
    v.HistIndex++

    lines := strings.Split(string(content), "\n")
    fmt.Printf("Loaded %d lines from %s\n", len(lines), path)
    return nil
}

func main() {
    viewer := NewViewer()
    if err := viewer.LoadFile("showcase.md"); err != nil {
        fmt.Fprintf(os.Stderr, "Error: %v\n", err)
        os.Exit(1)
    }
}
```

---

## 20. Drag & Drop and Navigation Test

!!! tip "Drag & Drop Test"
    Drag any `.md` or `.txt` file directly onto the app window.
    The app should automatically load and display that file.

!!! tip "Navigation Test"
    1. Open this file
    2. Click the [Documentation](documentation.md) link above
    3. Press ++alt+left++ to come back here
    4. Press ++alt+right++ to go to Documentation again

!!! tip "Auto-Reload Test"
    1. Open this file in the app
    2. Edit it in another editor (nano, vim, gedit, etc.)
    3. Save the change
    4. The app should automatically refresh the preview (~300ms)

---

## 21. Edit Mode Test

!!! note "How to Test Edit Mode"
    1. Press ++ctrl+e++ or click the **✏️ Edit** button in the toolbar
    2. You'll see the editor with syntax highlighting and line numbers
    3. In the editor toolbar you can click:
        - **B** for Bold
        - **I** for Italic
        - **S̶** for Strikethrough
        - **H1/H2/H3** for headings
        - **Link** to insert a link
        - **Img** to insert an image
        - **</>** for code
        - **- List** for a bullet list
        - **1. List** for a numbered list
        - **Table** to insert a table
        - **---** for a horizontal rule
        - **> Quote** for a blockquote
        - **Font** (spinner) to change font size
        - **Color** for HTML colored text
        - **Ω** for special characters
    4. Press ++ctrl+s++ to save
    5. Press ++ctrl+e++ again to return to Preview

---

## 22. Split View Test

!!! tip "How to Use Split View"
    1. Open a `.md` file
    2. Press ++ctrl+shift+s++ or click **⊟ Split** in the toolbar
    3. The editor appears on the left, live preview on the right
    4. Type in the editor — the preview updates after 400ms
    5. Press ++ctrl+shift+s++ again to exit Split View (file is saved automatically)

---

## 23. Search Test

Use the search field in the toolbar (🔍) to search:

- Search: `NZ-MDviewer` — should find many results
- Search: `admonition` — should find it in section 11
- Search: `xyz_does_not_exist` — should show "not found" message
- Search: `python` — should find in code blocks (case insensitive)

---

## 24. Context Menu Test

Right-click on the preview area — the menu should show:

- **Open Link in Browser** (only when cursor is over a link)
- **Copy Link URL** (only when cursor is over a link)
- **Copy Selected Text** (only when text is selected)
- **Select All**
- **Open in Browser** (renders current file in default browser)
- **Zoom In / Zoom Out / Reset Zoom**
- **Reload**

---

## 25. Feature Summary

| Category          | Elements                                           | Status  |
|:------------------|:---------------------------------------------------|:-------:|
| Headings          | H1, H2, H3, H4, H5, H6                            | 📋 Test |
| Formatting        | Bold, Italic, Strike, Highlight, Super, Sub        | 📋 Test |
| Code              | Inline, Fenced (10 languages), Syntax Highlighting | 📋 Test |
| Lists             | Ordered, Unordered, Task list, Nested              | 📋 Test |
| Tables            | Basic, Alignment, Formatted cells                  | 📋 Test |
| Blockquotes       | Simple, Nested, Formatted                          | 📋 Test |
| Links             | Inline, Reference, Auto, Anchor, .md files         | 📋 Test |
| Images            | URL, with title, as link                           | 📋 Test |
| Footnotes         | Short, Long, with code                             | 📋 Test |
| Admonitions       | Note, Warning, Danger, Tip                         | 📋 Test |
| Definition Lists  | Simple and multiple definitions                    | 📋 Test |
| Abbreviations     | Hover tooltip on abbreviations                     | 📋 Test |
| Keyboard Keys     | ++ctrl+s++ and other shortcuts                     | 📋 Test |
| HTML in MD        | `<div>`, `<details>`, `<span style>`               | 📋 Test |
| Smart Typography  | Quotes, Dashes, Ellipsis                           | 📋 Test |
| Unicode/Emoji     | Arrows, Math, Symbols, Emoji                       | 📋 Test |
| Horizontal Rules  | ---, ***, ___                                      | 📋 Test |
| TOC               | Auto-generated Table of Contents                   | 📋 Test |
| Edit Mode         | Editor, Toolbar, Shortcuts, Save                   | 📋 Test |
| Split View        | Side-by-side with live preview                     | 📋 Test |
| Search            | Search with highlight                              | 📋 Test |
| Context Menu      | Right-click options                                | 📋 Test |
| Auto-Reload       | File change detection                              | 📋 Test |
| Drag & Drop       | Dragging .md and .txt files                        | 📋 Test |
| Navigation        | Back/Forward history                               | 📋 Test |
| Zoom              | In, Out, Reset, Default setting                    | 📋 Test |
| Sidebar           | Show/hide, change folder                           | 📋 Test |
| PDF Export        | Ctrl+Shift+E                                       | 📋 Test |
| Documentation     | F1 opens this guide                                | 📋 Test |

---

*NZ-MDviewer v0.3.0 — Showcase file for complete feature testing* 🚀

*Built with ☕ and Python*
