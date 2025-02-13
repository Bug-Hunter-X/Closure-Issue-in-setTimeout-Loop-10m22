# Closure Issue in setTimeout Loop

This repository demonstrates a common closure issue in JavaScript when using `setTimeout` within a loop.  The expected behavior is to print numbers 0-9 after each one-second interval.  However, due to the way closures work, the loop completes before the `setTimeout` callbacks execute, resulting in all callbacks logging the final value of `i` (which is 10). 

## Bug Description
The problem stems from the fact that the `setTimeout` callbacks don't capture the value of `i` at the time they are created within the loop.  Instead, they capture a reference to `i`, which is updated by the loop until its completion.  Therefore, when the callbacks finally execute, `i` has already reached its final value.

## Solution
This issue can be easily resolved by using an immediately invoked function expression (IIFE) to create a new scope for each iteration of the loop, capturing the current value of `i`.

## How to Run
1. Clone the repository.
2. Open `bug.js` to see the buggy code.
3. Open `bugSolution.js` to see the corrected code.
4. Execute each file in your browser's console or a Node.js environment.