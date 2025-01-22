# Node.js Server Unresponsiveness

This repository demonstrates a common issue in Node.js where a long-running synchronous operation in the request handler causes the server to hang and become unresponsive.  The `bug.js` file shows the problematic code, while `bugSolution.js` provides a solution using asynchronous operations.

## Problem

Node.js is single-threaded, so a long-running operation in the event loop blocks other operations. The example uses a simple `while` loop to simulate this, causing the server to become unresponsive to new requests.

## Solution

The solution involves refactoring the long-running task to use asynchronous techniques.  For I/O-bound operations, asynchronous functions (like those in the `fs` or `http` modules) are ideal. For CPU-bound tasks, consider using worker threads or a task queue to offload processing.