# React useEffect setInterval Memory Leak

This repository demonstrates a common error in React applications involving the `useEffect` hook and `setInterval`.  The example showcases a memory leak due to improper cleanup of the interval when the component unmounts.

## Bug
The provided `MyComponent` uses `setInterval` within a `useEffect` hook.  However, the interval continues running even after the component is unmounted, leading to a memory leak because the component's state continues to be updated and rerenders, even when it is not present in the DOM.  This is a common pitfall when working with timers in React.

## Solution
The solution demonstrates how to properly handle the `setInterval` function. The `useEffect` hook's cleanup function (`return () => clearInterval(intervalId);`) ensures that the interval is cleared when the component unmounts, preventing the memory leak.