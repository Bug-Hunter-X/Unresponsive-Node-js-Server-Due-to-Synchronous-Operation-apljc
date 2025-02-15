# Node.js Unresponsive Server

This repository demonstrates a common issue in Node.js applications: an unresponsive server caused by a long-running synchronous operation that blocks the event loop.  The `blockingServer.js` file shows the problem, while `nonBlockingServer.js` provides the solution using asynchronous operations.

## Problem (`blockingServer.js`)

The server simulates a long-running task using a `while` loop.  This blocks the event loop, preventing the server from responding to subsequent requests.  Any attempts to connect will timeout.

## Solution (`nonBlockingServer.js`)

The solution involves avoiding synchronous, long-running operations.  Asynchronous methods, such as using `setTimeout` or promises, allow the event loop to continue processing other tasks while the long operation executes in the background. This keeps the server responsive.

## How to run:

1. Clone this repository.
2. Run `node blockingServer.js` to see the problem. (Expect timeouts).
3. Run `node nonBlockingServer.js` to see the solution. (The server will remain responsive).