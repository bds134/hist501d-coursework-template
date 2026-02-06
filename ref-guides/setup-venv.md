# Create a Python virtual environment at `.venv`

## What is a venv and why use one?

A venv (virtual environment) is a self-contained folder that holds a specific Python interpreter and the exact set of libraries your project needs. Think of it like a private reading room or archive box for a single research project: all the editions, notes, and tools you need are kept together and separate from other projects.

Why you want a venv:

- Isolation: Different projects can use different library versions without clashing (no more "it worked on my machine" surprises).
- Reproducibility: You can recreate the same software setup later or share it with collaborators so analyses behave predictably.
- Safety: Installing or upgrading packages in a venv avoids changing system-wide Python and other projects.
- Clean project packaging: It’s easy to record exactly what you used (e.g., requirements.txt) so your methods are transparent and archivable.

When to use:

- Anytime you run scripts for text analysis, data cleaning, GIS, or other digital methods tied to a specific research project.
- Especially useful before sharing code or publishing so readers can reproduce your computational steps.

## Prerequisites: Python 3 installed

Purpose: Before creating or activating a virtual environment, you need to run commands from the project's main folder so files are created in the right place.

## Project root

1. Open a terminal in the project root.

The **project root** is the top-level folder of your repository—the one that contains files like README.md, .git (sometimes), or this ref-guides folder.

How to get there:

- In VS Code: open the project folder, View → Terminal (or Ctrl+`). Select Git Bash as the terminal profile (use the terminal dropdown → "Select Default Profile" → "Git Bash"; Mac users can use Zsh) and open a new terminal — it will be started in the project folder.

How to check: list files (`ls` or `dir`) and look for project files (README.md, this repo folder). If you see them, you are in the correct location and can proceed with the next steps.

2. Create the venv
```bash
python3 -m venv .venv
```

3. Activate the venv
```bash
source .venv/bin/activate
```

4. Verify and update pip
```bash
python -V
python -m pip install --upgrade pip
```

5. Install dependencies

Dependencies are the Python libraries your project needs to run. They are often listed in a `requirements.txt` file. To install them, run:

```bash
pip install -r requirements.txt
```

6. (Optional) Freeze current packages

'Freeze' is used to capture the current state of installed packages in the venv. This is useful for sharing with collaborators or for future reference when you want to recreate the same environment.

To save current packages:
```bash
pip freeze > requirements.txt
```

7. (Optional) Deactivate

When you're done working in the venv, you can deactivate it to return to your system's default Python environment:

```bash
deactivate
```

8. Ignore the venv in git

'gitignore' is a file that tells Git which files or folders to ignore when you commit changes. Since the venv can be large and is specific to your local setup, it's best practice to exclude it from version control.

Add to `.gitignore`:
```
.venv/
```

## Python: "command not found"

- Windows: Reinstall Python, check "Add to PATH"
- Verify with: `python --version`
