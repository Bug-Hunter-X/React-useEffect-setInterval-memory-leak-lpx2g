# React useEffect setInterval Memory Leak
This repository demonstrates a common issue in React applications: memory leaks caused by improper cleanup in `useEffect` hooks using `setInterval`.

## Problem
The `MyComponent` component uses `setInterval` to update a counter every second. However, the cleanup function in the `useEffect` hook is not properly clearing the interval, leading to multiple intervals running concurrently and eventually causing a memory leak.

## Solution
The solution involves ensuring that `clearInterval` is called with the correct interval ID when the component unmounts or when the effect dependency changes.

## How to reproduce
1. Clone this repository.
2. Run `npm install` to install the dependencies.
3. Run `npm start` to start the development server.
4. Observe the counter in the browser. Note that even after unmounting the component, the counter will continue to increment in the background.

## How to fix
1. Replace the problematic `useEffect` with the corrected version in `bugSolution.js`.
2. Run `npm start` again. This time, the counter should stop incrementing correctly after unmounting.

This simple example demonstrates how easy it is to introduce subtle yet impactful memory leaks in React applications. Always make sure to clean up after yourself with `useEffect`!