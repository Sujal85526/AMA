## AMA-2

**Q:** What is difference between semantic and non-semantic elements?  
**A:** Semantic tags describe meaning (`<header>`, `<article>`), non-semantic are generic (`<div>` for anything).

**Q:** Type of variables in JS?  
**A:** Primitive (string, number, boolean, null, undefined, symbol, bigint) and objects; e.g., `let age = 20` (number), `let user = {}` (object).

**Q:** When do we use `ALTER` command in SQL?  
**A:** To modify schema objects, like adding/dropping columns or constraints; `ALTER TABLE users ADD email TEXT;`.

**Q:** What is the use of CSS `overflow` property?  
**A:** Controls how content exceeding a container is handled, e.g., `overflow: scroll;` adds scrollbars.

**Q:** What is the difference between `var`, `let`, and `const` in JavaScript?  
**A:** `var` is function-scoped and hoisted, `let` is block-scoped, `const` is block-scoped and immutable binding; `const name = "Ana";`.

**Q:** What is a closure in JavaScript?  
**A:** A function plus its preserved outer scope, e.g., `function outer(){let x=1; return ()=>x;}` keeps `x`.

**Q:** What is a higher-order function in JavaScript?  
**A:** A function that takes other functions as arguments or returns one; `array.map(cb)` calls `cb` for each item.

**Q:** What is debouncing in JavaScript?  
**A:** Delaying a function call until after a pause in repeated events, like waiting 300 ms after typing before searching.

**Q:** What is SQL Injection?  
**A:** A security attack injecting malicious SQL via input, e.g., entering `' OR 1=1 --` to bypass login checks.

**Q:** What is a composite primary key?  
**A:** A primary key made of multiple columns to guarantee row uniqueness.

**Q:** What is `git revert` used for?  
**A:** To create a new commit that undoes the changes introduced by a specific commit.

**Q:** What is hoisting in JavaScript?  
**A:** JavaScript moves declarations to the top of their scope before execution.

