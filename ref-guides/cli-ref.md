# CLI Reference

*Quick reference for command line interface (CLI) commands and operations.*

## Navigation

```bash
pwd                    # Show current directory
ls                     # List files in current directory
ls -la                 # List all files with details
cd folder-name         # Change to folder
cd ..                  # Go up one level
cd ~                   # Go to home directory
```

## File Operations

```bash
mkdir folder-name      # Create new folder
touch filename.txt     # Create new file
cp file.txt copy.txt   # Copy file
mv old.txt new.txt     # Rename/move file
rm file.txt            # Delete file
cat file.txt           # View file contents
```

## Terminal showing PowerShell instead of Bash

1. `Ctrl+Shift+P` → "Terminal: Select Default Profile"
2. Choose "Git Bash"
3. Restart terminal

## Set bash as default shell in VS Code

1. `Ctrl+Shift+P` → "Terminal: Select Default Profile"
2. Choose "Git Bash"
3. Restart terminal
4. To make it permanent: `Ctrl+Shift+P` → "Preferences: Open Settings (JSON)" → add `"terminal.integrated.defaultProfile.windows": "Git Bash"` to the JSON file and save. Restart VS Code.

Now every new terminal will open with Git Bash by default. You can still switch to PowerShell or other shells from the terminal dropdown if needed.

## Need More Help?

- [VSCode Tips & Tricks](https://code.visualstudio.com/docs/getstarted/tips-and-tricks)
- [Command Line Crash Course](https://learnpythonthehardway.org/book/appendixa.html)
