# React 19 useEffect Double Run Bug

This repository demonstrates an uncommon bug in React 19 where the `useEffect` hook runs twice after a state update when `setCount` is called twice in quick succession.  This leads to unexpected behavior, specifically, the count being incremented by two instead of one.

## Bug Description
The issue is present when calling `setCount` multiple times within a single render cycle. While React typically batches these updates, this specific scenario results in two executions of the `useEffect` hook.

## Reproduction Steps
1. Clone the repository.
2. Run `npm install` to install the dependencies.
3. Run `npm start` to start the development server.
4. Observe that clicking the increment button increments the count by two instead of one, demonstrating that `useEffect` is running twice.

## Solution
The solution involves optimizing the state update to prevent multiple calls to `setCount` within the same render cycle.

## How to use the Solution
The solution is provided in `bugSolution.js` demonstrating the fix for the double count increment issue. The fix involves using functional updates with `setCount((prevCount) => prevCount + 1)` which prevents the double update issue in React 19 and ensures that useEffect runs only once per update