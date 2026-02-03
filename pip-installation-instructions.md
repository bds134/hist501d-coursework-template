# Pip Installation Instructions for HIST 501D

## What is Pip?

Pip is Python's package installer - it's how you install additional Python libraries and tools (like Jupyter notebooks). Most modern Python installations include pip automatically, but if you don't have it, these instructions will help you get it installed.

## Table of Contents

- [Pip Installation Instructions for HIST 501D](#pip-installation-instructions-for-hist-501d)
  - [What is Pip?](#what-is-pip)
  - [Table of Contents](#table-of-contents)
  - [Checking if Pip is Already Installed](#checking-if-pip-is-already-installed)
  - [macOS Setup](#macos-setup)
    - [If Python is already installed](#if-python-is-already-installed)
    - [If Python is not installed](#if-python-is-not-installed)
  - [Windows Setup](#windows-setup)
    - [If Python is already installed](#if-python-is-already-installed-1)
    - [If Python is not installed](#if-python-is-not-installed-1)
  - [Upgrading Pip](#upgrading-pip)
  - [Using Pip in a Virtual Environment](#using-pip-in-a-virtual-environment)
  - [Installing Jupyter Notebook](#installing-jupyter-notebook)
  - [Troubleshooting](#troubleshooting)
    - ["pip: command not found" or "'pip' is not recognized"](#pip-command-not-found-or-pip-is-not-recognized)
    - ["externally-managed-environment" error](#externally-managed-environment-error)
    - [Permission/Access Denied Errors](#permissionaccess-denied-errors)
    - [Pip installs packages but they can't be imported](#pip-installs-packages-but-they-cant-be-imported)
  - [Need Help?](#need-help)

---

## Checking if Pip is Already Installed

Before installing pip, check if you already have it:

1. Open a terminal in VS Code (see [git-installation-instructions.md](git-installation-instructions.md) for how to open a terminal)

2. Type the following command and press Enter:
   ```bash
   pip --version
   ```
   or
   ```bash
   pip3 --version
   ```

3. If you see version information (e.g., `pip 24.0 from ...`), **pip is already installed!** You can skip to [Upgrading Pip](#upgrading-pip).

4. If you get an error like `command not found` or `is not recognized`, continue with the installation instructions below.

---

## macOS Setup

### If Python is already installed

Most Macs come with Python pre-installed. If `python3 --version` works, use this method:

1. Open Terminal in VS Code

2. Run the following command:
   ```bash
   python3 -m ensurepip --upgrade
   ```

3. Verify installation:
   ```bash
   pip3 --version
   ```

4. (Optional) Create an alias so you can use `pip` instead of `pip3`:
   ```bash
   echo 'alias pip="pip3"' >> ~/.zshrc
   source ~/.zshrc
   ```

### If Python is not installed

1. Install Homebrew if you haven't already (see [git-installation-instructions.md](git-installation-instructions.md))

2. Install Python (which includes pip):
   ```bash
   brew install python
   ```

3. Verify installation:
   ```bash
   python3 --version
   pip3 --version
   ```

---

## Windows Setup

### If Python is already installed

1. Open a terminal in VS Code (preferably PowerShell or Command Prompt)

2. Check if Python is installed:
   ```bash
   python --version
   ```

3. If Python is installed, install/repair pip:
   ```bash
   python -m ensurepip --upgrade
   ```

4. Verify installation:
   ```bash
   pip --version
   ```

### If Python is not installed

1. Download Python from [python.org/downloads](https://www.python.org/downloads/)

2. **Important:** During installation:
   - ✅ Check "Add Python to PATH"
   - ✅ Check "Install pip"
   - Click "Install Now"

3. After installation, open a **new** terminal in VS Code

4. Verify installation:
   ```bash
   python --version
   pip --version
   ```

---

## Upgrading Pip

It's a good idea to upgrade pip to the latest version:

**macOS:**
```bash
pip3 install --upgrade pip
```

**Windows:**
```bash
python -m pip install --upgrade pip
```

---

## Using Pip in a Virtual Environment

For this course, you'll often work in a virtual environment (a isolated Python setup for your project). Here's how to use pip with it:

1. **Activate your virtual environment first:**

   **macOS/Linux:**
   ```bash
   source .venv/bin/activate
   ```

   **Windows (Git Bash):**
   ```bash
   source .venv/Scripts/activate
   ```

   **Windows (PowerShell):**
   ```bash
   .venv\Scripts\Activate.ps1
   ```

   **Windows (Command Prompt):**
   ```bash
   .venv\Scripts\activate.bat
   ```

2. **You should see `(.venv)` at the beginning of your terminal prompt**

3. **Now install packages:**
   ```bash
   pip install package-name
   ```

4. **To deactivate when done:**
   ```bash
   deactivate
   ```

---

## Installing Jupyter Notebook

Once pip is installed, you can install Jupyter:

```bash
pip install jupyter notebook
```

Or if using a virtual environment:

```bash
source .venv/Scripts/activate  # Windows Git Bash
pip install jupyter notebook
```

To verify Jupyter is installed:
```bash
jupyter --version
```

---

## Troubleshooting

### "pip: command not found" or "'pip' is not recognized"

**Try these alternatives:**
```bash
python -m pip --version
```
or
```bash
python3 -m pip --version
```

If these work, you can use `python -m pip install package-name` instead of `pip install package-name`.

**If nothing works:**
- Make sure Python is in your PATH (reinstall Python with "Add to PATH" checked on Windows)
- Restart VS Code after installing Python
- Try opening a new terminal window

### "externally-managed-environment" error

This occurs on some Linux systems and newer macOS versions. Solutions:

1. **Use a virtual environment** (recommended for this course):
   ```bash
   python3 -m venv .venv
   source .venv/bin/activate  # macOS/Linux
   pip install package-name
   ```

2. **Use `--user` flag** (installs for your user only):
   ```bash
   pip install --user package-name
   ```

### Permission/Access Denied Errors

**Don't use `sudo`!** Instead:

1. Use a virtual environment (recommended)
2. Or use the `--user` flag:
   ```bash
   pip install --user package-name
   ```

### Pip installs packages but they can't be imported

This usually means you have multiple Python installations and pip is installing to a different one than you're using. 

**Solution:**
```bash
python -m pip install package-name
```

This ensures you're using the same Python that's running.

---

## Need Help?

- Visit during office hours
- Check the course discussion board
- Email me with the error message and what you've tried

Remember: **don't stress if you run into issues!** We'll work through any problems together.
