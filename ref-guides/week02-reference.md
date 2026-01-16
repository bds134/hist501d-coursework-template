# Week 2 Quick Reference: Python Fundamentals

*Use this as a reference during class and while completing assignments.*

## Variables & Data Types

```python
# Strings (text)
name = "Abraham Lincoln"
quote = 'Four score and seven years ago'

# Numbers
birth_year = 1809        # Integer
age_decimal = 56.5       # Float (decimal)

# Boolean (True/False)
is_president = True
still_alive = False

# Check type
type(name)               # Returns: <class 'str'>
```

## Lists (Ordered Collections)

```python
# Create a list
presidents = ["Washington", "Adams", "Jefferson"]

# Access items (zero-indexed!)
first = presidents[0]      # "Washington"
last = presidents[-1]      # "Jefferson" (last item)

# Slicing
first_two = presidents[0:2]  # ["Washington", "Adams"]

# Modify lists
presidents.append("Madison")      # Add to end
presidents.insert(0, "New")       # Insert at position
presidents.remove("Adams")        # Remove by value
presidents.pop()                  # Remove last item

# List operations
len(presidents)                   # Length of list
"Adams" in presidents             # Check if item exists
```

## Dictionaries (Key-Value Pairs)

```python
# Create a dictionary
person = {
    "name": "Susan B. Anthony",
    "birth_year": 1820,
    "occupation": "Suffragist",
    "accomplishments": ["Founded NWSA", "Organized protests"]
}

# Access values
name = person["name"]
birth = person["birth_year"]

# Add/modify entries
person["death_year"] = 1906
person["birth_year"] = 1820      # Update existing

# Dictionary methods
person.keys()                     # Get all keys
person.values()                   # Get all values
person.get("name", "Unknown")     # Safe access with default
```

## Control Flow: If/Else

```python
year = 1863

if year < 1776:
    period = "Colonial"
elif year < 1865:
    period = "Early Republic"
else:
    period = "Post-Civil War"

# Comparison operators: ==, !=, <, >, <=, >=
# Logical operators: and, or, not
```

## Loops

### For Loops (Iterate over collections)

```python
years = [1776, 1865, 1945, 2020]

# Loop through list
for year in years:
    print(year)

# Loop with index
for i, year in enumerate(years):
    print(f"{i}: {year}")

# Loop through range
for i in range(5):           # 0, 1, 2, 3, 4
    print(i)

for i in range(1800, 1810):  # 1800 to 1809
    print(i)
```

### While Loops

```python
year = 1800
while year < 1810:
    print(year)
    year += 1
```

## Functions

```python
# Define a function
def calculate_age(birth_year, current_year):
    """Calculate age given birth and current year."""
    age = current_year - birth_year
    return age

# Call the function
age = calculate_age(1809, 1865)
print(age)  # 56

# Function with default parameter
def greet(name, title="Dr."):
    return f"Hello, {title} {name}"

greet("Smith")              # "Hello, Dr. Smith"
greet("Jones", "Prof.")     # "Hello, Prof. Jones"
```

## String Operations

```python
text = "Four score and seven years ago"

# Common operations
text.upper()                      # UPPERCASE
text.lower()                      # lowercase
text.replace("Four", "Eight")     # Replace text
text.split()                      # Split into list of words
text.count("o")                   # Count occurrences
len(text)                         # Length of string

# String formatting (f-strings)
name = "Lincoln"
year = 1863
sentence = f"{name} delivered the address in {year}."
```

## File Input/Output

### Write to a file

```python
# Open file for writing (creates new or overwrites)
f = open("events.txt", "w")
f.write("American Revolution\n")
f.write("Civil War\n")
f.close()
```

### Read from a file

```python
# Read entire file
f = open("events.txt", "r")
content = f.read()
print(content)
f.close()

# Read line by line
f = open("events.txt", "r")
for line in f:
    print(line.strip())  # .strip() removes \n
f.close()
```

### Append to a file

```python
# Open file for appending (adds to end)
f = open("events.txt", "a")
f.write("World War I\n")
f.close()
```

### Better way: Using 'with' (auto-closes file)

```python
with open("events.txt", "w") as f:
    f.write("American Revolution\n")
# File automatically closed after this block
```

## Common List Operations

```python
battles = ["Gettysburg", "Antietam", "Shiloh"]

# Add items
battles.append("Bull Run")        # Add to end
battles.extend(["Vicksburg", "Atlanta"])  # Add multiple

# Remove items
battles.remove("Shiloh")          # Remove by value
last = battles.pop()              # Remove and return last

# Sort
battles.sort()                    # Sort in place
sorted_list = sorted(battles)     # Return sorted copy

# Other operations
battles.reverse()                 # Reverse order
count = battles.count("Shiloh")   # Count occurrences
index = battles.index("Gettysburg")  # Find position
```

## Working with Multiple Data Types

```python
# List of dictionaries (common pattern!)
battles = [
    {"name": "Gettysburg", "year": 1863, "casualties": 51000},
    {"name": "Antietam", "year": 1862, "casualties": 22717},
    {"name": "Shiloh", "year": 1862, "casualties": 23746}
]

# Access nested data
first_battle = battles[0]
name = battles[0]["name"]         # "Gettysburg"

# Loop through list of dicts
for battle in battles:
    print(f"{battle['name']} ({battle['year']}): {battle['casualties']} casualties")

# Filter data
battles_1863 = [b for b in battles if b["year"] == 1863]
```

## Common Errors & Fixes

### IndentationError

```python
# WRONG - inconsistent indentation
if year > 1800:
  print("19th century")
    print("After 1800")  # Error!

# CORRECT - consistent indentation (4 spaces)
if year > 1800:
    print("19th century")
    print("After 1800")
```

### IndexError: list index out of range

```python
presidents = ["Washington", "Adams"]
third = presidents[2]  # Error! Only 2 items (indices 0, 1)

# Fix: check length first
if len(presidents) > 2:
    third = presidents[2]
```

### KeyError: dictionary key doesn't exist

```python
person = {"name": "Lincoln"}
birth = person["birth_year"]  # Error! Key doesn't exist

# Fix: use .get() with default
birth = person.get("birth_year", "Unknown")
```

### TypeError: unsupported operand type(s)

```python
year = "1863"
result = year + 10  # Error! Can't add string and int

# Fix: convert types
year = int("1863")
result = year + 10  # Now works
```

## Useful Built-in Functions

```python
len(list)              # Length of list/string
max(list)              # Maximum value
min(list)              # Minimum value
sum(list)              # Sum of numbers
sorted(list)           # Return sorted copy
type(variable)         # Check data type
str(123)               # Convert to string
int("123")             # Convert to integer
float("3.14")          # Convert to float
```

## Need More Help?

- [Python Official Tutorial](https://docs.python.org/3/tutorial/)
- [Real Python Tutorials](https://realpython.com/)
- [Programming Historian: Working with Text Files](https://programminghistorian.org/en/lessons/working-with-text-files)
- Ask GitHub Copilot in VSCode!
