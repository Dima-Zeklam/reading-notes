# Introduction to React and Components
![react](https://res.cloudinary.com/practicaldev/image/fetch/s--3zWuwYa3--/c_imagga_scale,f_auto,fl_progressive,h_900,q_auto,w_1600/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/pdib9r9rk5j1m7oala1p.png)
## Component-Based Architecture

1. What is a component?

A **component** is a modular, portable, replaceable, and reusable set of well-defined functionality that encapsulates its implementation and exporting it as a higher-level interface.
A **component** is a software object, intended to interact with other components, encapsulating certain functionality or a set of functionalities. It has an obviously defined interface and conforms to a recommended behavior common to all components within an architecture.

2. What are the charactistics of a component?

* *Reusability* − Components are usually designed to be reused in different situations in different applications. However, some components may be designed for a specific task.

* *Replaceable* − Components may be freely substituted with other similar components.

* *Not context specific* − Components are designed to operate in different environments and contexts.

* *Extensible* − A component can be extended from existing components to provide new behavior.

* *Encapsulated* − A A component depicts the interfaces, which allow the caller to use its functionality, and do not expose details of the internal processes or any internal variables or state.

* *Independent* − Components are designed to have minimal dependencies on other components.

3. What are the advantages of using component based architecture?

* **Ease of deployment** − As new compatible versions become available, it is easier to replace existing versions with no impact on the other components or the system as a whole.

* **Reduced cost** − The use of third-party components allows you to spread the cost of development and maintenance.

* **Ease of development** − Components implement well-known interfaces to provide defined functionality, allowing development without impacting other parts of the system.

* **Reusable** − The use of reusable components means that they can be used to spread the development and maintenance cost across several applications or systems.

* **Modification of technical complexity** − A component modifies the complexity through the use of a component container and its services.

* **Reliability** − The overall system reliability increases since the reliability of each individual component enhances the reliability of the whole system via reuse.

* **System maintenance and evolution** − Easy to change and update the implementation without affecting the rest of the system.

* **Independent** − Independency and flexible connectivity of components. Independent development of components by different group in parallel. Productivity for the software development and future software development.

## Props in React?
1. What is props short for?
**Props** is a special keyword in React, which stands for properties and is being used for passing data from one component to another.
2. How are props used in React?
Firstly, define an attribute and its value(data), Then pass it to child component(s) by using Props, Finally, render the Props Data.

```
class ParentComponent extends Component {  
  render() {
    return (
      <h1>
        I'm the parent component.
        <ChildComponent />
      </h1>
    );
  }
}

const ChildComponent = () => {  
  return <p>I'm the 1st child!</p>; 
};

```

3. What is the flow of props?
**Flow** is a static type checker for your JavaScript code. It is developed at Facebook and is often used with React. It lets you annotate the variables, functions, and React components with a special type syntax, and catch mistakes early. 

### read more about [Flow](https://reactjs.org/docs/static-type-checking.html)

## Things I want to know more about
* .NET
* COM/DCOM
* ECMAScript6

