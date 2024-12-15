# React: Memory Leak in setInterval within useEffect

This repository demonstrates a common error in React applications: a memory leak caused by improper usage of `setInterval` within the `useEffect` hook.  The initial implementation lacks a cleanup function, resulting in multiple intervals running concurrently, leading to performance issues and memory leaks. The solution demonstrates the correct usage of `setInterval` with cleanup to prevent this.

## Bug

The `bug.js` file contains a React component that uses `setInterval` to update a counter every second. However, it fails to include a cleanup function within the `useEffect` hook, leading to memory leaks. Each render creates a new interval without clearing the previous one, resulting in a continuously increasing number of active intervals.

## Solution

The `bugSolution.js` file demonstrates the correct approach.  It uses the return function within the `useEffect` hook to clear the interval when the component unmounts or when the dependencies change. This ensures that no unnecessary intervals continue to run, preventing the memory leak.