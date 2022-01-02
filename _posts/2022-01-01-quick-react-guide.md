---
layout: post
title: Quick React Guide
excerpt: concepts in React
category: react
tags: [react]
---

## What are functional components?
```
const MyFunctionalComponent = (props) => {
    return <div />;
}

// or

function MyFunctionalComponent(props) {
    return <div />;
}
```

## What are class components?
```
class MyClassComponent extends React.Component {
    render() {
        return <p>Hello, {this.props.name}</p>;
    }
}
```

## Functional vs class components?
Functional components accept props as an argument. Class components require a render function. Functional components are JavaScript functions, so you cannot use `setState` in them.

## Hooks
Hooks allow functional components to "hook into" React features. For example, `useState` lets you add React state to functional components. If you have a functional component that requires state, previously you had to convert it to a class. Now you can just use a Hook inside the existing functional component.

## `render` vs `componentDidMount`/`componentDidUpdate`
In React class components, the `render` method itself shouldn’t cause side effects. It would be too early — we typically want to perform our effects after React has updated the DOM. This is why in React classes, we put side effects into `componentDidMount` and `componentDidUpdate`.

## `useEffect`
This hook tells React that your component needs to do **something** after `render`.

## props vs state
props (short for “properties”) and state are both plain JavaScript objects. While both hold information that influences the output of render, they are different in one important way: props get passed to the component (similar to function parameters) whereas state is managed within the component (similar to variables declared within a function).

## useMemo vs useCallback
See [this helpful note](https://dmitripavlutin.com/react-usememo-hook/).

## Resources
* [Functional vs Class Components](https://djoech.medium.com/functional-vs-class-components-in-react-231e3fbd7108)
* [Introduction to useState hook](https://reactjs.org/docs/hooks-state.html)
* [useEffect hook](https://reactjs.org/docs/hooks-effect.html)
* [props vs state](https://reactjs.org/docs/faq-state.html)