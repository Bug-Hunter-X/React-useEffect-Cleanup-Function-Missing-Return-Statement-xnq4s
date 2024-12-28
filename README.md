# React useEffect Cleanup Function Missing Return Statement

This repository demonstrates a common error in React's `useEffect` hook: forgetting to include a return statement in the cleanup function. This can lead to memory leaks and unexpected behavior.

## The Bug

The `bug.js` file contains a component that fetches data using `fetch` within a `useEffect` hook. However, it omits the return statement which is crucial for cleaning up side effects.  When the component unmounts or the dependency array changes, the unfinished `fetch` request might keep running which would lead to a memory leak.

## The Solution

The `bugSolution.js` file corrects this by adding the necessary return statement. The return statement ensures any in-flight fetch requests are aborted to prevent memory leaks, particularly when the component is unmounted or updates occur.

## How to Reproduce

1. Clone this repository.
2. Navigate to the directory containing the JavaScript files.
3. Run the code, you will observe how the component will continue running even after the component is unmounted.