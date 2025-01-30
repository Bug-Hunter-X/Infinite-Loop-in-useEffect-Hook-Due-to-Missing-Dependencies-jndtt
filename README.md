# React useEffect Infinite Loop Bug

This repository demonstrates a common React bug involving the `useEffect` hook.  The component uses `useEffect` to log the current count to the console, however, the missing dependency array causes the effect to run continuously and creates an infinite loop.

## Bug Description

The `useEffect` hook, without a dependency array, runs after every render.  In this example, the state `count` is updated whenever the button is clicked, causing the component to re-render.  Because the effect lacks dependencies, it re-runs, logging the new count.  This creates a continuous loop, leading to performance issues and excessive console logging. 

## Solution

The solution is to add a dependency array to the `useEffect` hook.  This array specifies the values that the effect depends on.  Only when these values change will the effect run again.  In this case, the effect only needs to run when the `count` changes.

## How to Reproduce

1. Clone the repository.
2. Run `npm install` to install the required packages.
3. Run `npm start` to start the development server.
4. Observe the console, noting the continuous logging of count values.
5. Refer to `bugSolution.js` for a corrected version.