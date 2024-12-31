# Express.js Route Handler Missing Error Handling for Invalid User ID

This repository demonstrates a common error in Express.js route handlers:  failure to handle invalid input gracefully.  Specifically, the `/users/:id` route attempts to parse the `id` parameter as an integer without checking whether it's actually a number. This leads to a crash if a non-numeric ID is provided.

## The Bug
The `bug.js` file contains the flawed route handler.  It uses `parseInt` directly on the `req.params.id` without validation, leading to a potential `NaN` error if the ID is not an integer.

## The Solution
The `bugSolution.js` file shows the corrected route handler.  It adds input validation to check if `req.params.id` is a valid integer before attempting to use it.