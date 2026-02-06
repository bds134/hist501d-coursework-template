# Practice Exercise: Regex in VS Code Search

**Scenario:** You're working with a collection of historical documents and need to clean up inconsistencies. Use VS Code's Find/Replace functionality to practice regex patterns.

## Setup
1. Create a new file called `practice-text.txt` in your workspace
2. Copy this sample text into it:

```
Historical Census Records - 1890

Born: 2/15/1845
Born: 02-15-1845
Born: February 15, 1845

Names:
- J. Smith (b. 1820)
- Mary A. Johnson (b. 1832)
- T.W. Brown (b. 1845)
- Frederick Douglass (b. 1818)

Locations:
- talbot county md
- hale's ford va
- MEMPHIS TN
- Great Barrington  MA

Occupations:
educator,,activist
writer,speaker,
,reformer,abolitionist

Dates: 1845, 1920, 1865, 2025, 1776, 1999
Contact: email@example.com or john.doe@university.edu
Phone: 555-1234 or (555) 123-4567
```

## Exercises

**Open VS Code Search:** Press `Ctrl+F` (Windows/Linux) or `Cmd+F` (Mac) and enable regex mode by clicking the `.*` button.

## Exercise 1: Find 19th Century Years
**Task:** Match only years from 1800-1899  
**Pattern:** `\b18\d{2}\b`  
**Expected matches:** 1820, 1832, 1845, 1818, 1865  
**Try it:** How would you modify the pattern to match years 1800-1999?

## Exercise 2: Normalize Date Formats
**Task:** Find dates in numeric format (e.g., `2/15/1845` or `02-15-1845`)  
**Find pattern:** `\b(\d{1,2})[/\-](\d{1,2})[/\-](\d{2,4})\b`  
**Replace with:** `$1/$2/$3`  
**Expected result:** Both dates become `2/15/1845` and `02/15/1845`  
**Challenge:** How would you reorder to YYYY-MM-DD format?

## Exercise 3: Find Names with Initials
**Task:** Match names like "J. Smith" or "T.W. Brown"  
**Pattern:** `\b[A-Z]\.\s*[A-Z]?\.?\s*[A-Z][a-z]+\b`  
**Expected matches:** J. Smith, Mary A. Johnson, T.W. Brown  
**Question:** What does `\s*` mean? Why is it useful here?

## Exercise 4: Fix Location Capitalization (Preview Only)
**Task:** Find locations with inconsistent capitalization  
**Find pattern:** `^- (.+)$` (matches lines starting with dash)  
**In practice:** You'd use this to identify lines to manually fix or process with a script  
**Try:** What pattern would match only the two-letter state codes?

## Exercise 5: Find Double Commas
**Task:** Find consecutive commas (which often indicate missing values in data)  
**Pattern:** `,,`  
**Expected matches:** Three instances in the Occupations section  
**Note:** This pattern is useful for spotting data quality issues in comma-separated text and CSV files  
**Follow-up:** How would you find lines ending with a comma?

## Exercise 6: Extract Email Addresses
**Task:** Match email addresses  
**Pattern:** `\b[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}\b`  
**Expected matches:** email@example.com, john.doe@university.edu  
**Challenge:** Find only `.edu` email addresses

## Exercise 7: Find Phone Numbers (Multiple Formats)
**Task:** Match phone numbers in different formats  
**Pattern:** `\(?\d{3}\)?[-.\s]?\d{3}[-.\s]?\d{4}`  
**Expected matches:** 555-1234, (555) 123-4567  
**Note:** This is a simplified pattern; real phone numbers have more variations

## Exercise 8: Workspace-Wide Search
**Task:** Search across multiple files  
1. Press `Ctrl+Shift+F` (Windows/Linux) or `Cmd+Shift+F` (Mac) for workspace search
2. Enable regex mode
3. Try: `\b(18|19|20)\d{2}\b` to find all years in your project
4. Use "files to include" field: `**/*.{md,txt,csv}` to search specific file types

## Advanced Challenges

**Challenge A:** Create a regex that matches any of these date formats:
- `2/15/1845`
- `February 15, 1845`
- `15 Feb 1845`
- `1845-02-15`

**Challenge B:** Find names with middle initials or names, like:
- `Mary A. Johnson`
- `Frederick Douglass`
- `T.W. Brown`

**Challenge C:** Find and fix the location names to be in proper title case with uppercase state codes (e.g., `Talbot County MD`)

## Tips for Success
- Always test patterns on a small sample first
- Use the "Replace" preview (click the arrow next to Replace All) to verify changes
- Save your work before doing Replace All operations
- Remember: `.` matches any character; use `\.` for literal periods
- `\b` is your friend for matching whole words only
- Character classes like `[A-Z]` and `\d` make patterns more readable

## Extension: Try in Terminal
Once comfortable with VS Code search, try the same patterns with `grep`:

```bash
grep -n -E '\b18\d{2}\b' practice-text.txt
grep -n ',,' practice-text.txt
grep -n -E '\b[A-Z]\.\s*[A-Z][a-z]+\b' practice-text.txt
```
