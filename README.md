# Node.js Server Hang - Synchronous Long Task

This repository demonstrates an uncommon Node.js server issue where a synchronous, long-running task blocks the event loop, causing the server to hang and become unresponsive to new requests.

The `server.js` file contains the buggy code. The `server-fixed.js` shows the solution.

## Problem
The server uses a `while` loop to simulate a 5-second delay.  This blocks the event loop, preventing it from handling other requests during this time. This is uncommon because typical Node.js errors involve asynchronous operations and callbacks. 

## Solution
The solution involves refactoring the long-running task to be asynchronous or using a worker thread to offload the task from the main thread and avoid blocking requests.

## How to run
1. Clone this repo.
2. Run `node server.js` to see the hanging behavior.
3. Run `node server-fixed.js` to see the corrected behavior.