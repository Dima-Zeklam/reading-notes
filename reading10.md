# Stacks and Queues

## Stack 

A Stack is a *linear data structure* or container of objects that are inserted and removed according to the last-in first-out (LIFO) principle or First-In Last-Out (FILO) principle, that mean the sequential access is only possible.

* The operations that can be performed on the stack:
   * push(x): used to insert  node at the top of the stack (pushed), we need to pass element that want to be bushed and pushing a Node onto a stack will always be an O(1) operation. 
   * pop : used to delete node  from the top of the stack and we dont pass an arg. You would check if the stack is empty or not before conducting a pop to ensure that an exception is not raised. The poped operatin takes O(1).
   * Top: This is the top of the stack.
   * Peek: function just returns the value of the top element available in the stack. You would check if the stack is empty or not before conducting a peek to ensure that an exception is not raised.The peek operatin takes O(1).
   * IsEmpty:  this function will return a true value if the stack is empty or otherwise it will return a false value and it take O(1).

#### Example on pseudocode: 


![Stack](https://cdn.programiz.com/sites/tutorial2program/files/stack.png)


For pushing a value onto a stack:

```
ALOGORITHM push(value)
// INPUT <-- value to add, wrapped in Node internally
// OUTPUT <-- none
   node = new Node(value)
   node.next <-- Top
   top <-- Node
   
```

For poped a value from a stack:
```
ALGORITHM pop()
// INPUT <-- No input
// OUTPUT <-- value of top Node in stack
// EXCEPTION if stack is empty

   Node temp <-- top
   top <-- top.next
   temp.next <-- null
   return temp.value
```

For peek a value from a stack:
```
ALGORITHM peek()
// INPUT <-- none
// OUTPUT <-- value of top Node in stack
// EXCEPTION if stack is empty

   return top.value
```

## Queue
![Queue](https://www.tutorialspoint.com/data_structures_algorithms/images/queue_example.jpg)

Is a container of objects (a linear collection) that are inserted and removed according to the first-in first-out (FIFO) and (LILO)
Last-In Last-Out principle 

* The operations that can be performed on the queue:
   * Enqueue - used to add node at the Front of the queue and it's operation will always be an O(1) . 
   * Dequeue - used to delete node from the queue and we dont pass an arg. You would check if the stack is empty or not before conducting a Dequeue to ensure that an exception is not raised. This operatin takes O(1).
   * Front - This is the front/first Node of the queue.
   * Rear - This is the rear/last Node of the queue.
   * Peek - function just returns the value of the Front element available in the queue. You would check if the queue is empty or not before conducting a peek to ensure that an exception is not raised.The peek operatin takes O(1).
   * IsEmpty - returns true when queue is empty otherwise returns false.


#### Example on pseudocode:  

For Enqueue a value onto a queue:
![Enqueue](https://www.tutorialspoint.com/data_structures_algorithms/images/queue_enqueue_diagram.jpg)


```
ALGORITHM enqueue(value)
// INPUT <-- value to add to queue (will be wrapped in Node internally)
// OUTPUT <-- none
   node = new Node(value)
   rear.next <-- node
   rear <-- node
```
For Dequeue a value from a queue:
![Dequeue](https://www.tutorialspoint.com/data_structures_algorithms/images/queue_dequeue_diagram.jpg)

```
ALGORITHM dequeue()
// INPUT <-- none
// OUTPUT <-- value of the removed Node
// EXCEPTION if queue is empty

   Node temp <-- front
   front <-- front.next
   temp.next <-- null

   return temp.value
```

For Peek a value from a queue:

```
ALGORITHM peek()
// INPUT <-- none
// OUTPUT <-- value of the front Node in Queue
// EXCEPTION if Queue is empty

   return front.value
```

For check if queue is Empty : 

```
ALGORITHM isEmpty()
// INPUT <-- none
// OUTPUT <-- boolean

return front = NULL
```


