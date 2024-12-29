# React Native: Accessing State or Props Before Component Mount

This repository demonstrates a common error in React Native: attempting to access component state or props before the component has fully mounted. This often leads to `undefined is not an object (evaluating 'this.state.something')` errors.

The `BuggyComponent.js` file shows the erroneous code.  The `FixedComponent.js` file provides the corrected version.

## Problem

In React Native, accessing `this.state` or `this.props` within methods like `constructor` or other methods called before `componentDidMount` results in undefined values, because the component hasn't yet finished mounting and its internal state hasn't been populated.

## Solution

The proper solution is to only access and modify `this.state` or `this.props` within lifecycle methods like `componentDidMount`, `componentDidUpdate`, or within methods that are triggered after these lifecycle methods.