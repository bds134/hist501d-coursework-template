# Week 2: Hands-On Practice

**During Class**: Follow along with instructor demos, then work through these practice activities.

**Remember**: Commit frequently! After each major section, stage and commit your changes.

---

## Setup

1. Make sure you're in the `hands-on` branch of your coursework repository
2. Open VSCode
3. Create a new folder: `week02-practice`
4. Open terminal: `Ctrl+\``
5. Navigate into your practice folder: `cd week02-practice`

---

## Practice 1: Variables & Types (10 min)

**Goal**: Store and work with different data types.

### Your Task

Create a new file: `historical_figure.py`

In this file, create variables for a historical figure of your choice:

```python
# Pick someone you're researching or interested in
name = "Your person's name"
birth_year = 1800  # Their birth year
death_year = 1875  # Their death year
is_alive = False
occupation = "Their occupation"
accomplishments = ["First thing they did", "Second thing", "Third thing"]

# Print each variable
print(name)
print(birth_year)
print(occupation)
print(accomplishments)

# Calculate their age
age = death_year - birth_year
print(f"{name} lived to be {age} years old")
```

**Run your code**: `python historical_figure.py`

**✓ Checkpoint**: Your output should show all the information about your historical figure.

**Commit**: `git add historical_figure.py` then commit with message: `Created historical figure variables`

---

## Practice 2: Working with Lists (12 min)

**Goal**: Practice list operations with historical data.

### Your Task

Create a new file: `presidents.py`

```python
# Create a list of presidents (any 5-7 presidents)
presidents = ["Washington", "Adams", "Jefferson"]

# 1. Print the entire list
print(presidents)

# 2. Print the first president
print(f"First president: {presidents[0]}")

# 3. Print the last president (use negative indexing)
print(f"Last president: {presidents[-1]}")

# 4. Add two more presidents to the list
presidents.append("Madison")
presidents.append("Monroe")

# 5. Print the length of the list
print(f"Total presidents in list: {len(presidents)}")

# 6. Print the second and third presidents using slicing
print(f"Presidents 2-3: {presidents[1:3]}")

# 7. CHALLENGE: Loop through and print each with their position
for i, president in enumerate(presidents):
    print(f"{i + 1}. {president}")
```

**Run it**: `python presidents.py`

**✓ Checkpoint**: You should see your full list, specific presidents, and a numbered list.

**Commit**: Stage and commit with message: `Practiced list operations`

---

## Practice 3: Dictionaries for Historical Data (15 min)

**Goal**: Structure historical information with dictionaries.

### Your Task

Create a new file: `historical_events.py`

```python
# Create a dictionary for a historical event
event = {
    "name": "Gettysburg Address",
    "date": "November 19, 1863",
    "location": "Gettysburg, Pennsylvania",
    "speaker": "Abraham Lincoln",
    "significance": "Redefined the Civil War as a struggle for equality"
}

# Print the entire dictionary
print(event)

# Access specific values
print(f"\nEvent: {event['name']}")
print(f"Date: {event['date']}")
print(f"Location: {event['location']}")

# Add a new key-value pair
event["duration"] = "2 minutes"
event["words"] = 272

# Print updated info
print(f"\nDuration: {event['duration']}")
print(f"Word count: {event['words']}")

# Print all keys
print(f"\nAvailable information: {list(event.keys())}")
```

**Run it**: `python historical_events.py`

**Now create your own**:
- Create a second dictionary for a different historical event
- Include at least 5 keys
- Print selected information using f-strings

**✓ Checkpoint**: You can access and print dictionary values by their keys.

**Commit**: Stage and commit with message: `Created historical event dictionaries`

---

## Practice 4: Loops with Historical Data (15 min)

**Goal**: Process multiple items using loops.

### Your Task

Create a new file: `battles.py`

```python
# List of Civil War battles with data
battles = [
    {"name": "Fort Sumter", "year": 1861, "casualties": 4},
    {"name": "Gettysburg", "year": 1863, "casualties": 51000},
    {"name": "Antietam", "year": 1862, "casualties": 22717},
    {"name": "Shiloh", "year": 1862, "casualties": 23746},
    {"name": "Chancellorsville", "year": 1863, "casualties": 30000}
]

# 1. Print each battle name
print("Civil War Battles:")
for battle in battles:
    print(f"- {battle['name']}")

# 2. Print detailed information for each
print("\nBattle Details:")
for battle in battles:
    print(f"{battle['name']} ({battle['year']}): {battle['casualties']} casualties")

# 3. Calculate total casualties
total_casualties = 0
for battle in battles:
    total_casualties += battle['casualties']

print(f"\nTotal casualties across all battles: {total_casualties}")

# 4. Find battles from 1863
print("\nBattles in 1863:")
for battle in battles:
    if battle['year'] == 1863:
        print(f"- {battle['name']}")

# 5. CHALLENGE: Find the deadliest battle
deadliest = battles[0]
for battle in battles:
    if battle['casualties'] > deadliest['casualties']:
        deadliest = battle

print(f"\nDeadliest battle: {deadliest['name']} with {deadliest['casualties']} casualties")
```

**Run it**: `python battles.py`

**Your turn**:
- Change the battles list to a different historical topic (revolutions, elections, treaties, etc.)
- Add at least one more field to each dictionary
- Write a loop that filters based on a condition

**✓ Checkpoint**: You can loop through lists and access nested dictionary values.

**Commit**: Stage and commit with message: `Practiced loops with historical data`

---

## Practice 5: Functions (10 min)

**Goal**: Create reusable code with functions.

### Your Task

Create a new file: `age_calculator.py`

```python
def calculate_age(birth_year, death_year):
    """Calculate the age at death given birth and death years."""
    age = death_year - birth_year
    return age

def format_lifespan(name, birth_year, death_year):
    """Return a formatted string about a historical figure's lifespan."""
    age = calculate_age(birth_year, death_year)
    return f"{name} ({birth_year}-{death_year}) lived to be {age} years old."

# Test your functions
print(calculate_age(1809, 1865))
print(format_lifespan("Abraham Lincoln", 1809, 1865))
print(format_lifespan("Frederick Douglass", 1818, 1895))
print(format_lifespan("Harriet Tubman", 1822, 1913))
```

**Run it**: `python age_calculator.py`

**Your turn**:
- Create a function called `years_ago(event_year)` that calculates how many years ago something happened
- Create a function that takes a list of years and returns the average
- Test both functions with historical dates

**✓ Checkpoint**: Your functions work with different inputs and return correct values.

**Commit**: Stage and commit with message: `Created reusable functions`

---

## Challenge: Mini Historical Database (Optional)

If you finish early, create `historical_database.py`:

```python
# Create a list of dictionaries for historical figures
people = [
    {
        "name": "Susan B. Anthony",
        "birth": 1820,
        "death": 1906,
        "occupation": "Suffragist",
        "achievements": ["Founded NWSA", "Women's voting rights"]
    },
    # Add at least 3 more people
]

# Write functions to:
# 1. Print all names
# 2. Find people by occupation
# 3. Calculate average lifespan
# 4. List all achievements
```

---

## Reflection

Create a new file: `week02-reflection.md`

```markdown
# Week 2 Reflection

## What I Learned
- 
- 
-

## What Was Challenging
- 
-

## Questions I Still Have
- 
-

## How I Might Use This in My Research
- 
```

Fill it out and commit it!

---

## Before You Leave

Make sure you've committed all your work:
1. Check Source Control in VSCode
2. If you see changes, stage and commit them
3. All your practice files should be saved

---

## What's Next?

**Take-home exercises** (due next Monday) are in the `main` branch:
- `exercises/week02/python-fundamentals/` - Jupyter notebook exercises
- `exercises/week02/ph-text-files/` - Programming Historian tutorial

Switch branches when you're ready to start homework!

---

## Resources

- [Week 2 Reference Guide](../documentation/week02-reference.md)
- [Programming Historian: Working with Text Files](https://programminghistorian.org/en/lessons/working-with-text-files)
- Office hours: Mon 3:15-4:45pm, Tue 9:30-11am

**Remember**: Using Copilot is encouraged, but document it in your AI-use-log!
