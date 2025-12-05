# JavaScript Questions and Answers

## What is the difference between break and continue?

**break**: Exits the loop immediately and continues execution after the loop.

**continue**: Skips the current iteration and moves to the next iteration of the loop.

**Example:**
```javascript
for (let i = 0; i < 5; i++) {
  if (i === 2) break;    // Loop stops at i=2
  if (i === 1) continue;  // Skips i=1, continues to i=2
}
```

---

## Why do we use trim()?

**trim()** removes whitespace (spaces, tabs, newlines) from both ends of a string.

**Use cases:**
- Clean user input (e.g., form fields)
- Remove accidental spaces before/after text
- Normalize string data

**Example:**
```javascript
"  hello world  ".trim()  // Returns "hello world"
```

---

## What is the use of module.exports?

**module.exports** is used in Node.js to export functions, objects, or values from a module so they can be imported and used in other files.

**Example:**
```javascript
// math.js
module.exports = {
  add: (a, b) => a + b,
  subtract: (a, b) => a - b
};

// app.js
const math = require('./math');
math.add(2, 3);  // 5
```

---

## Different types of loops in JS?

1. **for** - Traditional loop with initialization, condition, and increment
2. **while** - Loops while condition is true
3. **do...while** - Executes at least once, then checks condition
4. **for...in** - Iterates over object properties
5. **for...of** - Iterates over iterable values (arrays, strings)
6. **forEach** - Array method that executes a function for each element

**Example:**
```javascript
for (let i = 0; i < 5; i++) { }
while (condition) { }
do { } while (condition);
for (let key in obj) { }
for (let value of array) { }
array.forEach(item => { });
```

---

## What is Inversion of Control in callbacks?

**Inversion of Control (IoC)** means giving control of function execution to another function (the callback). Instead of your code calling a function directly, you pass a function that gets called later by the other code.

**Example:**
```javascript
// You don't control WHEN the callback runs
setTimeout(() => {
  console.log("This runs later");
}, 1000);
```

---

## What problem does "callback hell" describe?

**Callback hell** (pyramid of doom) occurs when you nest multiple callbacks inside each other, making code hard to read and maintain.

**Problem:**
```javascript
getData(function(a) {
  getMoreData(a, function(b) {
    getMoreData(b, function(c) {
      // Hard to read and maintain!
    });
  });
});
```

**Solution:** Use Promises or async/await instead.

---

## How is a Promise different from a callback?

**Callback**: A function passed as an argument that gets executed later.

**Promise**: An object representing a future value that can be in pending, fulfilled, or rejected state. Provides better error handling and avoids callback hell.

**Callback example:**
```javascript
getData(function(result) {
  // Handle result
});
```

**Promise example:**
```javascript
getData()
  .then(result => { /* Handle result */ })
  .catch(error => { /* Handle error */ });
```

---

## What are the three states of a Promise?

1. **Pending** - Initial state, neither fulfilled nor rejected
2. **Fulfilled** - Operation completed successfully
3. **Rejected** - Operation failed

---

## What is the purpose of .then() and .catch() in Promises?

- **.then()** - Handles successful promise resolution (fulfilled state)
- **.catch()** - Handles promise rejection (error handling)

**Example:**
```javascript
promise
  .then(result => console.log("Success:", result))
  .catch(error => console.log("Error:", error));
```

---

## What does Promise.all() do, and what happens if one promise fails?

**Promise.all()** waits for all promises to resolve and returns an array of results.

**If one promise fails**: The entire Promise.all() rejects immediately with the first rejection. Other promises may still be running, but their results are ignored.

**Example:**
```javascript
Promise.all([promise1, promise2, promise3])
  .then(results => console.log(results))  // All succeeded
  .catch(error => console.log(error));    // One failed
```

---

## How is Promise.allSettled() different from Promise.all()?

**Promise.all()**: Fails fast - rejects immediately if any promise fails.

**Promise.allSettled()**: Waits for all promises to complete (success or failure) and returns results for all, regardless of individual outcomes.

**Example:**
```javascript
Promise.allSettled([promise1, promise2])
  .then(results => {
    // results contains status and value/reason for each promise
    // Even if one fails, you get results for all
  });
```

---

## What does Promise.race() return?

**Promise.race()** returns the result of the first promise that settles (either fulfills or rejects). The other promises continue running but their results are ignored.

**Example:**
```javascript
Promise.race([slowPromise, fastPromise])
  .then(result => {
    // Returns result from whichever completes first
  });
```
