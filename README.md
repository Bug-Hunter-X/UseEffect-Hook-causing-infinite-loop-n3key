# React useEffect Infinite Loop Bug

This repository demonstrates a common React bug involving the `useEffect` hook causing an infinite loop. The bug occurs when the effect's dependencies array is incorrectly defined, leading to unnecessary re-renders and potentially crashing the application.

## Bug Description
The `useEffect` hook, in the `MyComponent` component, is designed to log the current count value to the console. However, because it lacks a dependency array, it runs after every render. This constant execution, in conjunction with the state update inside the `onClick` handler, creates a loop where the count is updated, triggering the effect, which logs the value, leading to another render, and so on.  This infinite loop overwhelms the browser and may cause it to crash.

## Solution
The solution involves correctly specifying the dependencies array for the `useEffect` hook. By passing `[count]` as the dependencies array, the effect only runs when the `count` state variable changes. This prevents the infinite loop and ensures the effect runs at appropriate times.