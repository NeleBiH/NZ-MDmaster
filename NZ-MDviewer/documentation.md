# NZ-MDviewer — Documentation

> **Version 0.3.0** · Desktop Markdown Editor & Viewer for Linux

---

## Table of Contents

1. [Introduction](#introduction)
2. [Installation](#installation)
3. [Getting Started](#getting-started)
4. [File Browser](#file-browser)
5. [Markdown Preview](#markdown-preview)
6. [Editor](#editor)
7. [Split View](#split-view)
8. [Search](#search)
9. [PDF Export](#pdf-export)
10. [Navigation History](#navigation-history)
11. [Settings](#settings)
12. [Keyboard Shortcuts](#keyboard-shortcuts)
13. [Markdown Syntax Reference](#markdown-syntax-reference)
14. [Troubleshooting](#troubleshooting)

---

## Introduction

**NZ-MDviewer** is a desktop Markdown editor and viewer for Linux. It renders Markdown files with a GitHub-style theme that automatically follows your system's light or dark mode, and includes a built-in syntax-highlighted editor with live preview.

### Key features at a glance

- Renders Markdown with **GitHub Light / Dark theme** (follows system theme automatically)
- **Split View** — edit and preview side by side with live updates
- **Syntax-highlighted editor** with line numbers (Fira Code)
- **File Browser** — navigate your filesystem without leaving the app
- **PDF Export**, **Auto-Reload**, **Recent Files**, **Word Count**
- **Desktop integration** — opens `.md` files from Dolphin, Nautilus, etc.

---

## Installation

### Requirements

**Arch / CachyOS / Manjaro:**
```bash
sudo pacman -S pyside6 qt6-webengine python
```

**Debian / Ubuntu:**
```bash
sudo apt install python3-pyside6.qtwebenginewidgets python3-pyside6.qtwebengine
```

Python packages (`markdown`, `pymdown-extensions`, `pygments`) are installed automatically by the installer.

### Install

```bash
git clone https://github.com/NeleBiH/NZ-MDviewer.git
cd NZ-MDviewer
chmod +x install_uninstall.sh
./install_uninstall.sh --install
```

### Update

```bash
./install_uninstall.sh --update
```

Settings are preserved across updates.

### Uninstall

```bash
./install_uninstall.sh --uninstall
```

---

## Getting Started

After installation, launch NZ-MDviewer from your app menu or terminal:

```bash
# Open the file browser
nzmdviewer

# Open a specific file directly
nzmdviewer /path/to/file.md
```

You can also:
- **Double-click** a `.md` file in your file manager (Dolphin, Nautilus, Thunar)
- **Right-click → Open With → NZ-MDviewer**
- **Drag and drop** a `.md` or `.txt` file onto the app window

---

## File Browser

The **left panel** is a file browser (sidebar) showing all `.md`, `.markdown`, `.mdown`, and `.txt` files.

| Action | Result |
|--------|--------|
| Click a file | Opens and previews the file |
| Ctrl+B | Toggle sidebar on/off |
| File → Change Folder | Change the root folder shown in the browser |

> **Tip:** The sidebar width is remembered between sessions. Drag the divider between the sidebar and preview to resize it.

---

## Markdown Preview

The main area shows your Markdown rendered as HTML with a **GitHub-style theme** that automatically switches between light and dark mode based on your system preferences.

### Zoom

| Action | Shortcut |
|--------|----------|
| Zoom in | Ctrl++ |
| Zoom out | Ctrl+- |
| Reset zoom | Ctrl+0 |
| Right-click → Zoom | Context menu |

The default zoom level can be set in **Settings → Preview → Default Zoom**.

### Auto-Reload

When another application modifies the currently open file, NZ-MDviewer detects the change and reloads automatically (with 300ms debounce). This can be toggled in **Settings → Preview → Auto-Reload**.

Press **F5** or **View → Reload** to reload manually at any time.

### Context Menu (Right-click)

Right-clicking in the preview area shows options:

- **Open Link in Browser** — for external links
- **Copy Link URL**
- **Copy Selected Text**
- **Select All**
- **Open in Browser** — opens the current file rendered in your default web browser
- **Zoom In / Out / Reset**
- **Reload**

---

## Editor

Press **Ctrl+E** or click the **✏️ Edit** toolbar button to switch to editor mode. The editor features:

- Syntax highlighting for Markdown syntax
- Line numbers
- Fira Code monospace font
- Formatting toolbar

### Saving

| Action | Shortcut |
|--------|----------|
| Save | Ctrl+S |
| Save and return to preview | Ctrl+E (toggle back) |

### Formatting Toolbar

The editor toolbar provides one-click insertion of common Markdown elements:

| Button | Inserts |
|--------|---------|
| **B** | Bold — `**text**` |
| *I* | Italic — `*text*` |
| ~~S~~ | Strikethrough — `~~text~~` |
| H1 / H2 / H3 | Headings |
| Link | `[text](url)` |
| Img | `![alt](url)` |
| `</>` | Inline code or fenced code block |
| - List | Bullet list |
| 1. List | Numbered list |
| Table | 3×2 table template |
| --- | Horizontal rule |
| > Quote | Blockquote |
| Font: Npx | Change editor font size |
| Color | Insert colored text span |
| Ω | Special characters (arrows, math, Greek, symbols, emoji) |

> **Tip:** Select text first, then click a formatting button — it wraps the selection instead of inserting empty markup.

### Editor Keyboard Shortcuts

| Shortcut | Action |
|----------|--------|
| Ctrl+B | Bold |
| Ctrl+I | Italic |
| Ctrl+K | Insert Link |
| Ctrl+\` | Inline Code |

---

## Split View

Split View shows the **editor on the left** and the **live preview on the right** at the same time.

| Action | Shortcut |
|--------|----------|
| Toggle Split View | Ctrl+Shift+S |
| Split View button | ⊟ Split in toolbar |

The preview updates **400ms after you stop typing** (debounce), keeping it fast without flickering on every keystroke.

When you exit Split View, the file is saved automatically and you return to Preview mode.

---

## Search

Use the **search field** in the toolbar (or click into it and type) to search for text in the currently open file.

1. Type your search term in the search box
2. Press **Enter**
3. All matches are highlighted in yellow in the preview
4. The view scrolls to the first match
5. The status bar shows how many matches were found

> **Note:** Search is case-insensitive and supports plain text. The file reloads before searching to clear any previous highlights.

---

## PDF Export

Export the current file as a PDF:

- **File → Export as PDF** (Ctrl+Shift+E)

The PDF is generated from the rendered HTML (with the current theme and zoom level), so what you see is what you get.

---

## Navigation History

NZ-MDviewer tracks which files you've opened and lets you navigate between them like a web browser.

| Action | Shortcut |
|--------|----------|
| Go back | Alt+Left or ◀ Back button |
| Go forward | Alt+Right or ▶ Fwd button |

The Back/Forward buttons are disabled when there is nothing to navigate to.

---

## Settings

Open settings with **Settings → Preferences**.

### Language

Switch between **English** and **Bosanski / Hrvatski / Srpski**. Language change requires a restart.

### Sidebar

| Option | Description |
|--------|-------------|
| Show sidebar | Toggle sidebar visibility |
| Auto-hide sidebar | *(reserved for future use)* |
| Remember sidebar position | Saves the sidebar width between sessions |

### Preview

| Option | Description |
|--------|-------------|
| Auto-Reload | Reload file when it changes on disk |
| Default Zoom | Zoom factor applied on startup (e.g. 1.2 = 120%) |

Settings are stored at:
```
~/.local/share/nzmdviewer/settings.json
```

---

## Keyboard Shortcuts

### Global

| Shortcut | Action |
|----------|--------|
| Ctrl+O | Open file |
| Ctrl+S | Save (in editor) |
| Ctrl+E | Toggle Edit / Preview |
| Ctrl+Shift+S | Toggle Split View |
| Ctrl+Shift+E | Export as PDF |
| Ctrl+B | Toggle sidebar |
| Ctrl++ | Zoom in |
| Ctrl+- | Zoom out |
| Ctrl+0 | Reset zoom |
| Alt+Left | Back |
| Alt+Right | Forward |
| F5 | Reload current file |
| Ctrl+Q | Quit |

### Editor only

| Shortcut | Action |
|----------|--------|
| Ctrl+B | Bold |
| Ctrl+I | Italic |
| Ctrl+K | Insert Link |
| Ctrl+\` | Inline Code |

---

## Markdown Syntax Reference

A quick reference for the Markdown features supported by NZ-MDviewer.

### Text Formatting

```markdown
**bold**
*italic*
~~strikethrough~~
`inline code`
==highlighted==
^^superscript^^
~subscript~
```

### Headings

```markdown
# Heading 1
## Heading 2
### Heading 3
#### Heading 4
```

### Links and Images

```markdown
[Link text](https://example.com)
![Alt text](image.png)
```

### Lists

```markdown
- Unordered item
- Another item
  - Nested item

1. First
2. Second
3. Third
```

### Task Lists

```markdown
- [x] Done
- [ ] Not done
```

### Code Blocks

````markdown
```python
def hello():
    print("Hello, World!")
```
````

### Tables

```markdown
| Column 1 | Column 2 | Column 3 |
|----------|----------|----------|
| Cell A   | Cell B   | Cell C   |
| Cell D   | Cell E   | Cell F   |
```

### Blockquotes

```markdown
> This is a blockquote.
> It can span multiple lines.
```

### Horizontal Rule

```markdown
---
```

### Footnotes

```markdown
Here is a footnote reference.[^1]

[^1]: Here is the footnote.
```

### Admonitions

```markdown
!!! note
    This is a note.

!!! warning
    This is a warning.
```

---

## Troubleshooting

### App doesn't open (icon bounces, nothing appears)

**Cause:** Virtual environment broken after a Python upgrade.

**Fix:**
```bash
rm -rf ~/.local/share/nzmdviewer/venv
~/.local/share/nzmdviewer/install_uninstall.sh --update
```

### PySide6-WebEngine not available (Python 3.14+)

PySide6-WebEngine from pip doesn't support Python 3.14+.

**Fix:** Use `--system-site-packages` to inherit the system PySide6:
```bash
python3 -m venv --system-site-packages ~/.local/share/nzmdviewer/venv
~/.local/share/nzmdviewer/venv/bin/pip install markdown pymdown-extensions pygments
```

**Arch/CachyOS:**
```bash
sudo pacman -S pyside6 qt6-webengine
```

### `.md` files don't open from file manager

```bash
update-desktop-database ~/.local/share/applications/
xdg-mime default nzmdviewer.desktop text/markdown
xdg-mime default nzmdviewer.desktop text/x-markdown
```

You may need to re-login or restart your file manager.

### App crashes without a message

Run from terminal to see the error:
```bash
nzmdviewer /path/to/file.md
```

### Preview doesn't render (blank white page)

Check WebEngine:
```bash
python3 -c "from PySide6.QtWebEngineWidgets import QWebEngineView; print('OK')"
```

If it fails, install `qt6-webengine` (`sudo pacman -S qt6-webengine` on Arch).

---

*NZ-MDviewer · Developed by Nele + Claude AI · MIT License*
