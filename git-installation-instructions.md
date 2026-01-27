# Git Setup Instructions for HIST 501D

## Important Notes

Git does not always come pre-installed with VS Code - they are separate tools. Installing and setting up git within VSCode is a one-time procedure that might cause some difficulties. Follow the instructions below (which are distinct for Mac and Windows users) and don't hesitate to reach out if you encounter problems. Importantly, don't stress it! If you can't get it done before next Monday (and thus can't finish the assignment in time), no problem! Visit me during office hours before class.

## Table of Contents

- [Git Setup Instructions for HIST 501D](#git-setup-instructions-for-hist-501d)
  - [Important Notes](#important-notes)
  - [Table of Contents](#table-of-contents)
  - [Opening a Terminal in VS Code](#opening-a-terminal-in-vs-code)
    - [Method 1: Menu Bar](#method-1-menu-bar)
    - [Method 2: Keyboard Shortcut (Fastest)](#method-2-keyboard-shortcut-fastest)
    - [Method 3: Command Palette](#method-3-command-palette)
    - [What is a Shell?](#what-is-a-shell)
    - [What is PATH?](#what-is-path)
    - [Selecting the Right Shell](#selecting-the-right-shell)
    - [Setting Git Bash as Default (Windows)](#setting-git-bash-as-default-windows)
  - [macOS Setup](#macos-setup)
    - [Step 1: Install Homebrew (if not already installed)](#step-1-install-homebrew-if-not-already-installed)
    - [Step 2: Install Git](#step-2-install-git)
    - [Step 3: Verify Git Installation](#step-3-verify-git-installation)
    - [Step 4: Configure Git with Your Identity](#step-4-configure-git-with-your-identity)
    - [Step 5: Verify Configuration](#step-5-verify-configuration)
  - [Windows Setup](#windows-setup)
    - [Step 1: Download and Install Git](#step-1-download-and-install-git)
    - [Step 2: Verify Git Installation](#step-2-verify-git-installation)
    - [Step 3: Configure Git with Your Identity](#step-3-configure-git-with-your-identity)
    - [Step 4: Verify Configuration](#step-4-verify-configuration)
  - [Cloning Your Coursework Repository](#cloning-your-coursework-repository)
    - [Method 1: Using VS Code GUI (Easiest)](#method-1-using-vs-code-gui-easiest)
    - [Method 2: Using Command Line](#method-2-using-command-line)
    - [Step 1: Get Your Repository URL](#step-1-get-your-repository-url)
    - [Step 2: Choose a Location](#step-2-choose-a-location)
    - [Step 3: Clone the Repository](#step-3-clone-the-repository)
    - [Step 4: Open in VS Code](#step-4-open-in-vs-code)
  - [Basic Git Workflow in VS Code](#basic-git-workflow-in-vs-code)
    - [Making Changes and Syncing](#making-changes-and-syncing)
    - [First-Time GitHub Authentication](#first-time-github-authentication)
    - [About .gitignore Files](#about-gitignore-files)
  - [Troubleshooting](#troubleshooting)
    - ["git: command not found" (macOS)](#git-command-not-found-macos)
    - ["git: command not found" (Windows)](#git-command-not-found-windows)
    - [VS Code doesn't show Git features](#vs-code-doesnt-show-git-features)
    - [Authentication/Permission Issues](#authenticationpermission-issues)
    - [Can't sync/push to GitHub](#cant-syncpush-to-github)
  - [Need Help?](#need-help)

---

## Opening a Terminal in VS Code

You'll need to use the terminal frequently for Git commands. Here's how to open it:

### Method 1: Menu Bar

- **macOS**: Terminal > New Terminal
- **Windows**: Terminal > New Terminal

### Method 2: Keyboard Shortcut (Fastest)

- **macOS**: `` Ctrl + ` `` (backtick/tilde key)
- **Windows**: `` Ctrl + ` `` (backtick/tilde key)

### Method 3: Command Palette

1. Press `Cmd+Shift+P` (macOS) or `Ctrl+Shift+P` (Windows)
2. Type "Terminal: Create New Terminal"
3. Press Enter

### What is a Shell?

A **shell** is a command-line interface that interprets and executes commands you type. Think of it as a text-based way to interact with your computer (as opposed to clicking icons with your mouse). Different shells have slightly different syntax and features, but they all serve the same basic purpose.

**Common shells:**

- **zsh** (macOS default): Modern shell with enhanced features, fully compatible with bash commands
- **bash** (Git Bash on Windows): Traditional Unix shell, widely used in tutorials and documentation
- **PowerShell** (Windows): Microsoft's shell with Windows-specific features
- **Command Prompt** (Windows): Older Windows shell with different syntax

**For this course**: All the commands we use (Git, Python, file navigation) work identically in zsh and bash. If you're on Windows, use **Git Bash** for consistency with course materials and most online tutorials.

### What is PATH?

**PATH** is an environment variable that tells your computer where to look for executable programs when you type a command. When you type `git` or `python` in a terminal, your computer searches through a list of directories specified in your PATH to find the program.

**Example**: If you install Git in `/opt/homebrew/bin/`, but that directory isn't in your PATH, the terminal won't find `git` when you type the command - even though it's installed! You'll get "command not found" errors.

**Adding to PATH**: When you see instructions like `export PATH="/opt/homebrew/bin:$PATH"`, this adds a new directory to your PATH so the terminal can find programs installed there. You only need to do this once - the settings save in your shell configuration file (`.zshrc` or `.bash_profile`).

### Selecting the Right Shell

**macOS**:

- The default shell is usually `zsh` (recommended); you can also use `bash`
- You can verify by typing: `echo $SHELL`

**Windows**:

- The terminal dropdown (upper-right of terminal panel) lets you choose:
  - **Git Bash** (recommended if Git is installed - best for following course instructions)
  - PowerShell
  - Command Prompt
- Click the **˅** dropdown next to the **+** button to select your shell

### Setting Git Bash as Default (Windows)

1. Open VS Code settings: `Ctrl+,`
2. Search for: "terminal default profile windows"
3. Select **Git Bash** from the dropdown

Or add to your settings.json:

```json
"terminal.integrated.defaultProfile.windows": "Git Bash"
```

---

## macOS Setup

### Step 1: Install Homebrew (if not already installed)

Homebrew is a package manager that makes installing software easier on Mac.

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

**After installation**, follow the on-screen instructions to add Homebrew to your PATH:

```bash
echo 'export PATH="/opt/homebrew/bin:$PATH"' >> ~/.zshrc
source ~/.zshrc
```

### Step 2: Install Git

```bash
brew install git
```

### Step 3: Verify Git Installation

```bash
git --version
```

You should see something like: `git version 2.x.x`

### Step 4: Configure Git with Your Identity

**Replace with your information**:

- `user.name`: Can be your full name ("Jane Smith") OR your GitHub username ("jsmith42")
- `user.email`: **MUST be the same email address you used for your GitHub account** - this is how GitHub links commits to your profile

```bash
git config --global user.name "Your Full Name or GitHub Username"
git config --global user.email "your.github@email.com"
```

### Step 5: Verify Configuration

```bash
git config --global --list
```

---

## Windows Setup

### Step 1: Download and Install Git

1. Go to [Download and Install Git](https://git-scm.com/download/win)
2. Download the installer (64-bit recommended)
3. Run the installer with these recommended settings:
   - **Editor**: Select "Use Visual Studio Code as Git's default editor"
   - **PATH environment**: Select "Git from the command line and also from 3rd-party software"
   - **Line ending conversions**: Select "Checkout Windows-style, commit Unix-style line endings"
   - **Terminal emulator**: Select "Use Windows' default console window" or "Use MinTTY"
   - Keep other defaults

### Step 2: Verify Git Installation

Open a **new** Command Prompt or PowerShell window:

```bash
git --version
```

You should see something like: `git version 2.x.x`

**Note**: You must open a NEW terminal window after installation for the PATH changes to take effect.

### Step 3: Configure Git with Your Identity

**Replace with your information**:

- `user.name`: Can be your full name ("Jane Smith") OR your GitHub username ("jsmith42")
- `user.email`: **MUST be the same email address you used for your GitHub account** - this is how GitHub links commits to your profile

```bash
git config --global user.name "Your Full Name or GitHub Username"
git config --global user.email "your.github@email.com"
```

### Step 4: Verify Configuration

```bash
git config --global --list
```

---

## Cloning Your Coursework Repository

Once Git is installed and configured, you can clone using either the command line OR the VS Code GUI.

### Method 1: Using VS Code GUI (Easiest)

1. **Get your repository URL**:
   - Go to your GitHub Classroom assignment repository
   - Click the green **"Code"** button
   - Make sure **HTTPS** is selected
   - Click the copy icon to copy the URL (looks like: `https://github.com/username/repo-name.git`)

2. **Clone in VS Code**:
   - Open VS Code
   - Press `Cmd+Shift+P` (macOS) or `Ctrl+Shift+P` (Windows) to open Command Palette
   - Type "Git: Clone" and select it
   - Paste your repository URL and press Enter
   - Choose a folder location where you want to save the repository
   - When prompted "Would you like to open the cloned repository?", click **Open**

### Method 2: Using Command Line

### Step 1: Get Your Repository URL

1. Go to your GitHub Classroom assignment repository
2. Click the green **"Code"** button
3. Make sure **HTTPS** is selected
4. Copy the URL (it should look like: `https://github.com/username/repo-name.git`)

### Step 2: Choose a Location

Create or navigate to a folder where you want to keep your course files:

- **macOS**: `/Users/yourname/Documents/courses/hist501d/`
- **Windows**: `C:\Users\YourName\Documents\courses\hist501d\`

### Step 3: Clone the Repository

```bash
cd /path/to/your/chosen/folder
git clone https://github.com/username/repo-name.git
```

### Step 4: Open in VS Code

```bash
cd repo-name
code .
```

(This assumes you have the `code` command installed in VS Code)

**Or** simply:

- Open VS Code
- File > Open Folder
- Navigate to and select your cloned repository folder

---

## Basic Git Workflow in VS Code

### Making Changes and Syncing

1. **Make changes** to your files (edit, create, delete)

2. **Stage changes**:
   - Click the Source Control icon in the left sidebar (branching icon)
   - Click the **+** button next to files to stage them
   - Or click **+** next to "Changes" to stage all

3. **Commit changes**:
   - Type a descriptive commit message in the message box
   - Example: "Complete week 2 reading response"
   - Click the **✓ Commit** button

4. **Sync to GitHub**:
   - Click the **Sync Changes** button (or **↑↓** icon)
   - This pushes your commits to GitHub
   - Enter your GitHub credentials if prompted

### First-Time GitHub Authentication

When you first push to GitHub, you may be prompted to authenticate:

- **macOS/Windows**: A browser window will open for GitHub authentication
- Sign in with your GitHub account
- VS Code will remember your credentials

### About .gitignore Files

A .gitignore file tells Git which files or types of files it should ignore (not track, commit, or push to GitHub). This is useful for keeping large, sensitive, or unnecessary files (like system files, temporary files, or compiled code) out of your repository. Git will ignore any file patterns listed in .gitignore. To track a file type (like PDFs), make sure it is not listed in .gitignore.

Common examples in .gitignore:

- *.log (ignore all log files)
- *.pyc (ignore Python bytecode)
- venv/ (ignore virtual environment folders)
- *.pdf (ignore all PDF files)

**Important for this course:**

If you want to commit and push PDF files (for example, to submit assignments as PDFs), you must remove *.pdf from your .gitignore file. Open the .gitignore file in your repository, find the line with `*.pdf`, and delete it or comment it out by adding a # at the start of the line. Save the file. Now you can add, commit, and push PDF files to GitHub.

---

## Troubleshooting

### "git: command not found" (macOS)

- Make sure you added Homebrew to your PATH (see Step 1)
- Close and reopen your terminal
- Run: `which git` to check if it's found

### "git: command not found" (Windows)

- Close and reopen your terminal/Command Prompt
- Check if Git is in your PATH: Settings > System > About > Advanced system settings > Environment Variables
- Reinstall Git if needed

### VS Code doesn't show Git features

- Make sure Git is installed: run `git --version` in a terminal
- Restart VS Code after installing Git
- Check VS Code settings: Search for "git.path" and make sure it's not disabled

### Authentication/Permission Issues

- Make sure you're using HTTPS URL (not SSH) if you haven't set up SSH keys
- Check that you have access to the repository on GitHub
- Try: `git remote -v` to see your remote URL

### Can't sync/push to GitHub

- Make sure you've committed your changes first (commit before sync)
- Check your internet connection
- Verify you have write access to the repository

---

## Need Help?

If you encounter issues:

1. Copy the exact error message
2. Note what command or action you were trying to do
3. Bring this information to office hours or post on the course forum
4. Include your operating system and Git version (`git --version`)
