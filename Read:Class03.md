# Passing Functions as Props

## React Docs - lists and keys
### 1. What does .map() return?
map function return a new array or modified array

### 2. If I want to loop through an array and display each value in JSX, how do I do that in React?
The `map()` method is the most commonly used function to iterate over an array of data in JSX, You can attach the `map()` method to the array and pass a callback function that gets called for each iteration. When rendering the User component, pass a unique value to the key prop. The key prop helps React keep track of JSX elements and identify any changes in the array.

### 4. Each list item needs a unique `key` .

### 5. What is the purpose of a key?
Keys help React identify which items have changed, are added, or are removed. Keys should be given to the elements inside the array to give the elements a stable identity.

```
const numbers = [1, 2, 3, 4, 5];
const listItems = numbers.map((number) =>
  <li key={number.toString()}>
    {number}
  </li>
);
```
Read more about [React Docs - lists and keys](https://reactjs.org/docs/lists-and-keys.html)

## The Spread Operator 

### 1. What is the spread operator?
Spread operator allows an iterable to expand in places where 0+ arguments are expected. It is mostly used in the variable array where there is more than 1 values are expected. It allows us the privilege to obtain a list of parameters from an array.

### 2. List 4 things that the spread operator can do.
* Copying an array.
* Concatenating or combining arrays.
* Using Math functions.
* Using an array as arguments.

### 3. Give an example of using the spread operator to combine two arrays.

```
const arr1 = [1,2,3]
const arr2 = [4,5,6]
const arr3 = [...arr1, ...arr2] //arr3 ==> [1,2,3,4,5,6]
```

### 4. Give an example of using the spread operator to add a new item to an array.

```
function sum(x, y, z) {
  return x + y + z;
}

const numbers = [1, 2, 3];

console.log(sum(...numbers));
// expected output: 6

console.log(sum.apply(null, numbers));
// expected output: 6
```

### 5. Give an example of using the spread operator to combine two objects into one.

```
const person = { name: 'David Walsh', gender: 'Male' };
const tools = { computer: 'Mac', editor: 'Atom' };
const attributes = { handsomeness: 'Extreme', hair: 'Brown', eyes: 'Blue' };

const summary = {...person, ...tools, ...attributes};
/*
Object {
  "computer": "Mac",
  "editor": "Atom",
  "eyes": "Blue",
  "gender": "Male",
  "hair": "Brown",
  "handsomeness": "Extreme",
  "name": "David Walsh",
}
*/
```

## Pass Functions Between Components
### 1. In the video, what is the first step that the developer does to pass functions between components?
create arrow function that contain map method to loop over the array and pass there values.


### 2. In your own words, what does the increment function do?
when click the button the function will add 1 to the variable counter, and make update for each time the button is clicked.

### 3.How can you pass a method from a parent component into a child component?
1. Create a child component .
2. Create a child component and put the below code inside that component.
`import Child from './Child'`

3. Then inside your parent function create another function to run our desire event and pass the child component to return.

### 4. How does the child component invoke a method that was passed to it from a parent component?
Create a boolean variable in the state in the parent class. Update this when you want to call a function. Create a prop variable and assign the boolean variable. From the child component access that variable using props and execute the method you want by having an if condition.

### Resources
* [The Spread Operator](https://medium.com/coding-at-dawn/how-to-use-the-spread-operator-in-javascript-b9e4a8b06fab)
* [React Docs - lists and keys](https://reactjs.org/docs/lists-and-keys.html)
* [Video about How to Pass Functions Between Components](https://www.youtube.com/watch?v=c05OL7XbwXU)
### Read more about :
* [React Docs - Conditional Rendering](https://reactjs.org/docs/conditional-rendering.html)
* [React Docs - Lifting State Up ](https://reactjs.org/docs/lifting-state-up.html)
