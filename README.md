# Express.js Route Handler Missing Error Handling for Invalid User ID

This repository demonstrates a common error in Express.js route handlers: the lack of proper error handling for invalid input.  Specifically, the `/users/:id` route attempts to parse the `id` parameter as an integer without validating it, resulting in potential crashes or unexpected behavior if the `id` is not a valid number.

The `bug.js` file contains the erroneous code. The `bugSolution.js` file provides a corrected version with robust error handling to address this issue.

## How to Reproduce

1. Clone this repository.
2. Run `npm install` to install the required dependencies.
3. Run `node bug.js` and try to access `/users/abc`. You will encounter an error because `parseInt('abc')` returns `NaN`, and the code doesn't handle this case.
4. Run `node bugSolution.js` and try the same. The improved code handles invalid input gracefully, returning a 404 error.

## Solution

The solution involves adding input validation to ensure the `userId` is a number before attempting to parse it.  The corrected code also includes more comprehensive error handling, providing clear error messages to the client.