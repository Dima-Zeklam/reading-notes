# State and Props

![State and Props](https://i.stack.imgur.com/wqvF2.png)

### 1. Based off the diagram, what happens first, the ‘render’ or the ‘componentDidMount’?
 render happens first.

### 2. What is the very first thing to happen in the lifecycle of React? 
Start with Mounting phase to putting elements into the DOM, starting with calling `constructor()` method.

### 3.Put the following things in the order that they happen: componentDidMount, render, constructor, componentWillUnmount, React Updates

1. constructor
2. render
3. componentDidMount
4. React Updates
5. componentWillUnmount

### 4. What does componentDidMount do?
If you need to load anything using a network request or initialize the DOM, it should go here. This method is a good place to set up any subscriptions. If you do that, don’t forget to unsubscribe in `componentWillUnmount()`.

### 5. What types of things can you pass in the props?
props enable you to pass variables from one to another component down the component tree.

### 6. What is the big difference between props and state?
props are handling outside the component and must be updated outside the component, but State are handling in the component and updated inside the component. Also when you change the state inside your application its going to re-render the section of your application but props you can't actually change them.  

### 7. When do we re-render our application?
React components automatically re-render whenever there is a change in their state or props.

### 8. What are some examples of things that we could store in state?
using a controlled component to fill out a form is a perfectly valid use of local state.

## Things I want to know more about
* *Bootstrap*

#### More resources About [Where to Hold React Component Data: state, store, static, and this](https://www.freecodecamp.org/news/where-do-i-belong-a-guide-to-saving-react-component-data-in-state-store-static-and-this-c49b335e2a00/)

### Resources [Component Lifecycle Events](https://medium.com/@joshuablankenshipnola/react-component-lifecycle-events-cb77e670a093) , [React State Vs Props](https://reactjs.org/docs/state-and-lifecycle.html) .

### Bookmark and Review
* [SyntheticEvent](https://reactjs.org/docs/events.html)
* [React Docs - State and Lifecycle](https://reactjs.org/docs/state-and-lifecycle.html)
* [React Docs - handling events](https://reactjs.org/docs/handling-events.html)
* [React Bootstrap Documentation](https://react-bootstrap.github.io/getting-started/introduction)
* [Boootstrap Cheatsheet](https://getbootstrap.com/docs/5.0/getting-started/introduction/)
* [Bootstrap Shuffle - Bootstrap CSS classes - a class “sandbox”](https://bootstrapshuffle.com/classes)
* [Netlify](https://en.wikipedia.org/wiki/Netlify)
