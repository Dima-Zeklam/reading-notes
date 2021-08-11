# Thinking in React

![Thinking in React](https://i.morioh.com/201022/2f6459ee.webp)

### 1. How would you break a mock into a component heirarchy?

1. Break The UI Into A Component Hierarchy
2. Build A Static Version in React
3. Identify The Minimal (but complete) Representation Of UI State
4. Identify Where Your State Should Live
5. Add Inverse Data Flow

### 2. What is the single responsibility principle and how does it apply to components?

The `single-responsibility principle` (SRP) is a computer-programming principle that states that every module, class or function in a computer program should have responsibility over a single part of that program's functionality, and it should encapsulate that part.

### 3. What does it mean to build a ‘static’ version of your application?
To build a static version of your app that renders your data model, you’ll want to build components that reuse other components and pass data using props. props are a way of passing data from parent to child. If you’re familiar with the concept of state, don’t use state at all to build this static version.


### 4. Once you have a static application, what do you need to add?
Deploying your static website

### 5. What are the three questions you can ask to determine if something is state?

1. Is it passed in from a parent via props? If so, it probably isn’t state.
2. Does it remain unchanged over time? If so, it probably isn’t state.
3. Can you compute it based on any other state or props in your component? If so, it isn’t state.

### 6. How can you identify where state needs to live?
* Identify every component that renders something based on that state.
* Find a common owner component (a single component above all the components that need the state in the hierarchy).
* Either the common owner or another component higher up in the hierarchy should own the state.
* If you can’t find a component where it makes sense to own the state, create a new component solely for holding the state and add
* it somewhere in the hierarchy above the common owner component.

## Things I want to know more about
* inverse data flow in React
* SRP
