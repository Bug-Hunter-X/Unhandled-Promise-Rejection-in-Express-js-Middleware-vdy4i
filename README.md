# Unhandled Promise Rejection in Express.js Middleware

This repository demonstrates a common error in Node.js Express.js applications where errors thrown within asynchronous middleware are not properly handled, leading to silent failures.

## Bug Description
The `bug.js` file contains an Express.js application with an asynchronous route handler.  The asynchronous operation (`someAsyncOperation`) intentionally throws an error.  While the error is caught within the `.catch` block, it's not propagated to Express, preventing Express from sending an appropriate error response to the client.

## Solution
The `bugSolution.js` file demonstrates the correct way to handle errors in asynchronous Express.js middleware using `next(err)` to propagate errors to Express's error-handling middleware. This allows for consistent error handling and avoids silent failures.