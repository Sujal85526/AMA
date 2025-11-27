`# Technical Questions and Answers

**What is a transaction in SQL?**
A sequence of SQL operations executed as a single unit. Follows ACID: Atomicity (all-or-nothing), Consistency, Isolation, Durability.

**What does COUNT(*) include that COUNT(column) doesn't?**
- `COUNT(*)`: Counts all rows, including NULL rows
- `COUNT(column)`: Counts only rows where column is NOT NULL

**What is the difference between merge and rebase?**
- **Merge**: Creates merge commit, preserves branch history, non-destructive
- **Rebase**: Replays commits onto another branch, creates linear history, rewrites commits (can be destructive)

**What is a pseudo-element in HTML?**
A keyword (like `::before`, `::after`, `::first-line`) that styles specific parts of an element without adding HTML.

**What is the difference between Flexbox and Grid?**
- **Flexbox**: One-dimensional (row OR column), best for components and navigation
- **Grid**: Two-dimensional (rows AND columns), best for page layouts

**What is git stash used for?**
Temporarily saves uncommitted changes so you can switch branches or pull updates, then re-apply them later with `git stash pop`.

**What is a generator and why use it?**
A function using `yield` that generates values on-the-fly instead of storing them all in memory. More memory-efficient for large datasets.

**What is the difference between process and thread?**
- **Process**: Independent program with isolated memory, higher overhead, crash doesn't affect others
- **Thread**: Lightweight unit within a process sharing memory, lower overhead, crash can affect entire process

**What is the purpose of HAVING clause?**
Filters groups after `GROUP BY` (unlike `WHERE` which filters rows before grouping). Can use aggregate functions like `COUNT()`, `SUM()`.

**What is the difference between em and rem?**
- **em**: Relative to parent's font-size (compounds when nested)
- **rem**: Relative to root element's font-size (consistent, preferred)

**What is HTML responsive web design?**
Design approach using fluid grids, flexible images, and media queries to make websites work on all device sizes.

**What is the difference between id and class?**
- **id**: Unique identifier (one per page), use `#id-name` in CSS
- **class**: Reusable (multiple elements), use `.class-name` in CSS
