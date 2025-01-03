# React useEffect Infinite Loop Bug

This repository demonstrates a common error in React applications involving the `useEffect` hook.  The provided code creates an infinite loop because the state variable `count` is updated within the `useEffect` callback without specifying any dependencies.

## Bug Description

The issue stems from the lack of a dependency array in the `useEffect` hook. This causes the effect to run after every render. Because the effect updates the `count` state, this creates a continuous loop of re-renders, leading to an application crash or extremely poor performance. 

## Bug Solution

The solution involves correctly specifying the dependency array in `useEffect`. By providing an empty array (`[]`), you ensure that the effect only runs once after the initial render. If the effect needs to run based on other state changes, the relevant state variables should be included in the dependency array.