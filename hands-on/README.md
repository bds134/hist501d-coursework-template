# Hands-On Practice Materials

**Branch**: `hands-on`  
**Purpose**: In-class practice activities

## What is This Folder?

This folder contains hands-on practice activities that you'll work through **during class time**. These are different from your take-home assignments - they're designed for in-class learning and experimentation.

## How to Access

These materials are on a separate Git branch called `hands-on`. To switch to this branch:

```bash
# Make sure you're in your coursework repository
cd path/to/your/coursework-repo

# Switch to the hands-on branch
git checkout hands-on

# Pull latest updates
git pull
```

To switch back to your assignments:

```bash
git checkout main
```

## Available Practice Files

### Week 1: [week-01-practice.md](week-01-practice.md)
**Topics**: VSCode, Command Line, Markdown, Git Basics

In-class activities:
- Practice 1: Command line navigation
- Practice 2: Working with files
- Practice 3: Writing markdown
- Practice 4: Git basics
- Practice 5: Explore VSCode

### Week 2: [week-02-practice.md](week-02-practice.md)
**Topics**: Python Fundamentals

In-class activities:
- Practice 1: Python basics (variables, types)
- Practice 2: Lists and historical data
- Practice 3: Dictionaries for records
- Practice 4: Control flow with dates
- Practice 5: Mini-project (census analysis)

## How to Use

1. **During class**: Open the practice file for the current week and work through the activities
2. **Follow along**: Instructor will guide you through some exercises
3. **Work at your pace**: You don't need to finish everything - practice what you can
4. **Commit your work**: Feel free to commit practice work to this branch
5. **Don't stress**: These are learning exercises, not graded assignments

## Git Branch Workflow

**Two branches in your repository:**
- **`main` branch**: Take-home assignments and graded work
- **`hands-on` branch**: In-class practice (not graded)

**Why separate branches?**
- Keeps your graded work clean and organized
- Allows you to experiment without affecting assignments
- You can always delete practice work and start over
- Easier to see what needs to be submitted vs. what's just practice

## Tips

- **Save your practice work**: Even though it's not graded, committing practice exercises helps you review later
- **Experiment freely**: This branch is for learning - mistakes are encouraged!
- **Reference later**: Come back to these exercises when working on assignments
- **Ask questions**: If stuck on practice activities, raise your hand - that's what they're for

## Switching Between Branches

**Common workflow:**

```bash
# During class - work on practice
git checkout hands-on
# ... do practice exercises ...
git add .
git commit -m "Completed Week 2 practice activities"
git push

# After class - work on assignments
git checkout main
# ... do your homework ...
git add .
git commit -m "Completed Week 2 assignment"
git push
```

**Check which branch you're on:**
```bash
git branch
# The branch with * is your current branch
```

## Questions?

- **"Do I need to submit practice work?"** - No, it's optional and not graded
- **"Should I commit practice exercises?"** - Yes, it's good practice and helps you review later
- **"Can I work on these at home?"** - Absolutely! They're great for review
- **"What if I mess up?"** - No problem! Hands-on branch is for experimenting
- **"How do I get practice files for new weeks?"** - `git checkout hands-on` then `git pull` before each class

## Need Help?

- Office hours: Mondays 3:15-4:45pm, Tuesdays 9:30-11am
- Email: bskopyk@binghamton.edu
- Ask during class - that's what practice time is for!
