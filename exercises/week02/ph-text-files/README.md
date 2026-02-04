# Programming Historian: Working with Text Files

This file should replace the existing file at path "exercises\week02\ph-text-files\README.md"

This folder is for your Programming Historian tutorial exercise ("Working with Text Files in Python") and any of the optional related lessons you choose to complete.

## Instructions

Follow the [Working with Text Files in Python](https://programminghistorian.org/en/lessons/working-with-text-files) tutorial and create the following files in this folder:

### Files to Create

As you work through the tutorial, you'll create these files:

1. **file-output.py** - Script that writes "hello world" to a text file
2. **file-input.py** - Script that reads from a text file
3. **file-append.py** - Script that appends content to an existing text file
4. **helloworld.txt** - Text file created/modified by the above scripts

There are other (**optional**) py lessons on Programming Historian that you might find useful as well:

2. **obo.py** - A Python module containing reusable functions for text manipulation

- [From HTML to List of Words (part 1)](https://programminghistorian.org/en/lessons/from-html-to-list-of-words-1); this lesson creates **obo.py** (a module with the `stripTags` function) and **trial-content.py** (a script that downloads a web page and strips HTML). If you do this extra lesson, add these files to your folder.

3. **trial-content.py** - Script that uses functions from the obo module to fetch and clean web content

- [Creating and Viewing HTML Files with Python](https://programminghistorian.org/en/lessons/creating-and-viewing-html-files-with-python); this lesson creates **write-html.py** (a script that wraps text in HTML tags and saves it to a file). If you do this extra lesson, add it to your folder as well.

4. **write-html.py** - Script that wraps text in HTML tags and writes to a file

- [Code Reuse and Modularity in Python](https://programminghistorian.org/en/lessons/code-reuse-and-modularity); this lesson teaches the concepts of modules and functions (which are used in `obo.py`), though it creates different example files (`greet.py` and `using-greet.py`).

## What You'll Learn

### From "Working with Text Files in Python" (the core lesson)

- How to **write to a text file** - creating new files with the `'w'` mode
- How to **read from a text file** - opening and reading file contents with the `'r'` mode  
- How to **append to an existing file** - adding content without overwriting using the `'a'` mode
- Understanding **file objects** and methods (`open()`, `.write()`, `.read()`, `.close()`)
- Working with **strings** in Python (creating, concatenating, using quotes correctly)
- The difference between printing to screen vs. writing to files

### From the broader lesson series (optional - if you do the extra lessons)

If you choose to complete the optional lessons and create `obo.py`, `trial-content.py`, and `write-html.py`, you'll also learn:

- **[Code Reuse and Modularity](https://programminghistorian.org/en/lessons/code-reuse-and-modularity)** - creating your own modules with functions that other scripts can import
- **[Downloading Web Pages with Python](https://programminghistorian.org/en/lessons/working-with-web-pages)** - using `urllib.request` to fetch web content
- **[From HTML to List of Words (part 1)](https://programminghistorian.org/en/lessons/from-html-to-list-of-words-1)** - stripping HTML tags and cleaning text
- **[Creating and Viewing HTML Files with Python](https://programminghistorian.org/en/lessons/creating-and-viewing-html-files-with-python)** - wrapping text in HTML and generating output files

**Note:** The required lesson only covers basic file I/O and produces `helloworld.txt`. The optional lessons teach modular code organization and web scraping.

## Tips

### For the required lesson:

- Follow the "Working with Text Files" tutorial step by step - the order matters
- Run each example script (`file-output.py`, `file-input.py`, `file-append.py`) to see how file I/O works
- Make sure you understand the difference between `'w'`, `'r'`, and `'a'` modes before moving on

### If doing the optional lessons:

- Test each function in `obo.py` as you create it
- The "Code Reuse and Modularity" lesson teaches you to build a reusable module that you'll import in other scripts
- Work through the lessons in sequence - they build on each other

### General

- You can use GitHub Copilot to help, but make sure you understand what each function does

## Submission

Complete all required files and commit/push your work by the deadline. (Feb. 9, 2026, 9 am)

**Tip:** Commit and push frequently as you work! It's good version control practice and protects your work. You don't need to wait until everything is perfect—commit after completing each script.
