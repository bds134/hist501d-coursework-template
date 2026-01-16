# Week 1: Hands-On Practice

**During Class**: Follow along with instructor demos, then work through these activities.

**Important**: Save your work frequently and commit as you complete each section!

---

## Setup

1. Make sure you're in the `hands-on` branch of your coursework repository
2. Open VSCode
3. Open your coursework repository folder in VSCode
4. Open the integrated terminal (`Ctrl+\``)

---

## Practice 1: Command Line Navigation (10 min)

**Goal**: Get comfortable moving around with commands.

### Tasks

1. Check where you are: `pwd`
2. List files in current directory: `ls`
3. Create a new folder called `week01-practice`: `mkdir week01-practice`
4. Move into that folder: `cd week01-practice`
5. Verify you're in the right place: `pwd`
6. Go back up one level: `cd ..`
7. Move back into week01-practice: `cd week01-practice`

**✓ Checkpoint**: Run `pwd` - you should see a path ending in `/week01-practice`

---

## Practice 2: Working with Files (10 min)

**Goal**: Create and explore files from the command line.

### Tasks

Still in your `week01-practice` folder:

1. Create an empty file: `touch notes.txt`
2. Verify it was created: `ls`
3. Create a markdown file: `touch my-bio.md`
4. List files again: `ls`
5. Try to view a file: `cat notes.txt` (should be empty)

**✓ Checkpoint**: Running `ls` should show both `notes.txt` and `my-bio.md`

---

## Practice 3: Writing Markdown (15 min)

**Goal**: Create a properly formatted markdown document.

### Tasks

1. In VSCode Explorer, navigate to your `week01-practice` folder
2. Click on `my-bio.md` to open it
3. Write a short academic bio including:
   - Your name as a level 1 heading (`#`)
   - "Research Interests" as a level 2 heading (`##`)
   - List 3-5 research interests (bullet points with `-`)
   - "Why Digital History?" as a level 2 heading
   - A paragraph explaining your interest in digital methods
   - Make at least one word **bold** and one word *italic*

4. Save your file (`Ctrl+S`)
5. Preview your markdown: `Ctrl+K V` (opens preview side-by-side)

**✓ Checkpoint**: Your preview should show properly formatted headings, lists, and text styling.

### Example Structure

```markdown
# Your Name Here

## Research Interests

- Colonial American History
- Digital archives
- Public history methods

## Why Digital History?

I'm interested in digital history because...
```

---

## Practice 4: Git Basics (15 min)

**Goal**: Track your changes with Git.

### Tasks

1. Click the Source Control icon in VSCode (3rd icon in Activity Bar, looks like a branch)
2. You should see your changed/new files listed
3. Click the `+` next to `my-bio.md` to stage it
4. Click the `+` next to any other files you created
5. In the message box at the top, type: `Completed week 1 practice activities`
6. Click the checkmark (✓) to commit
7. Add another line to your my-bio.md file: `## Goals for This Course`
8. Write 2-3 sentences about what you hope to learn
9. Save the file
10. Check Source Control - see that my-bio.md appears again as changed?
11. Stage and commit this change with message: `Added course goals`

**✓ Checkpoint**: Source Control should show "no changes" after your commit.

---

## Practice 5: Explore VSCode (5 min)

**Goal**: Get familiar with the interface.

### Tasks

1. Open the Command Palette: `Ctrl+Shift+P`
   - Type "theme" and explore color themes
   - Pick one you like!

2. Try the keyboard shortcut to open a file: `Ctrl+P`
   - Type the name of one of your files
   - Press Enter to open it

3. Split your editor: `Ctrl+\`
   - Open my-bio.md in one pane
   - Open notes.txt in another pane

4. Toggle terminal visibility: `Ctrl+\``
   - Practice showing/hiding it a few times

**✓ Checkpoint**: You feel comfortable navigating VSCode's interface.

---

## Challenge (Optional - If Time Remains)

Create a new markdown file called `research-project-ideas.md` with:

1. A main heading with your topic area
2. Three potential research questions (level 2 headings)
3. Under each question, list:
   - Potential sources (bullet list)
   - Why digital methods would help (paragraph)
4. Include at least one link to a relevant resource

Stage and commit your work!

---

## Reflection

Before you leave class, add a section to your `my-bio.md`:

```markdown
## Week 1 Reflection

What I learned today:
- 
- 
-

Questions I still have:
- 
-
```

Fill it out, save, stage, and commit with message: `Week 1 reflection`

---

## Need Help?

- Raise your hand during class
- Check the [week 1 reference guide](../documentation/week01-reference.md)
- Ask a neighbor
- Office hours: Mon 3:15-4:45pm, Tue 9:30-11am

---

## What's Next?

This practice stays in the `hands-on` branch. Your take-home exercises (due next Monday) are in the `main` branch in the `exercises/week01/` folder. Switch branches when you're ready to work on homework!
