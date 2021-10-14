# Linked List

![Linked List](https://www.101computing.net/wp/wp-content/uploads/linked-list.png)

**Linked List is the collection of objects called nodes A node contains two fields i.e. data stored at that particular address and the pointer which contains the address of the next node in the memory.**

#### Types of Linked List
![Types of Linked List](https://miro.medium.com/max/875/1*AeMDLFUjR0w0J4n8CP4H6g.jpeg)

1. Singly Linked list, Only forward traversal is possible; we cannot traverse in the backward direction as it has only one link in the list.

2. Doubly Linked list,  is a list that has three parts in a single node, includes one data part, a pointer to its previous node, and a pointer to the next node.

3. Circular Linked list, the last node connects to the first node
4. Doubly Circular Linked listm has the features of both the circular linked list and doubly linked list.

##### Traversing 
To visit each node of the list at least once in order to perform some specific operation on it.
This will done by using these statments :
```
ptr = head;   
        while (ptr!=NULL)  
            {  
                ptr = ptr -> next;  
            }  

```
#### the difference between Array and Linked List
![Array vs Linked List](https://miro.medium.com/max/875/1*yZ3qwI2I2iR2C3KgafQhsA.png)


## complicity 
Describe the amount of time(how long a function takes to complete) and space (how much memory a function consumes while executing) that the function will takes.

Big O’s role is to describe the Worst Case of efficiency, It specifically looks at the factors mentioned Space and Time to analyze these limiting factors, we should consider 4 Key Areas for analysis:
1. Input Size - when we use array as parameter will directly increase the Input Size for the function.
2. Units of Measurement - The time in millisecondsm the number of lines of code that are executed and the number of “Basic Operations” that are executed specify the Running Time in our analysis.The the number of bytes required to store the characters and The additional Memory Space  to hold the input data and output data and the stack Space of recursive function calls specify the Memory Space.
 
3. Orders of Growth

Examples: 
##### This algorithm has an O(1) constant efficiency

```
ALGORITHM Sum(number a, number b)

   number val <-- a + b
   return val
```

##### Logarithmic Complexity, in this example giving us O(lgn) complexity growth

```
AlGORITHM Search(SortedArray[0...n - 1], int SearchValue)

    number mid <-- n/2

    firstHalf <-- SortedArray[0...mid]
    secondHalf <-- SortedArray[mid...n]
    current <-- SortedArray[mid]

    if current > SearchValue
          return Search(firstHalf, SearchValue)
    if current < SearchValue
          return Search(secondHalf, SearchValue)

    return current

```

##### Linear Complexity,in this algorithm giving us O(n) complexity growth because of the loop

```
ALGORITHM SumArray(arr[0...n - 1])

    number sum <-- 0

    for number i <-- 0 to n - 1 do
          sum <-- sum + arr[i]

    return sum 
```

#### Quadratic Complexitymin this algorithm giving us O(n^2) complexity growth becaues his algorithm has a nested for loop 

```

ALGORITHM BubbleSort(arr[0...n - 1])

    for number i <-- 0 to n - 1 do

       for number j <-- 0 to n - i - 1 do

          if arr[j] > arr[j + 1]
             Swap(arr[i], arr[j])

```

#### Cubic Complexity, in this Example the algorithm giving us O(n^3) complexity growth becaues it's involve an additional set of nested loops

```
ALGORITHM CubicCounter(number n)

    number count <-- 0

    for number i <-- 0 to n do
       for number j <-- 0 to n do
          for number k <-- 0 to n do

             count = count + 1

     return count
```

#### Exponential Complexity, in this example we are performing the same number of iterative or recursive loops as n leaving us with O(2^n) complexity growth

```
ALGORITHM FibonacciIndex(number n)

    if n <= 1
       return 1

    return FibonacciIndex(n - 1) + FibonacciIndex(n - 2);
```
4. Best Case, Worst Case, and Average Case
* Worst Case: The efficiency for the worst possible input of size n
* Best Case: The efficiency for the best possible input of size which it runs the quickest for all possible inputs of n.
* Average Case: The efficiency for a “typical” or “random” input of size n.

#### Asymptotic Notations
![Asymptotic](https://slideplayer.com/slide/7929497/25/images/26/Basic+asymptotic+efficiency+of+code.jpg)


The Big O for Array vs Linked list:
![Big O ](https://miro.medium.com/max/3000/1*3IlTLK_S0HmATuYQGxcbUA.png)	