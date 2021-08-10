# React and Forms

### React Docs - Forms
#### 1. What is a ‘Controlled Component’?
A controlled component is a component that renders form elements and controls them by keeping the form data in the component's state.

#### 2.Should we wait to store the users responses from the form into state when they submit the form OR should we update the state with their responses as soon as they enter them? Why.
We have to update the state with their responses as soon as they enter them, because React doesn’t track the input’s state.

#### 3. How do we target what the user is entering if we have an event handler on an input field?
Using event.target.value, the updated value can be fetched and further processed for submitting the form values to the server.

### The Conditional (Ternary) Operator Explained

![ternary operators](https://flutter-examples.com/wp-content/uploads/2020/03/ternary_operator.png)

#### 1. Why would we use a ternary operator?
Because Ternary operators can make statements more concise and easy to reason about.
#### 2. Rewrite the following statement using a ternary statement:

```
  if(x===y){
 console.log(true);
  } else {
 console.log(false);
  }
```
##### by using ternary operator:

```
x === y ?  console.log(true) :  console.log(false);
```

## Things I want to know more about
* Python 
* react-bootstrap