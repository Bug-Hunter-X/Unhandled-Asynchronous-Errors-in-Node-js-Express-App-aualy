# Unhandled Asynchronous Errors in Node.js

This repository demonstrates a common error in Node.js applications involving unhandled asynchronous errors within Express.js routes.  When asynchronous operations throw exceptions, it's crucial to handle these gracefully and send appropriate error responses to the client.  Failure to do so can lead to unexpected behavior and a poor user experience.

## The Bug

The `bug.js` file showcases a simple Express.js server that simulates an asynchronous operation.  This operation randomly throws an error.  The crucial flaw lies in the error handling.  The `.catch` block logs the error, but it *doesn't* send an error response to the client.  This means the client will hang indefinitely.

## The Solution

The `bugSolution.js` file provides a corrected version.  It includes proper error handling that sends a relevant HTTP error response (500 Internal Server Error) to the client when an exception occurs.