# Silent Error in useEffect Cleanup Function in React Native

This repository demonstrates a common but often difficult-to-detect bug in React Native: an error thrown within the cleanup function of a `useEffect` hook being silently swallowed.

## The Problem
The provided `bug.js` file contains a `useEffect` hook with a cleanup function. Under certain conditions (like a race condition or premature unmounting), the cleanup function may attempt to unsubscribe from a subscription that's already null or undefined. This often throws an error which is not shown in the console, making debugging challenging.

## The Solution
The `bugSolution.js` file offers a solution that includes error handling within the cleanup function. This ensures that any errors are caught and logged to the console, making diagnosis much easier.

## How to Reproduce
1. Clone this repository.
2. Run `npm install` or `yarn install`.
3. Run the app. Observe the console output. The solution prevents any errors.

## Further Considerations
Consider adding more robust error handling, checking for null or undefined subscription before attempting to unsubscribe, and possibly providing more meaningful error messages to assist in debugging.