# Node.js Server Unresponsiveness

This repository demonstrates a common issue in Node.js where a long-running synchronous operation in a request handler blocks the event loop, causing the server to become unresponsive.  The `server.js` file contains the problematic code, while `serverSolution.js` provides a solution using asynchronous operations.

## Problem

The original server code simulates a long-running task within the request handler. This blocks the event loop, meaning that Node.js is unable to handle any further requests until this task finishes.  This can lead to significant performance issues and even crashes in production environments.

## Solution

The solution involves refactoring the code to use asynchronous operations (like promises, async/await, or callbacks). This allows the event loop to continue handling other tasks while the long-running operation is in progress.