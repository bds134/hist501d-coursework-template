# Week 1 Quick Reference: VSCode, CLI & Markdown

*Use this as a reference during class and while completing assignments.*

## VSCode Essential Shortcuts

| Action | Windows/Linux | Mac |
|--------|---------------|-----|
| Command Palette | `Ctrl+Shift+P` | `Cmd+Shift+P` |
| Toggle Terminal | `Ctrl+\`` | `Cmd+\`` |
| Quick File Open | `Ctrl+P` | `Cmd+P` |
| Markdown Preview | `Ctrl+K V` | `Cmd+K V` |
| Save | `Ctrl+S` | `Cmd+S` |
| New File | `Ctrl+N` | `Cmd+N` |

## Command Line Basics

### Navigation

```bash
pwd                    # Show current directory
ls                     # List files in current directory
ls -la                 # List all files with details
cd folder-name         # Change to folder
cd ..                  # Go up one level
cd ~                   # Go to home directory
```

### File Operations

```bash
mkdir folder-name      # Create new folder
touch filename.txt     # Create new file
cp file.txt copy.txt   # Copy file
mv old.txt new.txt     # Rename/move file
rm file.txt            # Delete file
cat file.txt           # View file contents
```

### Git Basics

```bash
git status             # Check repository status
git add filename.md    # Stage a file
git add .              # Stage all changes
git commit -m "message"  # Commit with message
git push               # Push to GitHub
git pull               # Pull from GitHub
```

## Markdown Syntax Cheatsheet

### Headings

```markdown
# Heading 1
## Heading 2
### Heading 3
```

### Text Formatting

```markdown
**bold text**
*italic text*
~~strikethrough~~
`inline code` [these are backticks not apostrophe marks]
```

### Links and Images

```markdown
[Link text](https://example.com)
![Image alt text](image-url.jpg)
```

### Lists

```markdown
- Unordered list item
- Another item
  - Nested item

1. Ordered list item
2. Second item
3. Third item
```

### Code Blocks

````markdown  
```python[these are backticks not apostrophe marks]
# Code with syntax highlighting
print("Hello World")
```
````

### Blockquotes

```markdown
> This is a quote
> Multiple lines
```

### Tables

```markdown
| Header 1 | Header 2 |
|----------|----------|
| Cell 1   | Cell 2   |
| Cell 3   | Cell 4   |
```

## Common Issues & Fixes

### Git: "not recognized as a command"

- Windows: Restart VSCode after installing Git
- Check that Git is in your PATH

### Python: "command not found"

- Windows: Reinstall Python, check "Add to PATH"
- Verify with: `python --version`

### Terminal showing PowerShell instead of Bash

1. `Ctrl+Shift+P` → "Terminal: Select Default Profile"
2. Choose "Git Bash"
3. Restart terminal

## GitHub Workflow for Assignments

1. Accept GitHub Classroom assignment link
2. Clone your repository
3. Work on files locally
4. Stage changes: `git add .`
5. Commit: `git commit -m "Completed exercise 1"`
6. Push: `git push`
7. Repeat steps 3-6 frequently!

## Need More Help?

- [Markdown Guide](https://www.markdownguide.org/)
- [Git Cheatsheet](https://education.github.com/git-cheat-sheet-education.pdf)
- [VSCode Tips & Tricks](https://code.visualstudio.com/docs/getstarted/tips-and-tricks)
