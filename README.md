# React setInterval Memory Leak
This repository demonstrates a common error in React components that involves using `setInterval` within the `useEffect` hook without proper cleanup.  This leads to a memory leak because the interval continues to run even after the component unmounts.

## Bug
The `bug.js` file shows a React component that uses `setInterval` to update a counter every second. However, it's missing a crucial part: a cleanup function to `clearInterval`. This results in a memory leak.

## Solution
The `bugSolution.js` file provides the corrected code. The `useEffect` hook now includes a return function, which acts as a cleanup function. This function clears the interval when the component unmounts, preventing the memory leak.  This ensures that the `setInterval` is properly stopped when the component is no longer needed.