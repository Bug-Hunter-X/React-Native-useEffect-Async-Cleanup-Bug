# React Native useEffect Async Operation Cleanup Bug

This repository demonstrates a common bug in React Native applications involving the `useEffect` hook and asynchronous operations.  The bug occurs when an asynchronous operation initiated within `useEffect` is not properly cleaned up before the component unmounts. This can lead to unexpected behavior, such as data inconsistencies or crashes.

## The Bug

The provided `bug.js` file contains a component that fetches data from an API using `useEffect`.  The issue lies in the lack of a proper cleanup function. If the component unmounts before the asynchronous operation completes, the cleanup function isn't called, potentially leading to memory leaks or race conditions.

## The Solution

The `bugSolution.js` file demonstrates the corrected implementation. A cleanup function is included in the `useEffect` hook to handle the cancellation of any ongoing asynchronous operations before the component unmounts. This ensures that resources are released and potential errors are avoided.

## How to Reproduce

1. Clone this repository.
2. Run `npm install` to install the necessary dependencies.
3. Run `npx react-native run-android` (or `npx react-native run-ios`) to run the app.
4. Observe the console for any errors.  Try quickly navigating away from the screen to simulate unmounting the component before the async operation completes.