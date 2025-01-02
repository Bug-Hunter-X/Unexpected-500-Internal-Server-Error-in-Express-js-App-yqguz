# Unexpected 500 Internal Server Error in Express.js App

This repository demonstrates a subtle bug in a Node.js Express.js application that results in an unexpected 500 Internal Server Error.  The issue occurs due to improper error handling and occurs even when there is no apparent error during synchronous code execution. The solution involves proper error handling that caters to asynchronous operation within the express app.

## Bug
The `bug.js` file contains the erroneous code.  Running this code may seemingly work fine but under heavier load or concurrent requests, it can lead to unexpected 500 errors.

## Solution
The `bugSolution.js` file demonstrates the correct implementation with improved error handling and asynchronous handling which prevents the 500 errors.

## How to reproduce the bug
1. Clone this repository.
2. Navigate to the directory containing `bug.js`.
3. Run `node bug.js`.
4. Send multiple requests to `http://localhost:3000/` simultaneously using tools like `curl` or `ab`.  You should see the issue occurring after several requests. Note that the issue might not be immediately apparent, it can manifest under high concurrency.

## How to run the solution
1. Navigate to the directory containing `bugSolution.js`.
2. Run `node bugSolution.js`.
3. Send multiple concurrent requests. This should be robust against the previous unexpected 500 errors. 
