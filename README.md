# React useEffect Hook Memory Leak
This repository demonstrates a common error in React applications involving the `useEffect` hook: a missing cleanup function that results in a potential memory leak.  The `bug.js` file contains the erroneous code, while `bugSolution.js` provides the corrected version.

## Problem
The `useEffect` hook in `bug.js` makes a fetch request but omits a return statement in the cleanup function. This means that when the component unmounts, any ongoing network requests or timers associated with the effect are not properly cleaned up, leading to a potential memory leak, especially with many unmounted components.