# Regex Cheat Sheet (VS Code / JavaScript)

- **`?` (optional quantifier)**: preceding token appears 0 or 1 time.
  - Example: `colou?r` → matches `color` or `colour`.
- **Literal question mark**: escape with `\?`.
  - Example: `How\?` → matches the text `How?`.
- **Lazy (non-greedy) quantifiers**: `*?`, `+?`, `??` — prefer the shortest match.
  - Example: `<.*?>` matches `<b>` (shortest tag), while `<.*>` is greedy.
- **Non-capturing group**: `(?:...)` — group without creating a numbered capture.
- **Named capture**: `(?<name>...)` — use in replacements as `$<name>`.
- **Backreference**: `\1`, `\2` in patterns; `$1`, `$2` in replacements.
- **Lookahead / lookbehind (assertions)**:
  - Positive lookahead: `(?=...)`  — e.g., `\d+(?= dollars)` matches digits before ` dollars`.
  - Negative lookahead: `(?!...)`.
  - Positive lookbehind: `(?<=...)` and negative lookbehind `(?<!...)` — supported in modern VS Code (V8 JS engine).
- **Replacement tokens (VS Code Find/Replace)**: `$1`, `$2` (numbered); `$<name>` (named); `$&` (entire match).
- **Inline flags**: `(?i)` and similar inline modifiers are not reliably supported in VS Code search — use the Find UI toggles (case-insensitive) instead.

Quick examples:

Find: `colou?r`  — matches `color` or `colour`

Find: `<.*?>`  — match shortest HTML tag contents

Find: `(\d{1,2})/(\d{1,2})/(\d{2,4})`  Replace: `$3-$1-$2`  — reorder date to `YYYY-M-D`

Find: `(?<=\$)\d+`  — digits preceded by `$` (lookbehind)

Find: `How\?`  — match literal question mark in text

Tip: test patterns in the VS Code Find panel on a copy of your file before using Replace All.

---
