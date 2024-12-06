# React useEffect setInterval Memory Leak

This repository demonstrates a common error in React applications: memory leaks caused by improper use of `setInterval` within the `useEffect` hook.

The `bug.js` file shows the incorrect implementation, where `setInterval` is used to update a counter every second.  However, it's missing the crucial cleanup function to stop the interval when the component unmounts, leading to a memory leak.

The `bugSolution.js` file provides the corrected implementation with the appropriate cleanup function to prevent the memory leak.

## How to Reproduce

1. Clone this repository.
2. Run `npm install` to install dependencies.
3. Run `npm start` to start the development server.
4. Observe the counter in the browser.
5. Note that even after navigating away from the page, the `setInterval` continues, creating the memory leak.

## Solution

The solution is to use a cleanup function in the `useEffect` hook's return value. This cleanup function is responsible for stopping the `setInterval` when the component unmounts, preventing the memory leak.  Refer to `bugSolution.js` for the corrected code.