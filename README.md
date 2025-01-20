# Express.js Route Handler Error Handling Bug

This repository demonstrates a common error in Express.js route handlers: the lack of proper error handling for invalid input, specifically in route parameters.  The `bug.js` file contains the buggy code, which throws an error if the `id` parameter in the `/users/:id` route is not a valid number. The `bugSolution.js` file shows how to correctly handle this situation using `isNaN` and returning appropriate HTTP error codes.

## Bug

The `bug.js` file shows how a missing error check in the route parameter handling can lead to unexpected behavior and crashes.  The code attempts to parse the `id` parameter as an integer using `parseInt` without checking if the parameter is actually a number. If a non-numeric value is provided, `parseInt` will return `NaN`, leading to an error when searching the `users` array.

## Solution

The `bugSolution.js` file demonstrates how to properly handle this case. Before attempting to parse the `id` parameter, the code checks if it's a valid number using `isNaN`. If it's not a number, it returns a 400 Bad Request response.  Otherwise, it proceeds with parsing and searching for the user.